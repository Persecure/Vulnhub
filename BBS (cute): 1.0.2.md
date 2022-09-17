<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/bbs-cute-102,567/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/bbs-cute-102,567/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumerataton will lead to a CuteNews interface</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Register a new user and upload a reverse shell in the Avatar</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Change the reverse shell format to a GIF format for it to bypass upload error</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check sudo permission </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use GTFOBins to find exploit for root access</li>
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

<!-- wp:image {"id":4819,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-364.png?w=688" alt="" class="wp-image-4819"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4820,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-365.png?w=1024" alt="" class="wp-image-4820"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4821,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-366.png?w=1024" alt="" class="wp-image-4821"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 88</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4823,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-367.png?w=1016" alt="" class="wp-image-4823"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4824,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-368.png?w=1024" alt="" class="wp-image-4824"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>index.php</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We find  CuteNews interface.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4826,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-369.png?w=1024" alt="" class="wp-image-4826"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's register a new user , for the Captcha code we can use /captcha.php to find one.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4828,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-370.png?w=1001" alt="" class="wp-image-4828"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4842,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-380.png?w=670" alt="" class="wp-image-4842"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the profile section of the interface we are able to upload an avatar. However only a GIF format can be uploaded. We create a php revershell and add the GIF magic number on the top of the source code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4829,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-371.png?w=708" alt="" class="wp-image-4829"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload is a success.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4830,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-372.png?w=1024" alt="" class="wp-image-4830"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I tried finding the upload link by right clicking on the broken avatar pic.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4832,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-373.png?w=601" alt="" class="wp-image-4832"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I edited the link for my victim box as shown below.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4833,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-374.png?w=531" alt="" class="wp-image-4833"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Remember to start a netcat listener before executing the upload link and you will get a shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4834,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-375.png?w=1024" alt="" class="wp-image-4834"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>First flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4835,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-376.png?w=497" alt="" class="wp-image-4835"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checking sudo permissions we are allowed to run hping3</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4837,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-377.png?w=1024" alt="" class="wp-image-4837"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Search GTFOBins for the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4840,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-379.png?w=939" alt="" class="wp-image-4840"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Able to view the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4839,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-378.png?w=1024" alt="" class="wp-image-4839"/></figure>
<!-- /wp:image -->
