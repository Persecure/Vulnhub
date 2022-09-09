<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/evilbox-one,736/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/evilbox-one,736/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Use gobuster to enumerate the webserver</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use ffuf to enumerate parameters</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Command parameter able to view restrictive information like passwd file and rsa keys</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>RSA key is password locked , use ssh2john to crack the hash</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Observe write permission in passwd file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Edit root user password in passwd with hash generated from openssl to gain root access</li>
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

<!-- wp:image {"id":4466,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-211.png?w=758" alt="" class="wp-image-4466"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4467,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-212.png?w=1024" alt="" class="wp-image-4467"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4469,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-213.png?w=1024" alt="" class="wp-image-4469"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4470,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-214.png?w=545" alt="" class="wp-image-4470"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The secret folder shows a 301 status. Let's enumerate that folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4471,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-215.png?w=1024" alt="" class="wp-image-4471"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use ffuf to enumerate the evil.php folder.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ffuf -c -r -u 'http://192.168.18.12/secret/evil.php?FUZZ=/etc/passwd' -w /usr/share/seclists/Discovery/Web-Content/common.txt -fs 0</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4476,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-216.png?w=1024" alt="" class="wp-image-4476"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Add the parameter found in ffuf and we can see the passwd file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4477,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-217.png?w=930" alt="" class="wp-image-4477"/><figcaption class="wp-element-caption">The user mowree is found.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The parameters only allows sensitive information after trying out different methods , we are able to view the private key for the user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4479,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-218.png?w=953" alt="" class="wp-image-4479"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We still a password for the private key.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4481,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-219.png?w=525" alt="" class="wp-image-4481"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use ssh2john to get the hash</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4483,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-220.png?w=972" alt="" class="wp-image-4483"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Password found</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4485,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-221.png?w=950" alt="" class="wp-image-4485"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ssh into the mowree account.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4487,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-222.png?w=1024" alt="" class="wp-image-4487"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>First flag found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4488,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-223.png?w=413" alt="" class="wp-image-4488"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are unable to find sudo permission but a list of /etc/passwd file indicated we are able to write the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4490,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-224.png?w=542" alt="" class="wp-image-4490"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's edit the root user in the passwd file.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First create a password hash with openssl.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4498,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-228.png?w=385" alt="" class="wp-image-4498"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4496,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-227.png?w=710" alt="" class="wp-image-4496"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch to the root user with the new password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4500,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-229.png?w=460" alt="" class="wp-image-4500"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4501,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-230.png?w=351" alt="" class="wp-image-4501"/></figure>
<!-- /wp:image -->
