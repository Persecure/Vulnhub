<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/cybersploit-1,506/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/cybersploit-1,506/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumerate the directories </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Read the source code of the webpage to get a clue</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>robots.txt gives us a base64 encrypted code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Decrypt the code to get the first flag</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SSH into the user with flag as password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Machine runs an outdated Linux kernel</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find the exploit Linux Kernel 3.13.0 &lt; 3.19 (Ubuntu 12.04/14.04/14.10/15.04) - 'overlayfs' Local Privilege Escalation</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Run the exploit to get root access</li>
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

<!-- wp:image {"id":4621,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-278.png?w=851" alt="" class="wp-image-4621"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4622,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-279.png?w=1023" alt="" class="wp-image-4622"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a username in the sourcecode.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4623,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-280.png?w=476" alt="" class="wp-image-4623"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4628,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-283.png?w=1024" alt="" class="wp-image-4628"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4625,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-281.png?w=649" alt="" class="wp-image-4625"/><figcaption class="wp-element-caption">An encrypted code.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use base64 to decrypt the code and the first flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4627,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-282.png?w=1024" alt="" class="wp-image-4627"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try to ssh into the itsskv user with the flag password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4631,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-284.png?w=998" alt="" class="wp-image-4631"/><figcaption class="wp-element-caption">User access gain.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the second flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4634,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-286.png?w=1024" alt="" class="wp-image-4634"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The 2nd flag is contains a binary code , decrypt it to get the 2nd flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4643,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-288.png?w=926" alt="" class="wp-image-4643"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to run sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4632,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-285.png?w=697" alt="" class="wp-image-4632"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check for linux kernel version</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4645,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-289.png?w=1024" alt="" class="wp-image-4645"/><figcaption class="wp-element-caption">The version is outdated and we can search for an exploit.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4646,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-290.png?w=1024" alt="" class="wp-image-4646"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4648,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-291.png?w=1024" alt="" class="wp-image-4648"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Download the exploit , upload it to the machine and compile it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4650,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-292.png?w=1024" alt="" class="wp-image-4650"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the exploit and root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4652,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-293.png?w=1024" alt="" class="wp-image-4652"/></figure>
<!-- /wp:image -->
