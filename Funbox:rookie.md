<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/funbox-rookie,520/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/funbox-rookie,520/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>FTP server allows anonymous login</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use John to crack each zipfile</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Able to crack 2 users with private keys.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Only one of the user can be accessed</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Search hidden history files to find for clues</li>
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

<!-- wp:image {"id":3982,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image.png?w=714" alt="" class="wp-image-3982"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3983,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-1.png?w=1024" alt="" class="wp-image-3983"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3985,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-2.png?w=566" alt="" class="wp-image-3985"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/logs/ gives us not found.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>FTP login</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3986,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-3.png?w=681" alt="" class="wp-image-3986"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found some clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3988,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-4.png?w=473" alt="" class="wp-image-3988"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3989,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-5.png?w=1024" alt="" class="wp-image-3989"/><figcaption class="wp-element-caption">A base64 code that is same as the @users msg</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use john to crack the zip files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3991,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-6.png?w=896" alt="" class="wp-image-3991"/><figcaption class="wp-element-caption">Only two users can be cracked.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The zip files contain the private keys.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We are able to gain access via the rsa key to the tom user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3993,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-7.png?w=694" alt="" class="wp-image-3993"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We have a restricted shell , let's use a python shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3995,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-8.png?w=706" alt="" class="wp-image-3995"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Look through the folder and search the history files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3997,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-9.png?w=687" alt="" class="wp-image-3997"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to find a password in the mysql_history</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3999,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-10.png?w=548" alt="" class="wp-image-3999"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permisiions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4000,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-11.png?w=1024" alt="" class="wp-image-4000"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Since we can run all sudo commands we can just switch to the root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4002,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-12.png?w=377" alt="" class="wp-image-4002"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4004,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-13.png?w=748" alt="" class="wp-image-4004"/></figure>
<!-- /wp:image -->
