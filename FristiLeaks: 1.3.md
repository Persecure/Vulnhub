<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/fristileaks-13,133/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/fristileaks-13,133/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to some clues for a hidden file.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the drink name of the box to find a hidden login page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Read the source code</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Decode the base64 code into a image of the password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Upload a reverse shell with an image extension</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit a cronjob to gain access to a user</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a decoder python script , reverse it to get a password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit a SUID binary to gain root</li>
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

<!-- wp:image {"id":6716,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-347.png?w=1024" alt="" class="wp-image-6716"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6711,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-344.png?w=1024" alt="" class="wp-image-6711"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6715,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-346.png?w=1024" alt="" class="wp-image-6715"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6719,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-348.png?w=550" alt="" class="wp-image-6719"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>All of the directories have the same image.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6713,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-345.png?w=757" alt="" class="wp-image-6713"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since the disallowed list are names of drinks , ill use the name of the box instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6720,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-349.png?w=1024" alt="" class="wp-image-6720"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The source code will indicate some clues , potential user names.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6722,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-350.png?w=1024" alt="" class="wp-image-6722"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>At the bottom of the page there will be a base64 encoded file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6726,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-352.png?w=682" alt="" class="wp-image-6726"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Save it into a file and it will be an image file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6724,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-351.png?w=508" alt="" class="wp-image-6724"/><figcaption class="wp-element-caption">Potential password</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6728,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-353.png?w=401" alt="" class="wp-image-6728"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6729,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-354.png?w=674" alt="" class="wp-image-6729"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6730,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-355.png?w=607" alt="" class="wp-image-6730"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Add a jpg extension to a PHP reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6732,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-356.png?w=576" alt="" class="wp-image-6732"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start a netcat listener and head to the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6734,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-357.png?w=433" alt="" class="wp-image-6734"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A shell is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6736,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-358.png?w=1024" alt="" class="wp-image-6736"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a note in EZ's folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6738,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-359.png?w=859" alt="" class="wp-image-6738"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Lets chmod the admin folder so we can view it contents.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "/home/admin/chmod -R 777 /home/admin" &gt; /tmp/runthis</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>After a min.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6741,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-360.png?w=729" alt="" class="wp-image-6741"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6743,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-361.png?w=1012" alt="" class="wp-image-6743"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6745,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-362.png?w=680" alt="" class="wp-image-6745"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Reverse the python program with the encoded text to get a password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6747,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-363.png?w=518" alt="" class="wp-image-6747"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6749,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-364.png?w=413" alt="" class="wp-image-6749"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch to the fristigod user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6750,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-365.png?w=771" alt="" class="wp-image-6750"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check for sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6752,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-366.png?w=947" alt="" class="wp-image-6752"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6754,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-367.png?w=973" alt="" class="wp-image-6754"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to run the setuid file and spawn a shell as root.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>sudo -u fristi /var/fristigod/.secret_admin_stuff/doCom /bin/bash</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6756,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-368.png?w=793" alt="" class="wp-image-6756"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6757,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-369.png?w=866" alt="" class="wp-image-6757"/></figure>
<!-- /wp:image -->
