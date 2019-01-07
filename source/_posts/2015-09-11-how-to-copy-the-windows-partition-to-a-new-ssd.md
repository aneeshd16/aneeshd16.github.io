---
layout: post
title: "How to copy the Windows partition to a new SSD"
date: 2015-09-11 11:04:51
comments: true
description: "How to copy the Windows partition to a new SSD"
keywords: ""
category: blog

tags:

---
<div class='content'>
        <p><p><a href="#soln">Skip to the Solution</a></p>
<br />
<br /><h2>Solidly Stating the Obvious</h2>
<br />
<br /><p>The summer had ended successfully, and I was ready to start some serious work. Over a period of 3 years, I had developed massive amounts of patience while watching my laptop boot from nought to 60 in 5 minutes. As my hard drive slowly started to fill up and the imaginary <em>jellyfication</em>&nbsp;of its innards, I decided that this was unacceptable and&nbsp;the first&nbsp;upgrade to my laptop&nbsp;was in order. Based from&nbsp;reviews on&nbsp;the net, a SSD seemed the perfect choice for speeding up my system. A trip to Nehru Place, and I was ready with a brand new 120GB Kingston SV300S37A SSD. I got to know about its shoddy performance a day later. After all, who would have guessed that a product from a well known company like Kingston would have such <a href="http://www.flipkart.com/kingston-sv300s37a-120g-internal-hard-drive/p/itmdhdk6xxd8rs8q?pid=IHDDHDK6XXD8RS8Q&amp;icmpid=reco_pp_hsame_computeraccessory_internalharddrive_1&amp;ppid=IHDDSX94PTMCSZFK" target="_blank">serious issues</a>? A few flaws notwithstanding, I convinced myself that given the cost, it was probably not a bad deal. I decided to go ahead with this.</p>
<br />
<br /><h2>The Caddy Conundrum</h2>
<br />
<br /><p>Now, I had the internal 1TB hard disk drive in my laptop which was divided into two partitions of approx equal size. One containing Windows (C:) and the other (B:) containing my <strong>super top secret stuff</strong>.<strong>​​​&nbsp;</strong>Now I cannot junk my old hard drive and live with just 120GB, can I? Nuh uh. But, I could sure live without my DVD drive which I might have used as many times as <em>Apple has invented a brand new product.</em></p>
<br />
<br /><p><em><img alt="" src="https://www.neowin.net/images/uploaded/2015/09/x2_story.jpg" style="height:440px; width:760px" /></em></p>
<br />
<br /><blockquote>
<br /><p>Shots fired.</p>
<br /></blockquote>
<br />
<br /><p>Coming back to the topic, the solution was to have my new SSD in place of the DVD drive, while fully&nbsp;reading (typo intended) the benefits of my internal HDD. But you cannot possibly&nbsp;just pull out your DVD drive and put in an SSD, can you? The solution was to get a caddy.</p>
<br />
<br /><p><img alt="" src="http://globalgolfermag.com/wp-content/uploads/2012/08/Golf-Caddy.jpg" style="height:150px; width:124px" /></p>
<br />
<br /><p>Not this one.</p>
<br />
<br /><p><img alt="" src="http://img.banggood.com/thumb/view/upload/2012/jiangjunchao/SKU069558%20(7).JPG" style="height:150px; width:150px" /></p>
<br />
<br /><p>This one.</p>
<br />
<br /><p>After an impatient wait, the caddy was delivered to my home, and I was ready to rock. I teared up the SSD and the caddy packing, rolled up my sleeves, switched on my desk lamp and switched on my engineer mode. The caddy makers were kind enough to pack in screws and a screwdriver and in no time the SSD was securely in place. Next step, I had to remove the bracket of my old DVD drive and fit in the caddy into the bracket.</p>
<br />
<br /><blockquote>
<br /><p>Plot Twist. The screws on the bracket were of a different size.</p>
<br /></blockquote>
<br />
<br /><p>I desparately tried to find my long lost screwdriver kit and ended up with just one which was too big. Got everyone from my dad to the neighbour&#39;s dog to open the bracket screws with the tools I had, no luck. The next day, a trip to the electrical store got me a new ULTRA MEGA SUPER FREAKIN 31 in 1 screwdriver kit. If this couldn&#39;t open it, I would probably have to buy a magic wand and say&nbsp;<em><strong><a href="http://harrypotter.wikia.com/wiki/Unlocking_Charm">Alohomora</a>.&nbsp;</strong></em>But it did, and saved me a trip to&nbsp;Ollivander. I snapped on the bracket onto my caddy and slotted it into my laptop. Things were proceeding smoothly.</p>
<br />
<br /><h2>Clone Wars</h2>
<br />
<br /><p>A basic search for &quot;How to migrate to a SSD&quot; gets you to this <a href="http://lifehacker.com/5837543/how-to-migrate-to-a-solid-state-drive-without-reinstalling-windows">article</a>. Nicely written, it should help you if you want to clone your&nbsp;<strong><em>entire</em></strong>&nbsp;hard drive to the SSD. I just wanted to clone the Windows (C:) partition to the SSD. My noobness about drives, partitions, volumes, EFI, UEFI and other related stuff notwithstanding, I made a new simple volume on the SSD using the Disk Management Tool (Start-&gt;Run-&gt;diskmgmt.msc), and cloned my C: drive onto the SSD. When I look back and think about this moment, all I can think is</p>
<br />
<br /><blockquote>
<br /><p>Dumbass.</p>
<br /></blockquote>
<br />
<br /><p>Feeling rather pleased with myself for successfully using a simple GUI program to clone a drive, I restarted my laptop and went into the Boot Menu (F2 -&gt; Boot) to select my SSD. The joke was on me though. No SSD in the boot device options. &quot;I should probably replace my internal hard drive with the SSD. Maybe it will boot then.&quot; I thought to myself with the surety of a veteran tech support guy. Alrighty then, I rolled up my sleeves, switched on the desk lamp and switched on my engineer mode <em>again</em>. Utilizing my newly acquired screwdriver arsenal, the cover came off, the old HDD was out and the SSD was in. Started my laptop, and not suprisingly,&nbsp;<strong><em>Boot Device Not Found</em></strong>&nbsp;flashed on my screen. Then followed 8&nbsp;hours of swapping drives, creating Windows recovery disks, reading forums, eating cake,&nbsp;and a total of 6 times I had to open up the entire machine.&nbsp;</p>
<br />
<br /><p><img alt="" src="http://i3.kym-cdn.com/entries/icons/original/000/008/012/Template_you_what_you_have_done.jpg" style="height:200px; width:200px" /><img alt="" src="http://i2.kym-cdn.com/photos/images/newsfeed/000/000/578/1234931504682.jpg" style="height:200px; width:200px" /><img alt="" src="http://i3.kym-cdn.com/photos/images/newsfeed/000/228/791/632.gif" style="height:161px; width:200px" /></p>
<br />
<br /><h2>The Solution.&nbsp;</h2>
<br />
<br /><ol>
<br />	<li>Create a recovery USB drive first.</li>
<br />	<li>Let the internal HDD be internal, and fit the SSD into the caddy.</li>
<br />	<li>Open the Disk Management Tool. Initialize your SSD with GPT. Do not initialize it with MBR.</li>
<br />	<li>Check the partitions of your HDD. There will be a partition called <strong>(Healthy)&nbsp;EFI System Partition. </strong>The first step is to clone this partition first.&nbsp;Note down its size. Mine was 260MB.</li>
<br />	<li>Your SSD should show up as&nbsp;<strong>Unallocated</strong>. Right click on it and select&nbsp;<strong>New Simple Volume</strong>. Set the size of this partition as the same as that of the&nbsp;<strong>EFI System Partition</strong>&nbsp;of your HDD. Just proceed with the default options.</li>
<br />	<li>Download <a href="http://www.todo-backup.com/products/home/free-backup-software.htm" target="_blank">EaseUS Todo Backup Free Edition</a>.</li>
<br />	<li>Open the program and click on <strong>Clone</strong>. Select the&nbsp;<strong>EFI System Partition</strong>&nbsp;as the <strong>Source</strong>. It won&#39;t be listed as that, but you can cross check how much space it occupies and select that one. For example, I chose the one with 260MB size.</li>
<br />	<li>Select your newly made partition as the&nbsp;<strong>Destination&nbsp;</strong>and make sure to&nbsp;<strong>CHECK &quot;OPTIMIZE FOR SSD&quot;</strong>&nbsp; in the lower left corner. Begin cloning.</li>
<br />	<li>Have tea.</li>
<br />	<li>Open Disk Management Tool again and create another volume from the rest of the unallocated space on the SSD. This will store your actual Windows system files.</li>
<br />	<li>Now repeating the above steps, open EaseUS Todo Backup and select your Windows partition as&nbsp;<strong>Source</strong>&nbsp;and the new unused partition on your SSD as the&nbsp;<strong>Destination. Do remember to check the &quot;Optimize for SSD&quot;&nbsp;</strong>option.</li>
<br />	<li>This might take a long time. Mine took upwards of 2 hours. Take a short nap. You deserved it.</li>
<br />	<li>Remove your internal hard drive if you can as it will make subsequent steps easier.</li>
<br />	<li>Pop in the recovery disk/USB and boot from it. You can do this by selecting it the boot device options of your BIOS.</li>
<br />	<li>Go to&nbsp;<strong>Troubleshoot -&gt; Advanced Options -&gt; Command Prompt.</strong></li>
<br />	<li>Type&nbsp;<code>C:</code></li>
<br />	<li>Type the following commands:
<br />	<ol>
<br />		<li><code>bootrec /fixmbr</code></li>
<br />		<li><code>bootrec /fixboot</code></li>
<br />		<li><code>bootrec /rebuildbcd</code></li>
<br />	</ol>
<br />	</li>
<br />	<li>You should get a success message. Turn off your computer, remove the recovery disk and you should be able to boot into the SSD now.</li>
<br />	<li>All that remains is to pop in your internal hard drive and optionally format it.</li>
<br /></ol>
<br />
<br /><h2>Phew. Time for a victory dance.</h2>
<br />
<br /><p><iframe frameborder="0" height="315" src="https://www.youtube.com/embed/BROWqjuTM0g" width="420"></iframe></p>
<br />
<br /><p>&nbsp;</p>
<br /></p>
    </div>