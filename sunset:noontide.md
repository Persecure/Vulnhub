<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/sunset-noontide,531/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/sunset-noontide,531/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will state an exploitable IRC server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>UNREAL IRC is a very common exploitable server </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use metasploit</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Do not overthink for privileged escalation</li>
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

<!-- wp:image {"id":4069,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-34.png?w=742" alt="" class="wp-image-4069"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4070,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-35.png?w=1024" alt="" class="wp-image-4070"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4071,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-36.png?w=732" alt="" class="wp-image-4071"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4075,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-38.png?w=1024" alt="" class="wp-image-4075"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4073,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-37.png?w=741" alt="" class="wp-image-4073"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>From the nmap scan and scripts results we notice the machine has a UNREAL IRC server.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> Let's check searchsploit for any exploits.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4077,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-39.png?w=593" alt="" class="wp-image-4077"/><figcaption class="wp-element-caption">Metasploit has a backdoor CE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start up metasploit and search for the moduel</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4079,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-40.png?w=1024" alt="" class="wp-image-4079"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A session is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4080,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-41.png?w=1024" alt="" class="wp-image-4080"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Gain a python shell</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4082,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-42.png?w=614" alt="" class="wp-image-4082"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4083,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-43.png?w=558" alt="" class="wp-image-4083"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4085,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-44.png?w=415" alt="" class="wp-image-4085"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After trying LinPeas and Linux kernel exploits , the machine box description states to not overthing.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try to use su to root with the same password.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Accessed gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4087,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-45.png?w=494" alt="" class="wp-image-4087"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4088,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-46.png?w=627" alt="" class="wp-image-4088"/></figure>
<!-- /wp:image -->
