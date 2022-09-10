<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dc-1,292/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dc-1,292/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a vulnerable Drupal 7 server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use metasploit to find an exploit</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find setuid binaries </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Get setuid binaries exploit from GTFOBins</li>
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

<!-- wp:image {"id":4517,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-235.png?w=698" alt="" class="wp-image-4517"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4518,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-236.png?w=750" alt="" class="wp-image-4518"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4520,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-237.png?w=1024" alt="" class="wp-image-4520"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>robots.txt gives us a long list.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4522,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-238.png?w=653" alt="" class="wp-image-4522"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some time exploring the robots.txt folders , I am unable to find anymore clues.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>From the Nmap scan we know that Drupal is running version 7. Use searchsploit to find for exploits.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4529,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-241.png?w=867" alt="" class="wp-image-4529"/><figcaption class="wp-element-caption">We can check metasploit for the exploit.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4531,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-242.png?w=1024" alt="" class="wp-image-4531"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Set up the options and run the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4533,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-243.png?w=1024" alt="" class="wp-image-4533"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A meteprepeter shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4535,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-244.png?w=1024" alt="" class="wp-image-4535"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>First flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4527,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-240.png?w=545" alt="" class="wp-image-4527"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found another flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4526,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-239.png?w=672" alt="" class="wp-image-4526"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's check for setuid binaries.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4537,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-245.png?w=614" alt="" class="wp-image-4537"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use this exploit from GTFObins.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4538,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-246.png?w=890" alt="" class="wp-image-4538"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4540,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-247.png?w=761" alt="" class="wp-image-4540"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4541,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-248.png?w=657" alt="" class="wp-image-4541"/></figure>
<!-- /wp:image -->
