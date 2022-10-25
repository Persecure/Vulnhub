<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>Name</strong>: Dina: 1.0.1</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Date release</strong>: 17 Oct 2017</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Author</strong>:&nbsp;<a href="https://www.vulnhub.com/author/touhid-shaikh,465/">Touhid Shaikh</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Series</strong>:&nbsp;<a href="https://www.vulnhub.com/series/dina,128/">Dina</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dina-101,200/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dina-101,200/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to robots text and and a directory that was not indicated in robots.txt</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check the source code of a directory to find creds</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Download a backup folder from one of the directory</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload the unzipped audio file in CyberChef to find the text file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Head to secret directory and gain access from a password list</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login to the playsms interface</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use metasploit to gain a shell</li>
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

<!-- wp:image {"id":7286,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-600.png?w=1024" alt="" class="wp-image-7286"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7296,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-605.png?w=1024" alt="" class="wp-image-7296"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7288,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-601.png?w=1024" alt="" class="wp-image-7288"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7289,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-602.png?w=581" alt="" class="wp-image-7289"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/nothing source code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7291,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-603.png?w=680" alt="" class="wp-image-7291"/><figcaption class="wp-element-caption">Found a password list</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/secure</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7293,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-604.png?w=1024" alt="" class="wp-image-7293"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unzip the file with the password list and a mp3 file is given.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7297,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-606.png?w=411" alt="" class="wp-image-7297"/><figcaption class="wp-element-caption">It is actually a text file.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef to read the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7299,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-607.png?w=954" alt="" class="wp-image-7299"/><figcaption class="wp-element-caption">Found some clues.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now we found an interface.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7301,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-608.png?w=1024" alt="" class="wp-image-7301"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the password list again gain access.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7303,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-609.png?w=1024" alt="" class="wp-image-7303"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>There are some exploits found on metasploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7346,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-625.png?w=1024" alt="" class="wp-image-7346"/><figcaption class="wp-element-caption">Let's use the third exploit.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Set up the necessary options.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7345,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-624.png?w=1024" alt="" class="wp-image-7345"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the exploit and a shell will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7348,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-626.png?w=1024" alt="" class="wp-image-7348"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check for sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7350,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-627.png?w=842" alt="" class="wp-image-7350"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use GTFOBins to find for a perl sudo exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7351,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-628.png?w=848" alt="" class="wp-image-7351"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root access is gained and flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7353,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-629.png?w=722" alt="" class="wp-image-7353"/></figure>
<!-- /wp:image -->
