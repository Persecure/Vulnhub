<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/w34kn3ss-1,270/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/w34kn3ss-1,270/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to hidden host info</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Edit the /etc/hosts file for the new host</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Directory enumerate the new hots to find a storage site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Download the public key and notice the text file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find the exploit for OpenSSL</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Compare the public key with the exploited hashes to gain access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Decompile the python program to find a password</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Switch to the root user</li>
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

<!-- wp:image {"id":6651,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-314.png?w=914" alt="" class="wp-image-6651"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6652,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-315.png?w=1024" alt="" class="wp-image-6652"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6657,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-318.png?w=1024" alt="" class="wp-image-6657"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6654,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-316.png?w=1024" alt="" class="wp-image-6654"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/ test</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6655,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-317.png?w=622" alt="" class="wp-image-6655"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the nmap scan we can notice a ssl cert report for port 443.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6659,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-319.png?w=1024" alt="" class="wp-image-6659"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I edit the etc/hosts file and we will find a new page. Looks like n30 could be a user name. n30 is also the agent in the Matrix. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6661,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-320.png?w=1024" alt="" class="wp-image-6661"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's do a gobuster scan on this page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6668,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-324.png?w=1024" alt="" class="wp-image-6668"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6663,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-321.png?w=621" alt="" class="wp-image-6663"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/private</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6665,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-322.png?w=1012" alt="" class="wp-image-6665"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>A note file and public key is present in the file storage. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6666,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-323.png?w=625" alt="" class="wp-image-6666"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Seems like an old version openssl. Let's search for an exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6669,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-325.png?w=1024" alt="" class="wp-image-6669"/><figcaption class="wp-element-caption">Download the exploit.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The exploit does not work as we need the private key location and user.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's get the exploit above instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6671,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-326.png?w=1024" alt="" class="wp-image-6671"/><figcaption class="wp-element-caption">Looks like we can compare the public key to the 66 possible options.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The public key contains is base64 encoded.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6673,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-327.png?w=1024" alt="" class="wp-image-6673"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the grep -r -l command to find the public key.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6674,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-328.png?w=931" alt="" class="wp-image-6674"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>use the key to SSH login.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6676,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-329.png?w=925" alt="" class="wp-image-6676"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6690,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-336.png?w=448" alt="" class="wp-image-6690"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a code program that is compiled.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6693,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-338.png?w=524" alt="" class="wp-image-6693"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":6695,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-339.png?w=1024" alt="" class="wp-image-6695"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's transfer the file and use a python decompiler to read the code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6691,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-337.png?w=827" alt="" class="wp-image-6691"/><figcaption class="wp-element-caption">Found the password dMASDNB!!#B!#!#33</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's check for sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6697,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-340.png?w=1024" alt="" class="wp-image-6697"/><figcaption class="wp-element-caption">Able to switch to the root user.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6699,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-341.png?w=479" alt="" class="wp-image-6699"/></figure>
<!-- /wp:image -->
