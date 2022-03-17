<!-- wp:paragraph -->
<p>Start by identifying the victim IP with netdiscover.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":872,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-98.png?w=782" alt="" class="wp-image-872"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a nmap scan to look for open ports.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":868,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-95.png?w=763" alt="" class="wp-image-868"/><figcaption>Port 80 and a type ssh port 4512 is open</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to website and it is run by a wordpress site.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's use wpscan to scan for users.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>wpscan --url 192.168.18.15 --enumerate u</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":860,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-90.png?w=586" alt="" class="wp-image-860"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":861,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-91.png?w=669" alt="" class="wp-image-861"/><figcaption>3 Users found</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use wpscan again with c0ldd user.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>wpscan --url 192.168.18.15 --passwords /usr/share/wordlists/rockyou.txt --usernames c0ldd</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":862,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-92.png?w=780" alt="" class="wp-image-862"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":864,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-93.png?w=837" alt="" class="wp-image-864"/><figcaption>password found</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Login to the wordpress site and head to the editor section. Upload a php revershell on the header section. Start up netcat too.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":869,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-96.png?w=1023" alt="" class="wp-image-869"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Reload the main site again and access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":870,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-97.png?w=836" alt="" class="wp-image-870"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Look at the wp-config.php file and get user credentials.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":850,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-84.png?w=369" alt="" class="wp-image-850"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the python shell exploit to gain and shell and switch user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":852,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-85.png?w=442" alt="" class="wp-image-852"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Find the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":853,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-86.png?w=489" alt="" class="wp-image-853"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>mVsaWNpZGFkZXMsIHByaW1lciBuaXZlbCBjb25zZWd1aWRvIQ==</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Sudo -l to find what we can use to exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":855,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-87.png?w=760" alt="" class="wp-image-855"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to gtfobins to find the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"bash"} -->
<pre class="wp-block-syntaxhighlighter-code">sudo vim -c ':!/bin/sh'</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:image {"id":856,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-88.png?w=606" alt="" class="wp-image-856"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the root folder to get the final flag. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":858,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-89.png?w=492" alt="" class="wp-image-858"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>wqFGZWxpY2lkYWRlcywgbcOhcXVpbmEgY29tcGxldGFkYSE=</p>
<!-- /wp:paragraph -->
