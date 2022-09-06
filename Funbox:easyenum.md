<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/funbox-easyenum,565/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/funbox-easyenum,565/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Run directory enumeration tools to find for clues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload reverse shells to gain access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bruteforce users</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check binary exploits</li>
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

<!-- wp:image {"id":4309,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-138.png?w=831" alt="" class="wp-image-4309"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4310,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-139.png?w=1024" alt="" class="wp-image-4310"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4316,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-142.png?w=1024" alt="" class="wp-image-4316"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4312,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-140.png?w=537" alt="" class="wp-image-4312"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>secret/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4322,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-146.png?w=581" alt="" class="wp-image-4322"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>mini.php/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4314,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-141.png?w=1024" alt="" class="wp-image-4314"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In this mini shell we are able to upload files. Let's upload a php reverse shell and execute it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4319,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-144.png?w=757" alt="" class="wp-image-4319"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4317,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-143.png?w=1024" alt="" class="wp-image-4317"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the home directory there are the following users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4320,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-145.png?w=578" alt="" class="wp-image-4320"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use hydra to bruteforce the goat user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4324,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-147.png?w=980" alt="" class="wp-image-4324"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now we have a user access with a better shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4325,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-148.png?w=665" alt="" class="wp-image-4325"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checking sudo permissons.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4327,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-149.png?w=1024" alt="" class="wp-image-4327"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4328,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-150.png?w=842" alt="" class="wp-image-4328"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>root access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4330,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-151.png?w=507" alt="" class="wp-image-4330"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4331,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-152.png?w=799" alt="" class="wp-image-4331"/></figure>
<!-- /wp:image -->
