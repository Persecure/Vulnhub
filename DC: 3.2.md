<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>Name</strong>: DC: 3.2</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Date release</strong>: 25 Apr 2020</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Author</strong>:&nbsp;<a href="https://www.vulnhub.com/author/dcau,610/">DCAU</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Series</strong>:&nbsp;<a href="https://www.vulnhub.com/series/dc,199/">DC</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Web page</strong>:&nbsp;<a href="http://www.five86.com/dc-3.html">http://www.five86.com/dc-3.html</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dc-32,312/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dc-32,312/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a joomla! CMS system</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use joomscan for enumeration</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>The joomla version will lead to a SQL exploit on searchsploit</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Read the searchspoilt file and use the SQLmap scipt to get a hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use john to crack the hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Enter the administrator section of the joomla system and add a PHP reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use google to find an exploit for the outdated kernel </li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"luminous-vivid-amber","fontSize":"small"} -->
<p class="has-text-align-center has-luminous-vivid-amber-background-color has-background has-small-font-size"><strong>Enumeration</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Run nmap scan to find for open ports.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7585,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image.png?w=953" alt="" class="wp-image-7585"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7587,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-2.png?w=1024" alt="" class="wp-image-7587"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7586,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-1.png?w=1024" alt="" class="wp-image-7586"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After enumerating the other pages I couldn't find anything useful. From the Nmap scan we know the machine has a joomla! cms system. I use the JoomScan tool to find the exact version of the system.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7589,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-3.png?w=673" alt="" class="wp-image-7589"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It uses 3.7.0 version.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I searched searchsploit for this version and found a potential exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7590,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-4.png?w=681" alt="" class="wp-image-7590"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Reading the exploit the author gave us a Sqlmap script to use. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7591,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-5.png?w=1024" alt="" class="wp-image-7591"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sqlmap -u "http://192.168.18.9/index.php?option=com_fields&amp;view=fields&amp;layout=modal&amp;list&#91;fullordering]=updatexml" --risk=3 --level=5 --random-agent --dbs -p list&#91;fullordering]</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Found some MySQL databases.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7593,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-6.png?w=731" alt="" class="wp-image-7593"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I redid the scan again but this time I dumped out the entire database.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sqlmap -u "http://192.168.18.9/index.php?option=com_fields&amp;view=fields&amp;layout=modal&amp;list&#91;fullordering]=updatexml" --risk=3 --level=5 --random-agent --dump</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>It was taking too long and I edited the scritp to get user info.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sqlmap -u "http://192.168.18.9/index.php?option=com_fields&amp;view=fields&amp;layout=modal&amp;list&#91;fullordering]=update.xml"-p list&#91;fullordering] -D joomladb -T '#__users' -C id,username,password --dump</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Found a hash for the admin user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7597,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-7.png?w=794" alt="" class="wp-image-7597"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use john to crack the hash.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7599,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-8.png?w=919" alt="" class="wp-image-7599"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use this password to login to the admin account in the administrator page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7602,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-10.png?w=1024" alt="" class="wp-image-7602"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the templates customize section and edit the component.php file to a php reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7605,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-12.png?w=1024" alt="" class="wp-image-7605"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Navigate to the page /template/protostar/component.php</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A reverse shell will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7606,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-13.png?w=1001" alt="" class="wp-image-7606"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some time enumerating, I use linpeas to find for more clues. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7611,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-16.png?w=931" alt="" class="wp-image-7611"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The kernel looks exploitable. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>After exploring exploits in google I came across a potential exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.exploit-db.com/exploits/39772" target="_blank" rel="noreferrer noopener">https://www.exploit-db.com/exploits/39772</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7608,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-14.png?w=1024" alt="" class="wp-image-7608"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The exploit requires us to download a zipfile.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7609,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-15.png?w=965" alt="" class="wp-image-7609"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I downloaded to my local machine and hand it over to the box using a python server.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Unzip the file and run the compile bash script in one of the folders. The exploited will be generated.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>When you run the exploit. Root shell will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7612,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-17.png?w=939" alt="" class="wp-image-7612"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7613,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/11/image-18.png?w=796" alt="" class="wp-image-7613"/></figure>
<!-- /wp:image -->
