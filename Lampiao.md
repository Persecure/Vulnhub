<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/lampiao-1,249/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/lampiao-1,249/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Run a full port scan to find for uncommon ports</li><li>Gobuster enumeration gives clues on framework name and version</li><li>Searchsploit drupal to find for exploits</li><li>Use metasploit to gain user access</li><li>Enumerate file to find for databases clues </li><li>Hash cracking takes time and find an alternate method to exploit</li><li>Use linux exploit (Linux Kernel 2.6.22 &lt; 3.9 - 'Dirty COW)</li></ul>
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

<!-- wp:image {"id":3876,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-660.png?w=774" alt="" class="wp-image-3876"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3877,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-661.png?w=1024" alt="" class="wp-image-3877"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3879,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-662.png?w=718" alt="" class="wp-image-3879"/><figcaption class="wp-element-caption">port 80</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3880,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-663.png?w=1024" alt="" class="wp-image-3880"/><figcaption class="wp-element-caption">port 1898</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3882,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-664.png?w=1024" alt="" class="wp-image-3882"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>robots.txt has some clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3883,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-665.png?w=906" alt="" class="wp-image-3883"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3884,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-666.png?w=803" alt="" class="wp-image-3884"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the profiles folder we can find the version number in one of the files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3886,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-667.png?w=623" alt="" class="wp-image-3886"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3888,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-668.png?w=606" alt="" class="wp-image-3888"/><figcaption class="wp-element-caption">Drupal version 7.54</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a searchsploit on the Drupal version.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3890,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-669.png?w=958" alt="" class="wp-image-3890"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start up metasploit</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3891,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-670.png?w=1024" alt="" class="wp-image-3891"/><figcaption class="wp-element-caption">Search for the exploit , input the options and run.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A meterpreter session is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3893,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-671.png?w=968" alt="" class="wp-image-3893"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3897,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-673.png?w=761" alt="" class="wp-image-3897"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Enumerating the folders , we can find some database credentials in /var/www/html/sites/default/settings.php</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3895,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-672.png?w=448" alt="" class="wp-image-3895"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use mysqldump to find a hash for tiago</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>mysqldump -u drupaluser -pVirgulino drupal users</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3898,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-674.png?w=1024" alt="" class="wp-image-3898"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to crack the hash but it was going to take hours.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3900,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-675.png?w=726" alt="" class="wp-image-3900"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:paragraph -->
<p>Let's search for another method.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>After some searching online, found an exploit <a href="https://www.exploit-db.com/exploits/40847" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3902,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-676.png?w=1024" alt="" class="wp-image-3902"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Download the exploit , start a python server and pass the exploit to the machine via the /tmp folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3904,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-677.png?w=820" alt="" class="wp-image-3904"/><figcaption class="wp-element-caption">Use the compiling instruction from the exploit db.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>This exploit changes the root password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3906,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-678.png?w=362" alt="" class="wp-image-3906"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ssh into the root terminal with the new password and the root flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3908,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-679.png?w=1024" alt="" class="wp-image-3908"/></figure>
<!-- /wp:image --></div>
<!-- /wp:group -->
