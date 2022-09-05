<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/sunset-dawn,341/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/sunset-dawn,341/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>From enumeration SMB servers can be found</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SMB enumeration</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Look at the log files on the web server for clues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit a cronjob to gain access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use linpeas to find for interesting flies</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Privilege access can be gained from exploiting binaries</li>
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

<!-- wp:image {"id":4232,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-105.png?w=598" alt="" class="wp-image-4232"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4234,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-106.png?w=1013" alt="" class="wp-image-4234"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4235,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-107.png?w=814" alt="" class="wp-image-4235"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4237,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-108.png?w=1024" alt="" class="wp-image-4237"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4241,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-110.png?w=1024" alt="" class="wp-image-4241"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/logs/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4240,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-109.png?w=571" alt="" class="wp-image-4240"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to gain access to the log files besides management.log</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The management logs shows us some kind of cron job with two particular files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4262,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-120.png?w=683" alt="" class="wp-image-4262"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's enumerate SMB</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4249,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-114.png?w=632" alt="" class="wp-image-4249"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4250,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-115.png?w=1024" alt="" class="wp-image-4250"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4252,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-116.png?w=796" alt="" class="wp-image-4252"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4254,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-117.png?w=1024" alt="" class="wp-image-4254"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4255,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-118.png?w=787" alt="" class="wp-image-4255"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4257,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-119.png?w=1024" alt="" class="wp-image-4257"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The SMB shares are empty but we are able to put files in them. Let's create the same files found on the management log and put a bash shell in them.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4264,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-121.png?w=543" alt="" class="wp-image-4264"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Place the file in the smb share and start nc.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4265,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-122.png?w=951" alt="" class="wp-image-4265"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4266,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-123.png?w=842" alt="" class="wp-image-4266"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checking sudo permisions we are able to run sudo.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4270,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-125.png?w=838" alt="" class="wp-image-4270"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>However using by just switching to root user we get a warning message.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4271,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-126.png?w=696" alt="" class="wp-image-4271"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check linpeas for more clues.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4268,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-124.png?w=831" alt="" class="wp-image-4268"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4273,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-127.png?w=1024" alt="" class="wp-image-4273"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4275,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-128.png?w=880" alt="" class="wp-image-4275"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Fro GTFOBins we can get shell.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Root access is gained and final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4276,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-129.png?w=1024" alt="" class="wp-image-4276"/></figure>
<!-- /wp:image -->
