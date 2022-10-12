<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/bob-101,226/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/bob-101,226/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a webshell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use "\" to bypass restrictions for command injection</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a backup file that contains the webshell source code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Insert a nc reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Enumerate folders to find creds</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SSH to users</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find admin's secret folder and solve a cryptic message to get a passkey for the encrypted file.</li>
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

<!-- wp:image {"id":6577,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-281.png?w=702" alt="" class="wp-image-6577"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6575,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-280.png?w=1024" alt="" class="wp-image-6575"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6574,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-279.png?w=941" alt="" class="wp-image-6574"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6585,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-286.png?w=1024" alt="" class="wp-image-6585"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6578,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-282.png?w=558" alt="" class="wp-image-6578"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/ passwords.html</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6580,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-283.png?w=1024" alt="" class="wp-image-6580"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/lat_memo.html</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6582,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-284.png?w=1024" alt="" class="wp-image-6582"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/dev_shell.php</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6583,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-285.png?w=1024" alt="" class="wp-image-6583"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried a couple of commands but it was restricted.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6587,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-287.png?w=721" alt="" class="wp-image-6587"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>However by using "\" I'm able to us the ls command and found these files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6589,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-288.png?w=638" alt="" class="wp-image-6589"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Enter dev_shell.php.bak in the URL and download the backup file. It shows the php code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6590,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-289.png?w=1024" alt="" class="wp-image-6590"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's insert a nc bash reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6592,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-290.png?w=737" alt="" class="wp-image-6592"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Gain a shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6593,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-291.png?w=715" alt="" class="wp-image-6593"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a file that some creds.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6595,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-292.png?w=520" alt="" class="wp-image-6595"/><figcaption class="wp-element-caption">seb:T1tanium_Pa$$word_Hack3rs_Fear_M3</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Read the notes to get more clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6597,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-293.png?w=1024" alt="" class="wp-image-6597"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6598,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-294.png?w=696" alt="" class="wp-image-6598"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>From the information we gathered</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>Username</td><td>Password</td></tr><tr><td>jc or James </td><td>Qwerty</td></tr><tr><td>seb</td><td>T1tanium_Pa$$word_Hack3rs_Fear_M3</td></tr><tr><td>elliot</td><td>theadminisdumb</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Bob seems to be the admin of this system.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's see if we can SSH to any of these users to get a better shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6600,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-295.png?w=1024" alt="" class="wp-image-6600"/><figcaption class="wp-element-caption">access gained.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the other password to switch users.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Tried exploiting sudo permissions but unable to get anything.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Decided to enumerate each folder again.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found a encrypted file in bob's folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6602,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-296.png?w=764" alt="" class="wp-image-6602"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We need a password to decrypt the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6604,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-297.png?w=752" alt="" class="wp-image-6604"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a Secret folder and a script executing cryptic messages.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6606,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-298.png?w=1024" alt="" class="wp-image-6606"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The first alphabet of each line gives us HARPOCRATES.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6608,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-299.png?w=713" alt="" class="wp-image-6608"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Decrypt the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6610,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-300.png?w=1024" alt="" class="wp-image-6610"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Switch user to bob and bod is able to use all root commands.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Switch to the root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6612,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-301.png?w=1024" alt="" class="wp-image-6612"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6614,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-302.png?w=748" alt="" class="wp-image-6614"/></figure>
<!-- /wp:image -->
