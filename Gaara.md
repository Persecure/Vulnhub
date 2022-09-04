<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/gaara-1,629/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/gaara-1,629/</a></p>
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
<li>Try out diffrent encryption methods</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Get pass the rabbit holes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gain privilege access with GTFO bins</li>
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

<!-- wp:image {"id":4182,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-83.png?w=730" alt="" class="wp-image-4182"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4183,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-84.png?w=1024" alt="" class="wp-image-4183"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4185,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-85.png?w=1024" alt="" class="wp-image-4185"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Scroll all the way to bottom to find some directories.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4186,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-86.png?w=163" alt="" class="wp-image-4186"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Each directory contains text data that tells the history of the character. The /iamGaara file is slightly diffrent form the others and after some observation a clue can be seen in the text.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4188,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-87.png?w=761" alt="" class="wp-image-4188"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef to decrypt the code and after some time I found the decryption method to be base58.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4190,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-88.png?w=1024" alt="" class="wp-image-4190"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to ssh into the user but password is wrong.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4192,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-89.png?w=667" alt="" class="wp-image-4192"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's bruteforce with hydra instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4194,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-90.png?w=850" alt="" class="wp-image-4194"/><figcaption class="wp-element-caption">Found another password instead.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4195,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-91.png?w=719" alt="" class="wp-image-4195"/><figcaption class="wp-element-caption">User access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>First flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4197,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-92.png?w=330" alt="" class="wp-image-4197"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There is txt file that contains a clue.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4199,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-93.png?w=312" alt="" class="wp-image-4199"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef to decrypt and there is a directory location.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4201,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-94.png?w=960" alt="" class="wp-image-4201"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the folder and another clue is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4203,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-95.png?w=718" alt="" class="wp-image-4203"/><figcaption class="wp-element-caption">Looks like it is encrypted in brainfuck</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Decode it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4204,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-96.png?w=605" alt="" class="wp-image-4204"/><figcaption class="wp-element-caption">We need more enumeration</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are unable to view sudo permissions either. Lets use linpeas instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4206,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-97.png?w=991" alt="" class="wp-image-4206"/><figcaption class="wp-element-caption">Found an interesting binary  under the SUID section.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Look up GTFO bins.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4208,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-98.png?w=827" alt="" class="wp-image-4208"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use the GTFO script to gain root acess</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4209,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-99.png?w=914" alt="" class="wp-image-4209"/><figcaption class="wp-element-caption">Access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4210,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-100.png?w=698" alt="" class="wp-image-4210"/></figure>
<!-- /wp:image -->
