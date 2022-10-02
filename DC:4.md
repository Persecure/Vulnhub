<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dc-4,313/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dc-4,313/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to an Admin login page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bruteforce with burpsuite</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Once admin access is gained, Use burpsuite repeater to injects commands</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a old password list in one of the users</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bruteforce users with the newly found list</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check mail indox for password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Switch user and check sudo permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit the teehee (tee) editor</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Add a user with root privileges </li>
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

<!-- wp:image {"id":5907,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-30.png?w=663" alt="" class="wp-image-5907"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5910,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-32.png?w=1024" alt="" class="wp-image-5910"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5911,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-33.png?w=1024" alt="" class="wp-image-5911"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5908,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-31.png?w=1024" alt="" class="wp-image-5908"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's try to do a bruteforce of login credentials with burpsuite. Since the interface says it for Admin we can use admin as the user and just bruteforce the password. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Set up burpsuite and send it to intruder and load up a password list as the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5923,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-35.png?w=1024" alt="" class="wp-image-5923"/><figcaption class="wp-element-caption">Password is happy</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5924,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-36.png?w=1024" alt="" class="wp-image-5924"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5925,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-37.png?w=1024" alt="" class="wp-image-5925"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5927,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-38.png?w=905" alt="" class="wp-image-5927"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5928,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-39.png?w=874" alt="" class="wp-image-5928"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5932,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-41.png?w=716" alt="" class="wp-image-5932"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to do command injection. Test it with the pwd command.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5930,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-40.png?w=1024" alt="" class="wp-image-5930"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Search the home users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5934,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-42.png?w=1024" alt="" class="wp-image-5934"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a backup file in the Jim user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5936,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-43.png?w=1024" alt="" class="wp-image-5936"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Inside there is an old-passwords.bak file</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5938,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-44.png?w=1024" alt="" class="wp-image-5938"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Contains a list.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5940,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-45.png?w=1024" alt="" class="wp-image-5940"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Copy the list into a file and use hydra to bruteforce the found users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5943,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-46.png?w=1024" alt="" class="wp-image-5943"/><figcaption class="wp-element-caption">found a user</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Jim user access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5945,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-47.png?w=840" alt="" class="wp-image-5945"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a bash script</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5949,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-49.png?w=648" alt="" class="wp-image-5949"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to check for sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5947,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-48.png?w=747" alt="" class="wp-image-5947"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After doing some commands , I received a notification.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5953,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-51.png?w=968" alt="" class="wp-image-5953"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checked the mail folder and found a password for charles.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5952,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-50.png?w=1024" alt="" class="wp-image-5952"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch to the charles user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5955,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-52.png?w=645" alt="" class="wp-image-5955"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check for sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5956,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-53.png?w=1024" alt="" class="wp-image-5956"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>teehee help info</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5963,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-56.png?w=935" alt="" class="wp-image-5963"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's add another root privilege user and switch into that user.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "persecure::0:0:::/bin/bash" | sudo teehee -a /etc/passwd</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5958,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-54.png?w=995" alt="" class="wp-image-5958"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5960,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-55.png?w=1024" alt="" class="wp-image-5960"/></figure>
<!-- /wp:image -->
