<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/born2root-1,197/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/born2root-1,197/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a hidden private key</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Explore the cron jobs and create a reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Brute forcing is the key to gain root access</li>
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

<!-- wp:image {"id":6276,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-174.png?w=657" alt="" class="wp-image-6276"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6277,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-175.png?w=711" alt="" class="wp-image-6277"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6278,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-176.png?w=1024" alt="" class="wp-image-6278"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6279,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-177.png?w=867" alt="" class="wp-image-6279"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6281,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-178.png?w=517" alt="" class="wp-image-6281"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/wordpress-blog</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6283,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-179.png?w=1024" alt="" class="wp-image-6283"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/ icons</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6285,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-180.png?w=791" alt="" class="wp-image-6285"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a RSA key.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6287,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-181.png?w=692" alt="" class="wp-image-6287"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the private key to SSH into the 3 users found on the homepage. It is a key for martin.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6289,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-182.png?w=819" alt="" class="wp-image-6289"/><figcaption class="wp-element-caption">Once login we need a password and I guessed the password as password.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some enumeration , found a cron job.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6292,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-184.png?w=1024" alt="" class="wp-image-6292"/><figcaption class="wp-element-caption">The user jimmy executes a python script every 5 mins but the file has not been created.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's create the exact file but with a python reverse shell inside.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6294,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-185.png?w=673" alt="" class="wp-image-6294"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start up netcat listener and wait for the connection.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6297,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-187.png?w=775" alt="" class="wp-image-6297"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After a long time enumerating , I'm unable to find any clues. I resorted to bruteforcing the last user.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Once we enter to the user hadi we are just able to switch user into root.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6299,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-188.png?w=1024" alt="" class="wp-image-6299"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6300,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-189.png?w=1024" alt="" class="wp-image-6300"/></figure>
<!-- /wp:image -->
