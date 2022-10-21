<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/greenoptic-1,510/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/greenoptic-1,510/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumeration will lead to two web servers</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Add the 2nd webser to the hosts file to gain access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the dig command to find for other domains</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use burpsuite for a LFI attack on the account page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a hashed credential in .htpasswd</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Crack the hash with John</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login to the recovery page and explore the forum for clues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use burpsuite to check the mail folders for passwords</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Unzip the file and investigate the pcap file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gain server credentials from the pcap file</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SSH into a user and exploit the wireshark application to capture packets</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>A base64 encoded authentication login credential can be found for the root user</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"luminous-vivid-amber","fontSize":"small"} -->
<p class="has-text-align-center has-luminous-vivid-amber-background-color has-background has-small-font-size"><strong>Enumeration</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First step we should do is to enumerate open ports available on the machine. Use NMAP to scan for all of the port first.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6995,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-472.png?w=932" alt="" class="wp-image-6995"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Once all the ports is scanned we can superficially target the open ports to get more information. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6996,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-473.png?w=1024" alt="" class="wp-image-6996"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We have the following ports:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>FTP - We cant get antonymous login.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SSH</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>DNS - There might be other domains available</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>HTTP</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MiniServe - Looks like another web server.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Let's also enumerate the http server with gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6994,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-471.png?w=1024" alt="" class="wp-image-6994"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":6992,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-470.png?w=1024" alt="" class="wp-image-6992"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's investigate the web server on port 10000.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7012,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-478.png?w=906" alt="" class="wp-image-7012"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We found a domain name and we should add the domain name to our /etc/hosts file.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A login page is available. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7014,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-479.png?w=1024" alt="" class="wp-image-7014"/><figcaption class="wp-element-caption">Tried some basic SQL injection but all negative.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since we have a DNS port open let's use dig to find if there are any other domains avalible.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7058,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-503.png?w=653" alt="" class="wp-image-7058"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7019,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-482.png?w=1024" alt="" class="wp-image-7019"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like we get a recoveryplan domain. Add the domain to /etc/hosts and head to the page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7021,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-483.png?w=1024" alt="" class="wp-image-7021"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We don't have any credentials yet. We will come back to this later.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's explore the other pages we found on gobuster. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>/statement.html</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Looks like the company experience a cyber attack and we have a potential user name as in the CEO.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7016,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-480.png?w=1024" alt="" class="wp-image-7016"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/account leads use to a login page. If we look at the URL bar we clearly have an option for LFI injection.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7061,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-504.png?w=549" alt="" class="wp-image-7061"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7010,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-477.png?w=1024" alt="" class="wp-image-7010"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>To use this attack let's activate burpsuite and send the request to repeater. To test if this vulnerability works we can use the classic<strong><em> ../../../../etc/passwd</em></strong> payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7017,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-481.png?w=1024" alt="" class="wp-image-7017"/><figcaption class="wp-element-caption">Looks like we can exploit this vulnerability.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We need to find some credentials for both login pages. Let's check if we can find .htpasswd</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7064,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-505.png?w=401" alt="" class="wp-image-7064"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7023,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-484.png?w=1024" alt="" class="wp-image-7023"/><figcaption class="wp-element-caption">staff:$apr1$YQNFpPkc$rhUZOxRE55Nkl4EDn.1Po.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like we are able to find a user name and a hashed password.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Use john to crack the password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7025,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-485.png?w=967" alt="" class="wp-image-7025"/><figcaption class="wp-element-caption">Password is found.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's login to the recoveryplan domain with the newly found credentials. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7027,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-486.png?w=497" alt="" class="wp-image-7027"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Looks like is some kind of forum board. Let's explore the messages to find for some clues.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7028,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-487.png?w=1024" alt="" class="wp-image-7028"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We found a clue from the user Terry indicating he emailed a password to Sam user that can be use for a zip file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7030,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-488.png?w=1024" alt="" class="wp-image-7030"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Download the zipfile. And let's head back to burpsuite to see if we can view the mail folders of the Sam user to find a password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7034,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-491.png?w=694" alt="" class="wp-image-7034"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7036,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-492.png?w=574" alt="" class="wp-image-7036"/><figcaption class="wp-element-caption">Password found.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I tried to looked at the terry user too. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7031,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-489.png?w=687" alt="" class="wp-image-7031"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found some creds from the Linux server support. It will be handy.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7032,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-490.png?w=700" alt="" class="wp-image-7032"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Once we unzip the file it contains a PCAP file which is a recorded network traffic by WireShark. Follow the TCP stream and we can find credentials for a FTP user. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7038,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-493.png?w=543" alt="" class="wp-image-7038"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's login to the FTP user and we can get a user.txt file but nothing interesting.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7040,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-494.png?w=923" alt="" class="wp-image-7040"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Usually the FTP credentials can be used in SSH. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7041,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-495.png?w=847" alt="" class="wp-image-7041"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We get the first flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7042,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-496.png?w=501" alt="" class="wp-image-7042"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I tried to check for sudo permissions but we are not able to run sudo.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7044,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-497.png?w=737" alt="" class="wp-image-7044"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>When I first check the ID, I notice this user is in the wireshark group. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7048,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-499.png?w=1024" alt="" class="wp-image-7048"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the terminal version of wireshark to capture some packets. I'm going to use the any interface to caputre all packets.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>After sometime I came across a AUTH PLAIN log that has base64 encoded text.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7046,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-498.png?w=1024" alt="" class="wp-image-7046"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I decode the text and it gives us the root password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7050,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-500.png?w=810" alt="" class="wp-image-7050"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Login to the root user via SSH.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7052,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-501.png?w=532" alt="" class="wp-image-7052"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7054,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-502.png?w=1024" alt="" class="wp-image-7054"/></figure>
<!-- /wp:image -->
