<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dripping-blues-1,744/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dripping-blues-1,744/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a open FTP server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Get the zip file , crack the password and find the clue</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Robots text will indicate a hidden directory</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use directory traversal to find the hidden directory that contains a password in the source code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Enter the user check for SUID permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit the machine with polkit and gain root access</li>
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

<!-- wp:image {"id":6791,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-379.png?w=682" alt="" class="wp-image-6791"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6792,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-380.png?w=949" alt="" class="wp-image-6792"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check the FTP server as anonymous.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6799,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-385.png?w=843" alt="" class="wp-image-6799"/><figcaption class="wp-element-caption">Download the zip file.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Crack the password on the zip file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6802,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-386.png?w=1006" alt="" class="wp-image-6802"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Read the text.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6803,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-387.png?w=374" alt="" class="wp-image-6803"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6795,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-382.png?w=1024" alt="" class="wp-image-6795"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6794,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-381.png?w=635" alt="" class="wp-image-6794"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6797,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-384.png?w=591" alt="" class="wp-image-6797"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6796,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-383.png?w=968" alt="" class="wp-image-6796"/><figcaption class="wp-element-caption">This does not work at all.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the robots text file there is a hidden directory that looks like a command injection. Moreover the clue given seems we can search a drip folder. Lets use the index.php to set a command injection.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6805,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-388.png?w=977" alt="" class="wp-image-6805"/><figcaption class="wp-element-caption">Found the hidden page.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Source code shows a password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6807,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-389.png?w=520" alt="" class="wp-image-6807"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Able to gain access into the thugger user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6809,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-390.png?w=688" alt="" class="wp-image-6809"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6810,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-391.png?w=592" alt="" class="wp-image-6810"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to find SUDO permissions. Check for SUID permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6820,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-396.png?w=543" alt="" class="wp-image-6820"/><figcaption class="wp-element-caption">We can use a polkit exploit.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Get the exploit from <a href="https://github.com/Almorabea/Polkit-exploit" data-type="URL" data-id="https://github.com/Almorabea/Polkit-exploit" target="_blank" rel="noreferrer noopener">here</a>. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6816,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-394.png?w=967" alt="" class="wp-image-6816"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6813,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-392.png?w=1024" alt="" class="wp-image-6813"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root user will be gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6815,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-393.png?w=1024" alt="" class="wp-image-6815"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6818,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-395.png?w=722" alt="" class="wp-image-6818"/></figure>
<!-- /wp:image -->
