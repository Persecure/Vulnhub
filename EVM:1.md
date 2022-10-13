<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/evm-1,391/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/evm-1,391/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Directory enumeration will lead to a wordpress site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>WPScan the site to gain creds</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use metasploit to gian wp admin access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Search for hidden files to find the password for the root user</li>
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

<!-- wp:image {"id":6626,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-303.png?w=704" alt="" class="wp-image-6626"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6627,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-304.png?w=1024" alt="" class="wp-image-6627"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6628,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-305.png?w=1024" alt="" class="wp-image-6628"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6630,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-306.png?w=1024" alt="" class="wp-image-6630"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to load the wordpress site.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's use WPscan to enumerate.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6634,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-309.png?w=783" alt="" class="wp-image-6634"/><figcaption class="wp-element-caption">Username: c0rrupt3d_brain, Password: 24992499</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since I cant load the WordPress site I'll use metasploit to see if I can gain access. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Set up the options.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6636,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-310.png?w=1024" alt="" class="wp-image-6636"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6637,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-311.png?w=1024" alt="" class="wp-image-6637"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the home folder and check the directory. Search for hidden files and there will be the root password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6639,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-312.png?w=905" alt="" class="wp-image-6639"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6641,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-313.png?w=677" alt="" class="wp-image-6641"/></figure>
<!-- /wp:image -->
