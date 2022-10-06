<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/sunset-midnight,517/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/sunset-midnight,517/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a web &amp; MYSQL server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Webserver is built by Wordpress</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bruteforce MYSQL server to find WP user details</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Update the hash value of the admin with a new password hash to gain WP access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Set up a malicious plugin to gain user access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Search wp config file for credentials</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use SUID to gain root privileges </li>
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

<!-- wp:image {"id":6162,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-136.png?w=668" alt="" class="wp-image-6162"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6163,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-137.png?w=984" alt="" class="wp-image-6163"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6164,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-138.png?w=1024" alt="" class="wp-image-6164"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6166,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-139.png?w=1024" alt="" class="wp-image-6166"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6169,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-141.png?w=591" alt="" class="wp-image-6169"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Only found the admin user by using WPscan.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6171,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-142.png?w=907" alt="" class="wp-image-6171"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried the bruteforce the WP admin user but it took too long. Decided to bruteforce the MYSQL server instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6173,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-143.png?w=1024" alt="" class="wp-image-6173"/><figcaption class="wp-element-caption">Found a password</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check out the MYSQL server.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6177,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-144.png?w=845" alt="" class="wp-image-6177"/><figcaption class="wp-element-caption">Found the WordPress database.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6179,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-145.png?w=775" alt="" class="wp-image-6179"/><figcaption class="wp-element-caption">wp_users in the tables</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6180,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-146.png?w=1004" alt="" class="wp-image-6180"/><figcaption class="wp-element-caption">We can select the user login and password to view.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6182,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-147.png?w=840" alt="" class="wp-image-6182"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's change the password for the admin. I encoded the password "123456" with MD5.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>UPDATE wp_users SET user_pass="e10adc3949ba59abbe56e057f20f883e" WHERE ID=1;</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":6185,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-149.png?w=1024" alt="" class="wp-image-6185"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>WordPress admin access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6186,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-150.png?w=1024" alt="" class="wp-image-6186"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to upload PHP reverse shells but the theme editor had some errors. Resorted to using Wordpwn which you can get it <a href="https://github.com/wetw0rk/malicious-wordpress-plugin" data-type="URL" data-id="https://github.com/wetw0rk/malicious-wordpress-plugin">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6226,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-162.png?w=555" alt="" class="wp-image-6226"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6229,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-164.png?w=881" alt="" class="wp-image-6229"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User accessed gained</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6227,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-163.png?w=893" alt="" class="wp-image-6227"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a WordPress config file with a user and db password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6230,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-165.png?w=830" alt="" class="wp-image-6230"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to switch to the jose user with the same password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6232,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-166.png?w=602" alt="" class="wp-image-6232"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6234,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-167.png?w=389" alt="" class="wp-image-6234"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to find for sudo permissions but unable to, looked for SUID permissions instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6236,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-168.png?w=651" alt="" class="wp-image-6236"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I switched to SSH for jose to get a better shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6238,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-169.png?w=703" alt="" class="wp-image-6238"/><figcaption class="wp-element-caption">the status binary looks different from the rest</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use strings on the binary to examine more.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6240,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-170.png?w=545" alt="" class="wp-image-6240"/><figcaption class="wp-element-caption">Looks like it starts a service</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's export the tmp folder to path and create a service file with a shell in it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6242,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-171.png?w=704" alt="" class="wp-image-6242"/><figcaption class="wp-element-caption">Root access gained</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6244,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-172.png?w=1024" alt="" class="wp-image-6244"/></figure>
<!-- /wp:image -->
