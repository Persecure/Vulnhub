<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/vegeta-1,501/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/vegeta-1,501/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Enumeration uncovers hidden directories </li><li>Check all the way to the bottom for clues</li><li>Decode file and look out for double encoding</li><li>Use a more through enumeration if stuck</li><li>Decode a morse code to find for clues</li><li>Check bash_histroy to find for clues</li></ul>
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

<!-- wp:image {"id":3820,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-634.png?w=893" alt="" class="wp-image-3820"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3821,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-635.png?w=1024" alt="" class="wp-image-3821"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3825,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-638.png?w=1024" alt="" class="wp-image-3825"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3822,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-636.png?w=518" alt="" class="wp-image-3822"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3824,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-637.png?w=627" alt="" class="wp-image-3824"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check the source and a base64 code is found right at the bottom.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3827,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-639.png?w=1024" alt="" class="wp-image-3827"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef and decode it twice as it is double encoded.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3829,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-640.png?w=1024" alt="" class="wp-image-3829"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Save the output image.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3831,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-641.png?w=296" alt="" class="wp-image-3831"/><figcaption class="wp-element-caption">It's a QR code.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Decode the QR code and we have a password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3833,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-642.png?w=799" alt="" class="wp-image-3833"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We have a password but no user. Let's use a more thorough enumeration with Seclists</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3838,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-645.png?w=1024" alt="" class="wp-image-3838"/><figcaption class="wp-element-caption">Found an additional directory.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3840,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-646.png?w=546" alt="" class="wp-image-3840"/><figcaption class="wp-element-caption">Contains a .wav file.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3835,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-643.png?w=769" alt="" class="wp-image-3835"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It is in morse code , let's use an online morse code decoder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3837,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-644.png?w=813" alt="" class="wp-image-3837"/><figcaption class="wp-element-caption">Found a user and password</figcaption></figure>
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

<!-- wp:image {"id":3842,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-647.png?w=827" alt="" class="wp-image-3842"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:paragraph -->
<p>Check the folder history.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3844,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-649.png?w=865" alt="" class="wp-image-3844"/><figcaption class="wp-element-caption">bash_history shows a password and a user name Tom. However Tom does not exsist.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3846,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-650.png?w=946" alt="" class="wp-image-3846"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use the same command in the file and add a Tom user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3847,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-651.png?w=923" alt="" class="wp-image-3847"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch user and root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3849,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-652.png?w=1024" alt="" class="wp-image-3849"/></figure>
<!-- /wp:image --></div>
<!-- /wp:group -->
