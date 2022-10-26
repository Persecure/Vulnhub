<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>Name</strong>: Deathnote: 1</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Date release</strong>: 4 Sep 2021</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Author</strong>:&nbsp;<a href="https://www.vulnhub.com/author/hwkds,816/">HWKDS</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Series</strong>:&nbsp;<a href="https://www.vulnhub.com/series/deathnote,499/">Deathnote</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/deathnote-1,739/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/deathnote-1,739/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a web site with a couple of clues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find the wordpress uploads directory to get a password and users list</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use hydra to crack the password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Once access is gained find a clue in the /opt directory</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Decode the code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>The next user has all sudo permissions</li>
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

<!-- wp:image {"id":7444,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-654.png?w=932" alt="" class="wp-image-7444"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7445,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-655.png?w=1024" alt="" class="wp-image-7445"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Add deathnote.vuln in etc/hosts.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7447,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-656.png?w=1024" alt="" class="wp-image-7447"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a hint section in the site.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7449,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-657.png?w=918" alt="" class="wp-image-7449"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like we can see a potential password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7451,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-658.png?w=403" alt="" class="wp-image-7451"/><figcaption class="wp-element-caption">iamjustic3</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7453,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-659.png?w=523" alt="" class="wp-image-7453"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7460,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-663.png?w=1024" alt="" class="wp-image-7460"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>While exploring the images in the site I found a wp-content uploads directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7455,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-660.png?w=923" alt="" class="wp-image-7455"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like a password list.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7457,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-661.png?w=853" alt="" class="wp-image-7457"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>And a username list.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7458,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-662.png?w=821" alt="" class="wp-image-7458"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use both text file on hydra and a password for l user will be found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7462,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-664.png?w=851" alt="" class="wp-image-7462"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7464,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-665.png?w=1024" alt="" class="wp-image-7464"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a user text file but it looks encoded.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7466,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-666.png?w=495" alt="" class="wp-image-7466"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like its encrypted with brainfuck.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7467,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-667.png?w=799" alt="" class="wp-image-7467"/><figcaption class="wp-element-caption">Nothing interesting just a message.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some time enumerating, I found two folders in the /opt directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7469,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-668.png?w=589" alt="" class="wp-image-7469"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a encoded text.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7471,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-669.png?w=869" alt="" class="wp-image-7471"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cyberchef to decode the text.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7473,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-670.png?w=1024" alt="" class="wp-image-7473"/><figcaption class="wp-element-caption">It's double encoded. Use Hex and then base64.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch to the kira user and text file can be seen.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7475,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-671.png?w=885" alt="" class="wp-image-7475"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It's another base64 code that has more clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7477,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-672.png?w=1024" alt="" class="wp-image-7477"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like a rabbit hole.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7479,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-673.png?w=371" alt="" class="wp-image-7479"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions and Kira can run everything.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7481,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-674.png?w=1024" alt="" class="wp-image-7481"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use sudo bash to gain a root shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7483,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-675.png?w=506" alt="" class="wp-image-7483"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the root flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7485,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-676.png?w=1024" alt="" class="wp-image-7485"/></figure>
<!-- /wp:image -->
