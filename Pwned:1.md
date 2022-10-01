<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/pwned-1,507/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/pwned-1,507/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to hidden directories</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a direcotrie list and re enumenrate the web server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Examine the source code to find FTP credentials</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Access FTP to find a private key</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Once access is gained exploit the script with code injection and bind a shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use docker exploit to gain root access</li>
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

<!-- wp:image {"id":5848,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image.png?w=673" alt="" class="wp-image-5848"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5849,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-1.png?w=1024" alt="" class="wp-image-5849"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5850,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-2.png?w=1024" alt="" class="wp-image-5850"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5851,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-3.png?w=1024" alt="" class="wp-image-5851"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>A clue found on port 80 source code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5853,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-4.png?w=392" alt="" class="wp-image-5853"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5854,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-5.png?w=540" alt="" class="wp-image-5854"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/nothing</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5856,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-6.png?w=647" alt="" class="wp-image-5856"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5857,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-7.png?w=618" alt="" class="wp-image-5857"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/hidden_text</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5859,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-8.png?w=579" alt="" class="wp-image-5859"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found some kind of directory list.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5861,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-9.png?w=661" alt="" class="wp-image-5861"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use that list to enumerate the web server again. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5864,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-10.png?w=849" alt="" class="wp-image-5864"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5865,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-11.png?w=1024" alt="" class="wp-image-5865"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>source code of /pwned.vuln</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5866,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-12.png?w=832" alt="" class="wp-image-5866"/><figcaption class="wp-element-caption">Unable to get anything from the page. I tried using the creds on the ftp server.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5868,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-13.png?w=632" alt="" class="wp-image-5868"/><figcaption class="wp-element-caption">Download both files.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The files contains a note stating a potential user name and a private key.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5870,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-14.png?w=706" alt="" class="wp-image-5870"/></figure>
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

<!-- wp:image {"id":5872,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-15.png?w=861" alt="" class="wp-image-5872"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5875,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-17.png?w=393" alt="" class="wp-image-5875"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a note that has potential user names.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5877,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-18.png?w=1024" alt="" class="wp-image-5877"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5873,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-16.png?w=557" alt="" class="wp-image-5873"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the messenger script in the home directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5879,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-19.png?w=453" alt="" class="wp-image-5879"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can run sudo -u selena /home/messenger.sh to interact directly with the selena user. Let's use a bind shell to connect.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5886,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-24.png?w=700" alt="" class="wp-image-5886"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5883,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-22.png?w=589" alt="" class="wp-image-5883"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Selena access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5885,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-23.png?w=615" alt="" class="wp-image-5885"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5881,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-20.png?w=1024" alt="" class="wp-image-5881"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We find the second flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5882,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-21.png?w=603" alt="" class="wp-image-5882"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>After some trial and error I resorted to linpeas. I missed out on the ID in the beginning. Selena user is able to use docker.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5888,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-25.png?w=1024" alt="" class="wp-image-5888"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We search docker exploit on GTFObins.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5889,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-26.png?w=904" alt="" class="wp-image-5889"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the script and root user is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5890,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-27.png?w=1024" alt="" class="wp-image-5890"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5891,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-28.png?w=962" alt="" class="wp-image-5891"/></figure>
<!-- /wp:image -->
