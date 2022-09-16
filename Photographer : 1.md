<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/photographer-1,519/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/photographer-1,519/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Full enumeration will show two webservers</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Port 8000 webserver runs under the Koken CMS</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find exploit for Koken CMS on Exploit DB</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Craft a php reverse shell payload and upload the file through burpsuite request </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Edit the extension to full upload the file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Naviagate to the payload and a revershell is gained</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Look for SUID binaries and find an exploit on GTFOBins to gain root access</li>
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

<!-- wp:image {"id":4744,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-331.png?w=720" alt="" class="wp-image-4744"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4745,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-332.png?w=1024" alt="" class="wp-image-4745"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4746,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-333.png?w=966" alt="" class="wp-image-4746"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4748,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-334.png?w=1024" alt="" class="wp-image-4748"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 8000</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4751,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-336.png?w=1024" alt="" class="wp-image-4751"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4750,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-335.png?w=1024" alt="" class="wp-image-4750"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>SMB Enumeration </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4754,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-338.png?w=1024" alt="" class="wp-image-4754"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4753,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-337.png?w=1024" alt="" class="wp-image-4753"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>mailsent.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4758,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-339.png?w=1007" alt="" class="wp-image-4758"/><figcaption class="wp-element-caption">Some clues</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>From port 8000 we can see it runs on the Koken cms.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Find the admin page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4759,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-340.png?w=1024" alt="" class="wp-image-4759"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>login with the sent user email id and the password as the clue.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4761,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-341.png?w=361" alt="" class="wp-image-4761"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Search an exploit online</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4763,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-342.png?w=1024" alt="" class="wp-image-4763"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4765,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-343.png?w=1024" alt="" class="wp-image-4765"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>From the exploit information we need to craft a reverse shell php payload with .jpg extension and forward it to burpsuite. From there we remove the .jpg extension and forward the request.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4772,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-347.png?w=1024" alt="" class="wp-image-4772"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Payload uploaded</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4773,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-348.png?w=802" alt="" class="wp-image-4773"/><figcaption class="wp-element-caption">enable the download link</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Back to the 8000 webserver we click on the download file link of the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4774,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-349.png?w=1024" alt="" class="wp-image-4774"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Set up a nc listener a shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4776,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-350.png?w=1024" alt="" class="wp-image-4776"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The first flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4777,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-351.png?w=762" alt="" class="wp-image-4777"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Search for setuid binaries and we can use the php7.2 binary.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4779,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-352.png?w=1024" alt="" class="wp-image-4779"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use GTFOBins to get a php SUID exploit</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4785,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-354.png?w=898" alt="" class="wp-image-4785"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4780,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-353.png?w=1024" alt="" class="wp-image-4780"/></figure>
<!-- /wp:image -->
