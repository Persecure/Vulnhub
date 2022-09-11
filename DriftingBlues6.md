<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/driftingblues-6,672/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/driftingblues-6,672/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Thorough enumeration is needed</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Crack a zip file with John to get some creds</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login into the textpattern interface</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload a revershell shell to gain user access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the dirty exploit for root access</li>
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

<!-- wp:image {"id":4578,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-262.png?w=661" alt="" class="wp-image-4578"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4581,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-264.png?w=1024" alt="" class="wp-image-4581"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4579,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-263.png?w=1024" alt="" class="wp-image-4579"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt , /robots</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4584,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-266.png?w=477" alt="" class="wp-image-4584"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/textpattern/textpattern</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4590,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-269.png?w=1024" alt="" class="wp-image-4590"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/spammer gives us a zip file</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4583,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-265.png?w=507" alt="" class="wp-image-4583"/><figcaption class="wp-element-caption">However it is password protected</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's crack the password for the zip protected file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4586,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-267.png?w=1024" alt="" class="wp-image-4586"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the credentionals.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4588,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-268.png?w=312" alt="" class="wp-image-4588"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Login via text pattern</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4591,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-270.png?w=1024" alt="" class="wp-image-4591"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>From textpattern interface we are able to upload files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4594,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-272.png?w=1024" alt="" class="wp-image-4594"/><figcaption class="wp-element-caption">Uploaded a php reverse shell</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I run gobuster on /textpattern to find a directory to run the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4592,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-271.png?w=1024" alt="" class="wp-image-4592"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4596,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-273.png?w=811" alt="" class="wp-image-4596"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Gained a user shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4597,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-274.png?w=806" alt="" class="wp-image-4597"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried searching for setuid binaries and sudo permissions but unable to find any.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>However the Linux kernel is outdated and exploitable.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4599,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-275.png?w=771" alt="" class="wp-image-4599"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the dirtycow exploit found <a href="https://www.exploit-db.com/exploits/40839" data-type="URL" data-id="https://www.exploit-db.com/exploits/40839" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Upload the exploit to the victim machine and read the exploit to find the method to compile the program.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Then run the program. The exploit will create a user with root privelideges.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4601,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-276.png?w=762" alt="" class="wp-image-4601"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4602,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-277.png?w=638" alt="" class="wp-image-4602"/></figure>
<!-- /wp:image -->
