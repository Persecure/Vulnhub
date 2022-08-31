<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/funbox-easy,526/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/funbox-easy,526/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Enumeration gives us multiple pathways</li><li>Use default credentials to gain access to an online bookstore</li><li>Add a book that has a php reverse shell attached</li><li>Once user access is gained , a password file is stored in the open</li><li>SSH to the user and check for sudo permissions.</li><li>Use GTFOBins to find for a root exploit</li></ul>
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

<!-- wp:image {"id":3935,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-689.png?w=779" alt="" class="wp-image-3935"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3936,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-690.png?w=1024" alt="" class="wp-image-3936"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3938,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-691.png?w=1024" alt="" class="wp-image-3938"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3950,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-698.png?w=1024" alt="" class="wp-image-3950"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3943,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-694.png?w=604" alt="" class="wp-image-3943"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/gym/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3945,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-695.png?w=1024" alt="" class="wp-image-3945"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a clue on the contact page of the gym site.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3946,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-696.png?w=1024" alt="" class="wp-image-3946"/><figcaption class="wp-element-caption">Since it is created with LAMP it is a linux machine.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/secret/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3948,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-697.png?w=893" alt="" class="wp-image-3948"/></figure>
<!-- /wp:image -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:paragraph -->
<p>/admin/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3940,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-692.png?w=1024" alt="" class="wp-image-3940"/><figcaption class="wp-element-caption">Small CRM Projects</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check searchsploit for any exploits.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3951,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-699.png?w=687" alt="" class="wp-image-3951"/></figure>
<!-- /wp:image --></div>
<!-- /wp:group -->

<!-- wp:paragraph -->
<p><em>"Small CRM 3.0 is vulnerable to SQL Injection on it's admin login because of insufficient user supplied data sanitization and the sql injection payload being executed. Attacker is able to acious payload, successfully taking over admin account."</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3953,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-700.png?w=1024" alt="" class="wp-image-3953"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>Enter the following payload in 'Username' and 'Password' parameter: ' OR 'x'='x</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3954,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-701.png?w=1024" alt="" class="wp-image-3954"/><figcaption class="wp-element-caption">CRM access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some enumeration there's isn't much we can do.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The online bookstore has a admin login page.</p>
<!-- /wp:paragraph -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:paragraph -->
<p>/store/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3942,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-693.png?w=1024" alt="" class="wp-image-3942"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried default creds like admin : admin and access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3959,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-704.png?w=1024" alt="" class="wp-image-3959"/></figure>
<!-- /wp:image --></div>
<!-- /wp:group -->

<!-- wp:image {"id":3956,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-702.png?w=1024" alt="" class="wp-image-3956"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Create a new book and upload a php reverse shell in the image then click on the book to activate the reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3961,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-705.png?w=1024" alt="" class="wp-image-3961"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3962,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-706.png?w=1024" alt="" class="wp-image-3962"/><figcaption class="wp-element-caption">User access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We find some passwords in a file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3964,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-707.png?w=507" alt="" class="wp-image-3964"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>SSH to the tony user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3966,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-708.png?w=808" alt="" class="wp-image-3966"/><figcaption class="wp-element-caption">Tony access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Check sudo -l for priveledges.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3968,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-709.png?w=1024" alt="" class="wp-image-3968"/><figcaption class="wp-element-caption">We can use time to get a root access.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3969,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-710.png?w=823" alt="" class="wp-image-3969"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3971,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-711.png?w=751" alt="" class="wp-image-3971"/></figure>
<!-- /wp:image -->
