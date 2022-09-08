<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/sunset-decoy,505/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/sunset-decoy,505/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Use fcrackzip to get password for the zipfile</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Unshadow files to get password hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Crack the hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bypass restrictive shell </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Observe the AV </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find exploit for chrootkit to gain root access</li>
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

<!-- wp:image {"id":4430,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-196.png?w=840" alt="" class="wp-image-4430"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4428,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-195.png?w=567" alt="" class="wp-image-4428"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4431,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-197.png?w=1024" alt="" class="wp-image-4431"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's download the save.zip file form the webserver. However it is password protected. Use fcrackzip to get the password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4433,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-198.png?w=429" alt="" class="wp-image-4433"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The zip file contains a /etc/ folders that has the following.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4434,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-199.png?w=422" alt="" class="wp-image-4434"/><figcaption class="wp-element-caption">Contains hashes and information about the machine.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's crack the shadow file.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Since there is both the passwd and shadow file we can unshadow and run john on it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4436,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-200.png?w=482" alt="" class="wp-image-4436"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4440,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-202.png?w=1024" alt="" class="wp-image-4440"/><figcaption class="wp-element-caption">Found a user password.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>However this user looks suspicious and from accessing it it seems to be a honeypot with very little privileges.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4438,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-201.png?w=1024" alt="" class="wp-image-4438"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The user is limited with a restricted shell. We need to bypass it.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use the following ssh command to bypass the shell.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ssh 296640a3b825115a47b68fc44501c828@192.168.18.4 -t "bash --noprofile"</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4442,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-203.png?w=1024" alt="" class="wp-image-4442"/><figcaption class="wp-element-caption">We need to use the full path for cat to work to get the user.txt flag.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's run the honeypot file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4444,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-204.png?w=945" alt="" class="wp-image-4444"/><figcaption class="wp-element-caption">Use the AV scan option.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After exploring the rest of the directories we are able to find a log file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4446,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-205.png?w=1024" alt="" class="wp-image-4446"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The chkrootkit is executed during the AV scan.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4448,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-206.png?w=891" alt="" class="wp-image-4448"/><figcaption class="wp-element-caption">It gives the version too.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Search exploit db for an exploit of this version.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4450,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-207.png?w=1024" alt="" class="wp-image-4450"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Instructions are given.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4451,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-208.png?w=758" alt="" class="wp-image-4451"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Create an update file and insert a nc reverse shell to your attacking machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4453,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-209.png?w=1024" alt="" class="wp-image-4453"/><figcaption class="wp-element-caption">use /usr/bin/chmod +x update </figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start a nc listner an root access is gain.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4455,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-210.png?w=876" alt="" class="wp-image-4455"/></figure>
<!-- /wp:image -->
