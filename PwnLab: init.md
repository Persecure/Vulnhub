<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/pwnlab-init,158/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/pwnlab-init,158/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a config page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use a PHP filter to view the base64 text</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>This will lead to a credential </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find creds in the database </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload a reverse shell and by pass the extension</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a method to read the file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Inside the machine find ways to exploit binaries</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the same method to get root access</li>
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

<!-- wp:image {"id":6453,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-232.png?w=662" alt="" class="wp-image-6453"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6454,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-233.png?w=1024" alt="" class="wp-image-6454"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6456,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-234.png?w=1024" alt="" class="wp-image-6456"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6457,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-235.png?w=1024" alt="" class="wp-image-6457"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a login page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6461,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-237.png?w=998" alt="" class="wp-image-6461"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried using SQL injection and bruteforcing but to no availability.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In the gobuster enumeration found a config.php file , however it doesn't show any results. After some googling I found the following <a rel="noreferrer noopener" href="https://diablohorn.com/2010/01/16/interesting-local-file-inclusion-method/" target="_blank">resource</a>. The php is encoded and wrapped.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6463,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-238.png?w=669" alt="" class="wp-image-6463"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I tried with the following injection.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>http://192.168.18.12/?page=php://filter/convert.base64-encode/resource=config</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Got a result.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6459,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-236.png?w=1024" alt="" class="wp-image-6459"/><figcaption class="wp-element-caption">PD9waHANCiRzZXJ2ZXIJICA9ICJsb2NhbGhvc3QiOw0KJHVzZXJuYW1lID0gInJvb3QiOw0KJHBhc3N3b3JkID0gIkg0dSVRSl9IOTkiOw0KJGRhdGFiYXNlID0gIlVzZXJzIjsNCj8+</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use base64 to decode the text and you will get some credentials.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6465,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-239.png?w=1024" alt="" class="wp-image-6465"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the credentials to login into the mysql server.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6469,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-240.png?w=1024" alt="" class="wp-image-6469"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to view some user credentials in base64.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6470,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-241.png?w=708" alt="" class="wp-image-6470"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Decode the passwords.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6472,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-242.png?w=436" alt="" class="wp-image-6472"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's try the newly found credentials on the login page.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Once I got accessed I tried upload a php file but it needed a image extension.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6474,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-243.png?w=541" alt="" class="wp-image-6474"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>So I renamed the file and uploaded it by burpsuite. I added the magic number in the request too.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6475,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-244.png?w=1024" alt="" class="wp-image-6475"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some trial and error I was able to upload it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6490,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-253.png?w=767" alt="" class="wp-image-6490"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We need to find a way to run the file.  I decoded the index page with the same method I used to find the config file and found that we can use injection by editing the cookie.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6492,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-254.png?w=1024" alt="" class="wp-image-6492"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6476,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-245.png?w=771" alt="" class="wp-image-6476"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Intercept the request and change the cookie to the uploaded link. Remember to start netcat.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6478,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-246.png?w=1024" alt="" class="wp-image-6478"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After trying out the creds, the kane user has a file for us to explore. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6481,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-248.png?w=628" alt="" class="wp-image-6481"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It has a file that runs cat with mike user as the owner. However the cat command is not in the path.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6482,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-249.png?w=710" alt="" class="wp-image-6482"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I create a cat file and export the path back to Kane.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6484,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-250.png?w=487" alt="" class="wp-image-6484"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Once exported I export the path again with mike.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6486,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-251.png?w=1024" alt="" class="wp-image-6486"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There is another file that we can use injection. Sent a shell and got the root user. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6488,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-252.png?w=1009" alt="" class="wp-image-6488"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6479,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-247.png?w=990" alt="" class="wp-image-6479"/></figure>
<!-- /wp:image -->
