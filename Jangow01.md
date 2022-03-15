<!-- wp:paragraph -->
<p>Download the box from <a href="https://www.vulnhub.com/entry/jangow-101,754/" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Discover the machine IP with netdiscover.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Run a nmap scan.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":818,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-69.png?w=808" alt="" class="wp-image-818"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the http site.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":820,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-70.png?w=1024" alt="" class="wp-image-820"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Click on the Buscar page on the top right. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Seems like a page we can exploit, (http://192.168.18.4/site/busque.php?buscar=)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Send the page to burpsuite.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":823,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-71.png?w=743" alt="" class="wp-image-823"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Send the page to repeater.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":824,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-72.png?w=738" alt="" class="wp-image-824"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test out some linux commands.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":826,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-73.png?w=749" alt="" class="wp-image-826"/><figcaption>Able to list out the current directory</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p> Use basecode encoding to explore the rest of the directories.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":828,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-74.png?w=744" alt="" class="wp-image-828"/><figcaption>Found a user jangow01</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":830,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-75.png?w=744" alt="" class="wp-image-830"/><figcaption>user.txt is found</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":832,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-76.png?w=745" alt="" class="wp-image-832"/><figcaption>User flag is found</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>d41d8cd98f00b204e9800998ecf8427e</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's cat the config.php file found in the wordpress directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":834,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-77.png?w=915" alt="" class="wp-image-834"/><figcaption>Some credentials found</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>$username = "desafio02";<br>$password = "abygurl69";</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Tried logging in with desafio02 account and password but it was invalid. Tried it again with the jangow01 user and gained access.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":836,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-78.png?w=772" alt="" class="wp-image-836"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Cant find anything on the FTP servers.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's login to the main VM itself.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":837,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-79.png?w=676" alt="" class="wp-image-837"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Download the dirtycow exploit from <a href="https://gist.github.com/scumjr/17d91f20f73157c722ba2aea702985d2" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Complile the exploit with : gcc -Wall -o dirtycow-mem dirtycow-mem.c -ldl -lpthread</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":843,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-82.png?w=881" alt="" class="wp-image-843"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":844,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-83.png?w=418" alt="" class="wp-image-844"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head back to the VM chmod +x the exploit and run it.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Root is gained and head to the root folder to find the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":840,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-81.png?w=796" alt="" class="wp-image-840"/></figure>
<!-- /wp:image -->
