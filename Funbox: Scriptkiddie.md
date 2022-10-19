<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/funbox-scriptkiddie,725/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/funbox-scriptkiddie,725/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to an old version of FTP server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the metasploit ftp server exploit to gain root access</li>
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

<!-- wp:image {"id":6938,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-446.png?w=692" alt="" class="wp-image-6938"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6940,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-447.png?w=692" alt="" class="wp-image-6940"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6941,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-448.png?w=1024" alt="" class="wp-image-6941"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Set the etc/hosts to funbox11.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6942,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-449.png?w=1024" alt="" class="wp-image-6942"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The website is under Wordpress.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6943,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-450.png?w=1024" alt="" class="wp-image-6943"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use WPscan to enumerate more information.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6945,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-451.png?w=814" alt="" class="wp-image-6945"/><figcaption class="wp-element-caption">Found the admin user but unable to bruteforce the password.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the nmap scan we can see a FTP server that has an old version of Proftpd. Learch search an exploit on it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6946,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-452.png?w=1024" alt="" class="wp-image-6946"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start up metasploit and search for the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6948,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-453.png?w=1024" alt="" class="wp-image-6948"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Set the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6949,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-454.png?w=1024" alt="" class="wp-image-6949"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6951,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-455.png?w=1024" alt="" class="wp-image-6951"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Root user will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6952,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-456.png?w=1024" alt="" class="wp-image-6952"/></figure>
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
<p>The final flag will be in the root folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6954,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-457.png?w=1024" alt="" class="wp-image-6954"/></figure>
<!-- /wp:image -->
