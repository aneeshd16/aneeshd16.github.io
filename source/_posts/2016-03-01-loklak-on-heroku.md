---
layout: post
title: "Loklak on Heroku"
date: 2016-03-01 11:00:27
comments: true
description: "Loklak on Heroku"
keywords: ""
category: blog

tags:

---
 <div class='content'>
        <p><p>Over the last one year Loklak has been turning into quite a huge project. The main Loklak site (<a href="http://loklak.org">http://loklak.org</a>) hosts 125 million messages for 14 million users! How cool is that?</p>
<br />
<br /><p>Loklak is a P2P based service; the more peers, the better the service. Till very recently, the only way to have&nbsp;your own Loklak instance was to spin up a VM on a cloud provider, and then follow the instructions to install, build and start the Loklak server. This also meant that you had to download and install all required dependencies like JDK, ant, etc. Also, if the server unexpectedly shut down, you had to manually restart it. A major leap came when Loklak was dockerized. Yes! Loklak can now be easily installed with Docker. <a href="https://github.com/loklak/loklak_server/blob/master/installation_docker.md">Here are the instructions to deploy Loklak with Docker.</a></p>
<br />
<br /><p>A key piece missing was deployment to PaaS providers like Heroku. Heroku makes it super easy for developers and organizations to deploy the code without needing to worry about maintenance and deployment issues. You just need to upload your code and Heroku takes care of the rest. Since its underlying stack is Debian based Ubuntu, most applications will have no trouble running on it. However, Heroku does not give you direct access to the VM per se. There is no terminal access. All deployment and build commands are in a special file named <code>Procfile</code>, stored in the root directory of your project. This can handle most use cases and programming languages but not stuff like custom builds and deployment. To overcome this, Heroku has given us the option to <a href="https://devcenter.heroku.com/articles/third-party-buildpacks">create custom buildpacks</a>. To enable the deployment of Loklak on Heroku, a new buildpack was needed. The buildpack needed to:</p>
<br />
<br /><ol>
<br />	<li>Download JDK and ant.</li>
<br />	<li>Build the project&nbsp;using the <code>ant </code>command.</li>
<br />	<li>Start the server using the custom shell script in the <code>bin </code>directory of the project.</li>
<br /></ol>
<br />
<br /><p>Luckily, I found an <a href="https://github.com/dennisg/heroku-buildpack-ant">excellent buildpack for building ant projects to Heroku</a>. I promptly forked it and began writing my own modifications so that it could be used with Loklak server. I finally ended up with<a href="https://github.com/aneeshd16/heroku-buildpack-ant-loklak">&nbsp;Heroku buildpack for Loklak: Java (with Apache Ant)</a>. I also had to make a special start-up script in the Loklak server project so that the server runs in the foreground and logs are properly forwarded to Heroku&#39;s logging utility.</p>
<br />
<br /><h2 style="margin-left:0px; margin-right:0px">How to run the Loklak server on Heroku</h2>
<br />
<br /><ol>
<br />	<li>Create a Heroku account&nbsp;<a href="https://www.heroku.com/" style="box-sizing: border-box; color: rgb(64, 120, 192); text-decoration: none; background-color: transparent;">https://www.heroku.com/</a></li>
<br />	<li>Download the Heroku toolbelt&nbsp;<a href="https://toolbelt.heroku.com/" style="box-sizing: border-box; color: rgb(64, 120, 192); text-decoration: none; background-color: transparent;">https://toolbelt.heroku.com/</a></li>
<br />	<li>Login with heroku:&nbsp;<code>heroku login</code></li>
<br />	<li>Clone the Loklak server (if not already) :&nbsp;<code>git clone https://github.com/loklak/loklak_server.git</code></li>
<br />	<li>Create a heroku app:&nbsp;<code>heroku create</code></li>
<br />	<li>Set the buildpack:&nbsp;<code>heroku buildpacks:set https://github.com/aneeshd16/heroku-buildpack-ant-loklak.git</code></li>
<br />	<li>Push your app to heroku:&nbsp;<code>git push heroku master</code></li>
<br />	<li>Confirm the loklak server is running:&nbsp;<code>heroku logs --tail</code></li>
<br />	<li>Sometimes the server may take a while to start. The logs would show&nbsp;<code>State changed from starting to up</code>&nbsp;when the server is ready.</li>
<br />	<li>Open the URL of your server in your browser:&nbsp;<code>heroku open</code>.</li>
<br /></ol>
<br />
<br /><p>And that&#39;s it! Seems like the easiest way to deploy Loklak to the cloud. Keep in mind that a free dyno on heroku sleeps after some period of inactivity, and it may take a while for it to start up from the sleep phase. You can always upgrade to a paid tier if you wish. (Wish Heroku paid me for this post)</p>
<br />
<br /><p><img alt="" src="http://s.quickmeme.com/img/8c/8c86006f69f9a7f08140063782154842ef188b3a4a8eaa36457c90bb61a43884.jpg" style="height:481px; width:550px" /></p>
<br /></p>
    </div>