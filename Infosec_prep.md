<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/infosec-prep-oscp,508/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/infosec-prep-oscp,508/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Find hidden directories on web server</li><li>Decrypt clues with base64</li><li>Edit files to gain information needed</li></ul>
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

<!-- wp:image {"id":3789,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-616.png?w=1024" alt="" class="wp-image-3789"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3790,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-617.png?w=1024" alt="" class="wp-image-3790"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3814,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-633.png?w=625" alt="" class="wp-image-3814"/><figcaption class="wp-element-caption">Found a user.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3795,"width":974,"height":494,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large is-resized"><img src="https://persecure.files.wordpress.com/2022/08/image-621.png?w=1024" alt="" class="wp-image-3795" width="974" height="494"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3793,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-619.png?w=552" alt="" class="wp-image-3793"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a base64 script</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3794,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-620.png?w=650" alt="" class="wp-image-3794"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef to decode the base64 code and it is a RSA key.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3796,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-622.png?w=669" alt="" class="wp-image-3796"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SSH into oscp user with the RSA key</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3797,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-623.png?w=1024" alt="" class="wp-image-3797"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3804,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-628.png?w=715" alt="" class="wp-image-3804"/><figcaption class="wp-element-caption">There is txt file call ip that is run by root and sends out the ip address.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3806,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-629.png?w=316" alt="" class="wp-image-3806"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's edit the file and list out the root folder in a ls.txt file. Chmod the file to view it. Restart the machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3808,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-630.png?w=352" alt="" class="wp-image-3808"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Edit the ip file script again to cat the flag.txt file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3810,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-631.png?w=455" alt="" class="wp-image-3810"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Flag is found</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3803,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-627.png?w=712" alt="" class="wp-image-3803"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Even though the flag is found we can gain root access with the following.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3812,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-632.png?w=599" alt="" class="wp-image-3812"/><figcaption class="wp-element-caption">/bin/bash indicates a setuid info, these does not seem right.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3800,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-625.png?w=399" alt="" class="wp-image-3800"/><figcaption class="wp-element-caption">root shell is gained.</figcaption></figure>
<!-- /wp:image -->
