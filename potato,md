<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/potato-1,529/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/potato-1,529/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Access FTP server to find for source code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Inspect port 80 and look for PHP Type Juggling vulnerability</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gain access to server and use Burpsuite to explore requests</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use LFI to gain user's hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use John to crack hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check sudo permissions to gain root access</li>
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

<!-- wp:image {"id":4341,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-153.png?w=545" alt="" class="wp-image-4341"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4342,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-154.png?w=867" alt="" class="wp-image-4342"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4343,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-155.png?w=995" alt="" class="wp-image-4343"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4345,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-156.png?w=1024" alt="" class="wp-image-4345"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/potato/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4346,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-157.png?w=524" alt="" class="wp-image-4346"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/admin/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4347,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-158.png?w=574" alt="" class="wp-image-4347"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check the FTP server</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4350,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-160.png?w=743" alt="" class="wp-image-4350"/><figcaption class="wp-element-caption">Get both files</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>welcome.msg</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4352,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-161.png?w=331" alt="" class="wp-image-4352"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>index.php.bak</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4349,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-159.png?w=797" alt="" class="wp-image-4349"/><figcaption class="wp-element-caption">We get some credentionals</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried the creds but still same</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Looking at the source code above we can see that it uses a strpcmp.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I found a clue <a href="https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf" data-type="URL" data-id="https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf" target="_blank" rel="noreferrer noopener">online</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4355,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-162.png?w=1024" alt="" class="wp-image-4355"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4356,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-163.png?w=1024" alt="" class="wp-image-4356"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Edit and resend the request header with adding the array like this.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4358,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-164.png?w=345" alt="" class="wp-image-4358"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4360,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-165.png?w=291" alt="" class="wp-image-4360"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4361,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-166.png?w=649" alt="" class="wp-image-4361"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to get files from the server.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4363,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-167.png?w=721" alt="" class="wp-image-4363"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's intercept with burpsuite</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4364,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-168.png?w=1024" alt="" class="wp-image-4364"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use File Inclusion/Path traversal scripts to test.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4366,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-169.png?w=805" alt="" class="wp-image-4366"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the passwd file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4368,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-170.png?w=782" alt="" class="wp-image-4368"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's crack the hash with John.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4370,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-171.png?w=937" alt="" class="wp-image-4370"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>SSH into the webadmin user.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4372,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-172.png?w=834" alt="" class="wp-image-4372"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the user flag</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4373,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-173.png?w=743" alt="" class="wp-image-4373"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4375,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-174.png?w=1024" alt="" class="wp-image-4375"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>No permissions in the notes folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4377,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-175.png?w=549" alt="" class="wp-image-4377"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Head back to home folder and use sudo permision with notes to gain a root shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4379,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-176.png?w=693" alt="" class="wp-image-4379"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4380,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-177.png?w=904" alt="" class="wp-image-4380"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Bse64 both flages to get the encrypted flags.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4382,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-178.png?w=1024" alt="" class="wp-image-4382"/></figure>
<!-- /wp:image -->
