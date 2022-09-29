<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/icmp-1,633/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/icmp-1,633/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Use the Monitorr exploit</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Search for a crypt.php file to find a user password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check for sudo permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>User can use Hping3 as root</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Transfer the private rsa key locally with hping3 to gain root access</li>
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

<!-- wp:image {"id":5598,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-653.png?w=652" alt="" class="wp-image-5598"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5600,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-654.png?w=946" alt="" class="wp-image-5600"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5602,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-655.png?w=1024" alt="" class="wp-image-5602"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5604,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-656.png?w=1024" alt="" class="wp-image-5604"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5605,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-657.png?w=1024" alt="" class="wp-image-5605"/><figcaption class="wp-element-caption">The version number can be found as Monitorr 1.7.6</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found an exploit of searchsploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5607,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-658.png?w=830" alt="" class="wp-image-5607"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the exploit and start a netcat listener </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5609,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-659.png?w=656" alt="" class="wp-image-5609"/></figure>
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

<!-- wp:image {"id":5611,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-660.png?w=800" alt="" class="wp-image-5611"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some exploring, I head to the home directory and found a fox user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5612,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-661.png?w=563" alt="" class="wp-image-5612"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a reminder text that indicates about a file called crypt.php. Since we cant enter devel folder , I tried to cat the file from outside. Found a key. Let's see if this the ssh password for the fox user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5614,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-662.png?w=848" alt="" class="wp-image-5614"/><figcaption class="wp-element-caption">Fox user accessed</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5616,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-663.png?w=647" alt="" class="wp-image-5616"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found out the files can be transferred out by hping3 in Google.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's test this out.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Set up the listener hping3 on the receiving machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5620,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-665.png?w=598" alt="" class="wp-image-5620"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now transfer the /etc/passwd file to the receiving machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5618,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-664.png?w=890" alt="" class="wp-image-5618"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It went through</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5621,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-666.png?w=607" alt="" class="wp-image-5621"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now let's see if we can transfer the SSH RSA key for the root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5623,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-667.png?w=913" alt="" class="wp-image-5623"/><figcaption class="wp-element-caption">However it sends multiple results.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now i'll use hping3 inside the machine instead. Open up another fox user. In one of the shell start a listener.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5625,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-668.png?w=609" alt="" class="wp-image-5625"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>And in the other send the file over.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5627,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-669.png?w=913" alt="" class="wp-image-5627"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can see the full key now.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5629,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-670.png?w=726" alt="" class="wp-image-5629"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Copy the key to your attacking machine. Change the permissions and SSH into the root user.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5631,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-671.png?w=820" alt="" class="wp-image-5631"/></figure>
<!-- /wp:image -->
