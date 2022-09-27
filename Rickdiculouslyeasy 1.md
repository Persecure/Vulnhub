#RickdiculouslyEasy :1
<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/rickdiculouslyeasy-1,207/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/rickdiculouslyeasy-1,207/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Explore the various ports to find flags</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FTP server can be accessed anonymously for a flag</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Web server enumeration will lead to a password and flag</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use command injection to find users </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Access a user and examine other users files </li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Transfer other user's file to attacking machine to find for clues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Create a password list with the clues given</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check sudo permissions for privelidge exploitation</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use Hacktricks for root access</li>
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

<!-- wp:image {"id":5277,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-529.png?w=670" alt="" class="wp-image-5277"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5281,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-531.png?w=747" alt="" class="wp-image-5281"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5282,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-532.png?w=731" alt="" class="wp-image-5282"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>FTP Server</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Able to access it annoymously.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5293,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-539.png?w=697" alt="" class="wp-image-5293"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5294,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-540.png?w=561" alt="" class="wp-image-5294"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:paragraph -->
<p>Port 9090</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5301,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-543.png?w=1024" alt="" class="wp-image-5301"/><figcaption class="wp-element-caption">Found a flag</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Unable to do much with he website as there is no login or password input.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Port 13337</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5303,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-544.png?w=523" alt="" class="wp-image-5303"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Port 60000</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Netcat into the port to find a flag</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5309,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-547.png?w=567" alt="" class="wp-image-5309"/></figure>
<!-- /wp:image --></div>
<!-- /wp:group -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5279,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-530.png?w=1024" alt="" class="wp-image-5279"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5284,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-533.png?w=1024" alt="" class="wp-image-5284"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/robots.txt</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5286,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-534.png?w=519" alt="" class="wp-image-5286"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5298,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-541.png?w=617" alt="" class="wp-image-5298"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5300,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-542.png?w=709" alt="" class="wp-image-5300"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's test for command injection.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5310,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-548.png?w=741" alt="" class="wp-image-5310"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Able to find a password list but when we cat we get a literal picture of a cat. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5312,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-549.png?w=455" alt="" class="wp-image-5312"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Tried to use alternatives like head and tail and no luck.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5314,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-550.png?w=458" alt="" class="wp-image-5314"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use the tail command to check for users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5315,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-551.png?w=548" alt="" class="wp-image-5315"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>/passwords</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5287,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-535.png?w=557" alt="" class="wp-image-5287"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5288,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-536.png?w=644" alt="" class="wp-image-5288"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a password in the source code.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5290,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-537.png?w=778" alt="" class="wp-image-5290"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5291,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-538.png?w=510" alt="" class="wp-image-5291"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try to ssh into the summer user with the password found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5317,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-552.png?w=1024" alt="" class="wp-image-5317"/><figcaption class="wp-element-caption">access gained</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a flag</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5321,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-554.png?w=711" alt="" class="wp-image-5321"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Head to the Morty directory and there are two files. Let's send this file over to the attacking machine to examine.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5322,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-555.png?w=717" alt="" class="wp-image-5322"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the attacking machine , I use cat on the image to find a password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5324,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-556.png?w=1024" alt="" class="wp-image-5324"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use that password to unzip the zipped file and you will get a cluse and a flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5326,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-557.png?w=1024" alt="" class="wp-image-5326"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Head to RickSanchez folder and get the safe file into your attacking machine. Run the executable and use the previous flag number as an argument. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5327,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-558.png?w=1024" alt="" class="wp-image-5327"/><figcaption class="wp-element-caption">we get a flag and a clue for a password</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Cracking Rick's password</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I googled Rick's band.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5329,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-559.png?w=736" alt="" class="wp-image-5329"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Now we need to generate a passwordlist that contains clues given to us.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's use maskprocessor aka m64 to generate a wordlist</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5334,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-561.png?w=942" alt="" class="wp-image-5334"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5335,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-562.png?w=573" alt="" class="wp-image-5335"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5333,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-560.png?w=690" alt="" class="wp-image-5333"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After some time I'm unable to get the password. I tried again with capital letters for the band's name.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5337,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-563.png?w=549" alt="" class="wp-image-5337"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Cracked the password !</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5339,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-564.png?w=1024" alt="" class="wp-image-5339"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ssh into the new user</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5421,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-587.png?w=1024" alt="" class="wp-image-5421"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Check for sudo permissions</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5423,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-588.png?w=808" alt="" class="wp-image-5423"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5425,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-589.png?w=800" alt="" class="wp-image-5425"/><figcaption class="wp-element-caption">Used hacktricks for some clues.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root accessed gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5427,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-590.png?w=859" alt="" class="wp-image-5427"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a flag in the root folder</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5429,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-591.png?w=737" alt="" class="wp-image-5429"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Flags Obtained</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>FLAG{Whoa this is unexpected} - 10 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG{Yeah d- just don't do it.} - 10 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG {There is no Zeus, in your face!} - 10 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG:{TheyFoundMyBackDoorMorty} - 10Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG{Flip the pickle Morty!} - 10 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG{Get off the high road Summer!} - 10 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG: {131333} - 20 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG{And Awwwaaaaayyyy we Go!} - 20 Points</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>FLAG: {Ionic Defibrillator} - 30 points</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->
