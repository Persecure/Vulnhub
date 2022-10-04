<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/funbox-1,518/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/funbox-1,518/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a WordPress site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use WPscan to enumerate for users and passwords</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Same credentials are used for the other services</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Escape the restricted shell with SSH</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a cronjob script and add a python reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Rabbit hole : Two users are executing the cronjob script including root user. </li>
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

<!-- wp:image {"id":6038,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-84.png?w=792" alt="" class="wp-image-6038"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6039,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-85.png?w=1024" alt="" class="wp-image-6039"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6040,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-86.png?w=1024" alt="" class="wp-image-6040"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6046,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-89.png?w=1024" alt="" class="wp-image-6046"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6044,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-88.png?w=555" alt="" class="wp-image-6044"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/secrets</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6047,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-90.png?w=542" alt="" class="wp-image-6047"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Used WPscan to enumerate users and bruteforce users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6049,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-91.png?w=810" alt="" class="wp-image-6049"/><figcaption class="wp-element-caption">Found two users with passwords joe:12345 &amp; admin:iubire</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Login to WP as admin.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6051,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-92.png?w=1024" alt="" class="wp-image-6051"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I'm unable to upload any reverse shell plugins. Since I got the user Joe and the password I can check if its the same passwords for the SSH and FTP service.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6054,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-93.png?w=898" alt="" class="wp-image-6054"/><figcaption class="wp-element-caption">Looks like its the same for both services.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Joe access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6132,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-125.png?w=461" alt="" class="wp-image-6132"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>However the shell is restricted. We can use the following method to by the restricted shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6136,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-128.png?w=797" alt="" class="wp-image-6136"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a inbox for joe.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6143,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-132.png?w=1024" alt="" class="wp-image-6143"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We find another user called funny and the user has a hidden script that runs uploads a backup. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6139,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-130.png?w=1024" alt="" class="wp-image-6139"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's try to add a python reverses hell into the script and start a netcat listener. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6137,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-129.png?w=975" alt="" class="wp-image-6137"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Funny user access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6141,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-131.png?w=1024" alt="" class="wp-image-6141"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>However I couldn't find any method for privilege escalation. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In Joe's inbox the first message is from the root user stating the backup script is completed. The root user could potentially run the script too.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I tried to run another netcat listener after and we got the root user. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6145,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-133.png?w=832" alt="" class="wp-image-6145"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checked the crontab and indeed the root user runs the backup script. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6147,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-134.png?w=882" alt="" class="wp-image-6147"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6148,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-135.png?w=405" alt="" class="wp-image-6148"/></figure>
<!-- /wp:image -->
