<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/inclusiveness-1,422/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/inclusiveness-1,422/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Driectory enumeration indicates robots.txt can be seen with a regular user-agent</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use curl to bypass the user-agent with Googlebot to find a clue</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Hidden directory can be exploited by LFI</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Test out the LFI exploit by uploading a PHP webshell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Create a PHP reverse shell and upload to get a shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Explore system to find a rootshell program</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Edit configuration to gain root access</li>
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

<!-- wp:image {"id":4859,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-382.png?w=834" alt="" class="wp-image-4859"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4861,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-384.png?w=1024" alt="" class="wp-image-4861"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Most of the robots pages shows this.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4860,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-383.png?w=699" alt="" class="wp-image-4860"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>FTP</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4863,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-385.png?w=757" alt="" class="wp-image-4863"/><figcaption class="wp-element-caption">Unable to find anything</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Lets' bypass the useragent with google bot in curl</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4867,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-387.png?w=1024" alt="" class="wp-image-4867"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/secret_information/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4868,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-388.png?w=1024" alt="" class="wp-image-4868"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to do some DNS enumeration but there wasn't much. However upon noticing the URL of the secret information, I decided to try a directory reversal.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4960,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-396.png?w=765" alt="" class="wp-image-4960"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4959,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-395.png?w=937" alt="" class="wp-image-4959"/><figcaption class="wp-element-caption">Seems that it can be exploited.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since we know the FTP runs vsftpd, let's search for a config file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4962,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-397.png?w=931" alt="" class="wp-image-4962"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4963,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-398.png?w=634" alt="" class="wp-image-4963"/><figcaption class="wp-element-caption">We are able to write into the ftp directory</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Create a PHP webshell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4968,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-402.png?w=710" alt="" class="wp-image-4968"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4966,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-400.png?w=354" alt="" class="wp-image-4966"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload it into the FTP server.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4967,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-401.png?w=759" alt="" class="wp-image-4967"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test the webshell</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4971,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-404.png?w=915" alt="" class="wp-image-4971"/><figcaption class="wp-element-caption">It works.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now let's enter a PHP reverse shell payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4973,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-405.png?w=708" alt="" class="wp-image-4973"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Encode the one liner PHP reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4974,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-406.png?w=982" alt="" class="wp-image-4974"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Paste the encoded script into the webshell, start a netcat listener and a shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4976,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-407.png?w=1024" alt="" class="wp-image-4976"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4978,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-408.png?w=811" alt="" class="wp-image-4978"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Checking Tom directory we find a rootshell.c </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4979,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-409.png?w=671" alt="" class="wp-image-4979"/><figcaption class="wp-element-caption">The file will execute a root shell if the current user is Tom</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Head to the tmp directory and create a whoami file with tom. Then export the path.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4981,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-410.png?w=832" alt="" class="wp-image-4981"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the rootshell again and root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4982,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-411.png?w=407" alt="" class="wp-image-4982"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4984,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-412.png?w=720" alt="" class="wp-image-4984"/></figure>
<!-- /wp:image -->
