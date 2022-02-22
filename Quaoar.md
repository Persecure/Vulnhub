# QUAOAR-Vulnhub

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/hackfest2016-quaoar,180/">https://www.vulnhub.com/entry/hackfest2016-quaoar,180/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Goals: This machine is intended to be doable by someone who is interested in learning computer security There are 3 flags on this machine 1. Get a shell 2. Get root access 3. There is a post exploitation flag on the box</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use netdiscover to find the IP address of the machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":130,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/netdiscover-1.png?w=690" alt="" class="wp-image-130"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run nmap to scan for open ports.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":132,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/nmap-1.png?w=573" alt="" class="wp-image-132"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run gobuster to find for directories.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":133,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/gobuster.png?w=740" alt="" class="wp-image-133"/><figcaption>Seems the site is runned by wordpress</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run wpscan to look for users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":135,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/wpscan1.png?w=686" alt="" class="wp-image-135"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":136,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/wpscan2.png?w=691" alt="" class="wp-image-136"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the wordpress site and login via Username: admin Password: admin (default)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>You are able to spawn a shell by editing the theme of the site. Use a php reverse shell exploit from https://pentestmonkey.net/tools/web-shells/php-reverse-shell. *Remember to change the listening IP to your attacking machine. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":138,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/wpphp.png?w=1024" alt="" class="wp-image-138"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start a netcat listener and reload a page from the main wordpress site. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":140,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/nc1.png?w=841" alt="" class="wp-image-140"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Spawn a python shell for a more stable shell using: </p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">python -c 'import pty; pty.spawn("/bin/sh")'</pre>
<!-- /wp:preformatted -->

<!-- wp:image {"id":142,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/pythonshell.png?w=552" alt="" class="wp-image-142"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the wp-config.php to find root credentials. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":144,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/wpadmin.png?w=630" alt="" class="wp-image-144"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>su to root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":145,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/root-1.png?w=520" alt="" class="wp-image-145"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the root folder and find the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":147,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/root2.png?w=325" alt="" class="wp-image-147"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to wpadmin folder from the home/user to find the second flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":148,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/flag2.png?w=434" alt="" class="wp-image-148"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>And finally head to the cron folder to find the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":150,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/02/flag3.png?w=870" alt="" class="wp-image-150"/></figure>
<!-- /wp:image -->
