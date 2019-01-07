---
layout: post
title: "Loklak can now see sharper"
date: 2016-03-01 10:54:30
comments: true
description: "Loklak can now see sharper"
keywords: ""
category: blog

tags:

---
<div class='content'>
        <p><p>As you might <a href="/blog/2015/dentro-and-my-experiences-in-the-nokia-dogood-hackathon">already know</a>, I always had a soft corner in my heart for Microsoft, Windows and C#. I got my first major successes developing on that platform, and to be honest, I still think developing in Visual Studio is the best thing ever.</p>
<br />
<br /><blockquote>
<br /><p>Visual Studio feels like everything is right in the world.</p>
<br /></blockquote>
<br />
<br /><p>I set out to develop a C# wrapper for the<a href="http://loklak.org/"> Loklak server</a>, partly because I wanted more people to use Loklak on Windows, and partly&nbsp;to satisfy my Visual Studio cravings.</p>
<br />
<br /><p>My objectives were simple:</p>
<br />
<br /><ol>
<br />	<li>It should be platform independent.</li>
<br />	<li>It should support all Loklak server API calls.</li>
<br />	<li>It should follow the async/await pattern.</li>
<br />	<li>It should have tests.</li>
<br /></ol>
<br />
<br /><p>Well, I solved all those problems. Here is the final result. <a href="https://github.com/loklak/LoklakDotNet">LoklakDotNet on Github.</a></p>
<br />
<br /><h2>Supported Platforms are:</h2>
<br />
<br /><ol>
<br />	<li>.NET Framework 4.5</li>
<br />	<li>ASP.NET Core 5.0</li>
<br />	<li>Windows 8/8.1</li>
<br />	<li>Windows Universal (UWP)</li>
<br />	<li>Windows Phone 8.1</li>
<br />	<li>Windows Phone Silverlight 8.1</li>
<br />	<li>Xamarin.Android</li>
<br />	<li>Xamarin.iOS</li>
<br />	<li>Xamarin.iOS (Classic)</li>
<br /></ol>
<br />
<br /><p>Wow. That&#39;s a lot.</p>
<br />
<br /><p>The wrapper gives the raw JSON results from the server. You can choose to parse the JSON however you wish. <a href="http://www.newtonsoft.com/json">Newtonsoft.JSON</a> is highly recommened.&nbsp;You <a href="https://github.com/loklak/LoklakDotNet">can view the documentation for LoklakDotNet&nbsp;here.</a>&nbsp;</p>
<br />
<br /><p>Side Note: The documentation looks really cool. I used an automated doc generation tool.</p>
<br />
<br /><p>The wrapper is still in its early stages, so go ahead and <a href="https://github.com/loklak/LoklakDotNet">submit a PR!</a></p>
<br />
<br /><p><img alt="" src="http://biblipole.com/images/pictuers/do_you_know_how_c_talking.png" style="height:101px; width:662px" /></p>
<br /></p>
    </div>