<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/my-cmsms-1,498/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/my-cmsms-1,498/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>@_p4nk4j</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will indicate a CMS interface with mysql servers</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use default credentials to check for access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find password hash in database and update </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login to the CMS interface with the newly updated password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find for interface exploits and upload a reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find for hidden user credentials and decode it</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check for sudo permissions to gain privilege access</li>
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

<!-- wp:image {"id":5754,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-708.png?w=668" alt="" class="wp-image-5754"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5755,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-709.png?w=1024" alt="" class="wp-image-5755"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5756,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-710.png?w=1024" alt="" class="wp-image-5756"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5759,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-712.png?w=358" alt="" class="wp-image-5759"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5758,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-711.png?w=1024" alt="" class="wp-image-5758"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/admin</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5760,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-713.png?w=484" alt="" class="wp-image-5760"/><figcaption class="wp-element-caption">default credentials do not work.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/phpmyadmin</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5762,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-714.png?w=1024" alt="" class="wp-image-5762"/><figcaption class="wp-element-caption">Same with the php admin page.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's try enumerating the SQL server.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We start with logging on to the MYSQL server with default creds of root:root</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5765,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-715.png?w=1023" alt="" class="wp-image-5765"/><figcaption class="wp-element-caption">accessed gained</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>View databases</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5767,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-716.png?w=399" alt="" class="wp-image-5767"/><figcaption class="wp-element-caption">Let's use the application db</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>View tables</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5768,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-717.png?w=489" alt="" class="wp-image-5768"/><figcaption class="wp-element-caption">use cms_users</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5770,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-718.png?w=831" alt="" class="wp-image-5770"/><figcaption class="wp-element-caption">Let's search for username , password and email</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5772,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-719.png?w=850" alt="" class="wp-image-5772"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a hash password but I'm unable to crack the hash. Let's see if we can edit the password section in the server.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> After some googling , I found a MYSQL query to update a new password hash:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>update cms_users set password = (select md5(CONCAT(IFNULL((SELECT sitepref_value FROM cms_siteprefs WHERE sitepref_name = 'sitemask'),''),'persecure'))) where username = 'admin';</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5774,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-720.png?w=1024" alt="" class="wp-image-5774"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I found an exploit for the 2.4.14 version of CMS MS. But it doesn't seem to work.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5779,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-722.png?w=1024" alt="" class="wp-image-5779"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's login to CMS MS admin with the new password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5777,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-721.png?w=1024" alt="" class="wp-image-5777"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found an exploit is exploit.db</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5784,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-725.png?w=1024" alt="" class="wp-image-5784"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5785,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-726.png?w=1024" alt="" class="wp-image-5785"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload a PHP reverse shell and change the extension to .phtml and start a netcat listener.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Click on the newly uploaded file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5789,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-728.png?w=1024" alt="" class="wp-image-5789"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5787,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-727.png?w=1024" alt="" class="wp-image-5787"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5791,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-729.png?w=1024" alt="" class="wp-image-5791"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a hash password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5792,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-730.png?w=692" alt="" class="wp-image-5792"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Used cyberchef to crack the hash. The hash is double encoded. Base64 &amp; Base85.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5794,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-731.png?w=1024" alt="" class="wp-image-5794"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>armour:Shield@123</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Switch to the armour user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5798,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-732.png?w=756" alt="" class="wp-image-5798"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>check for sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5799,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-733.png?w=994" alt="" class="wp-image-5799"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We are able to use python to gain a root shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5801,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-734.png?w=862" alt="" class="wp-image-5801"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5802,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-735.png?w=717" alt="" class="wp-image-5802"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5804,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-736.png?w=1024" alt="" class="wp-image-5804"/></figure>
<!-- /wp:image -->
