---
layout: post
title: "Node streams for AWS SQS"
permalink: node-streams-for-aws-sqs
date: 2020-05-21 18:06:24
comments: true
description: "Node streams for AWS SQS"
keywords: ""
categories:

tags:
---

## TL;DR:
SQS as a write stream.

Installation
```
npm i node-sqs-stream
```
or
```
yarn add node-sqs-stream
```

Link to Github project - [https://github.com/aneeshd16/node-sqs-stream](https://github.com/aneeshd16/node-sqs-stream)

If you've worked in Node.js for a while, you've probably heard of streams. I spent years knowing that streams exist, but never understood how they worked. Streams are one of the fundamental concepts that power Node.js applications. I learnt how streams work only recently and have been applying them in my projects for great results.

# Node SQS Stream
A Writable stream interface for AWS SQS. Stream data to AWS SQS directly from your read/transform streams. Uses [SQS batch send](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SendMessageBatch.html) to reduce costs. Batteries not included! Pass in your sqs client:

{% highlight js %}
const sqsClient = new AWS.SQS({apiVersion: '2012-11-05'});
const sqsStream = new SQSWritableStream({
    sqsClient: sqsClient,
    queueUrl: 'http://example-sqs-url',
});
someStream.pipe(sqsStream);
{% endhighlight %}

## Motivation
I had a use case where the contents of an entire Postgres database had to be transformed and then pushed to a SQS queue. One way to do this was to fetch results from Postgres in batches, transform and then send to SQS. However, while waiting for the next batch from Postgres, the process was essentially idle. This time could have been utilized for transformation or sending data to SQS also. The final solution was to stream results from Postgres using the excellent [pg-query-stream](https://www.npmjs.com/package/pg-query-stream), use a custom Transform stream for my data transformation and then pipe the results into node-sqs-stream. 

## Why Streams
Consider a use case where you need to run a series of tasks on a collection of data. For example - Read data from a file, convert it to upper case and then write it back to another file. Your code might look like this:

{% highlight js %}
const fs = require('fs');

//Callbacks
fs.readFile('in.txt', (err, data) => {
	if (err) return;
	const upperCase = data.toString().toUpperCase();
	fs.writeFile('out.txt', upperCase, (err, result) => {
		if (err) return;
		console.log('done callbacks');
	});
});

// Promises
fs.promises.readFile('in.txt')
	.then(data => data.toString().toUpperCase())
	.then(data => fs.promises.writeFile('out.txt', data))
	.then(result => console.log('done promises'))
	.catch(err => console.error(err));

// Async Await
(async () => {
	try {
		const data = await fs.promises.readFile('in.txt');
		const upperCase = data.toString().toUpperCase();
		await fs.promises.writeFile('out.txt', upperCase);
		console.log('done async/await');
	} catch (error) {
		console.error(error);
	}
})();

{% endhighlight %}


While all this is pretty straightforward, what happens when the file size is larger than available memory? All three methods above load the complete contents of the file in memory, modify them *in memory* and then write it back to another file. Streams can help us solve this problem. We can view the operation as 3 independent steps:
1. Read bytes from a file
2. Convert bytes to string and then uppercase it
3. Write bytes to a file

The above code looks like this when implemented with streams:

{% highlight js %}
const fs = require('fs');
// Read Stream
const inStream = fs.createReadStream('in.txt');
// Write Stream
const outStream = fs.createWriteStream('out.txt');
// Custom Transform Stream
const upperCaser = new Transform({
  transform(chunk, encoding, callback) {
    this.push(chunk.toString().toUpperCase());
    callback();
  }
});

// Push data from inStream -> upperCaser -> outStream
inStream.pipe(upperCaser).pipe(outStream);
{% endhighlight %}

You can run this code on a file with infinite size with limited memory resources. There are many resources online to explain how streams work in detail, but my TL;DR version is this:

Imagine a stream is dam. A dam has finite capacity. Water from the river keeps on flowing towards the dam. When the dam becomes full, it is opened till it can hold water again. 

In the NodeJS world, each stream has a buffer. When the buffer is full, the contents of the buffer are sent to the next stream as a "chunk".

## Further Reading
* [https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/](https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/)
* [https://nodesource.com/blog/understanding-streams-in-nodejs/](https://nodesource.com/blog/understanding-streams-in-nodejs/)
* [https://www.bennadel.com/blog/3236-using-transform-streams-to-manage-backpressure-for-asynchronous-tasks-in-node-js.htm](https://www.bennadel.com/blog/3236-using-transform-streams-to-manage-backpressure-for-asynchronous-tasks-in-node-js.htm)