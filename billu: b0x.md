<!-- wp:paragraph -->
<p>Download the machine:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/billu-b0x,188/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/billu-b0x,188/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Overview</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Web enumenration will lead to a login page that suggests to use SQLI</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SQLI payloads do not work</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find a page that is able to use Local file read</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use the curl command to find credentials for a sql server</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login into the server and find creds for the main page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Check the server config files to find creds for root access</li>
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

<!-- wp:image {"id":7134,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-524.png?w=699" alt="" class="wp-image-7134"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7135,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-525.png?w=1024" alt="" class="wp-image-7135"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7136,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-526.png?w=1024" alt="" class="wp-image-7136"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7137,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-527.png?w=1024" alt="" class="wp-image-7137"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since the page indicates to use SQLI, I tried with some payloads but results were negative. Let's explore the other pages found on the directory enumeration.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>/ test</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7142,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-530.png?w=673" alt="" class="wp-image-7142"/><figcaption class="wp-element-caption">Looks like there is a possibility to test for a LFI vulnerability. </figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong><em>** I found this is not  LFI vulnerability as it only read files and not execute code. So its a Local file read vulnerability. </em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Test LFI vulnerability with the curl command.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7141,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-529.png?w=896" alt="" class="wp-image-7141"/><figcaption class="wp-element-caption">We are able to use LFI exploits.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's check if we can get some information on the SQLI restrictions by curling the index.php page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7145,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-531.png?w=1024" alt="" class="wp-image-7145"/><figcaption class="wp-element-caption">Seems that we need to add "\" in our payloads.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I tried with few payloads but still unable to get pass. So I decided to curl the c.php and head.php files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7147,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-532.png?w=728" alt="" class="wp-image-7147"/><figcaption class="wp-element-caption">Looks like we have some mysql credentials.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>But we need to find a mysql login page first. Let's use a bigger list in our web enumeration.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Looks like we found it.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7149,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-533.png?w=803" alt="" class="wp-image-7149"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7151,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-534.png?w=1024" alt="" class="wp-image-7151"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can login the creds found in the c.php file.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7152,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-535.png?w=1024" alt="" class="wp-image-7152"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the auth database and we can get some creds.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7154,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-536.png?w=979" alt="" class="wp-image-7154"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use these creds to login to the main page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7156,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-537.png?w=1024" alt="" class="wp-image-7156"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>However after some time adding and checking the users, I'm not able to get any leads. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try searching for the standard config file in phpmy.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7158,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-538.png?w=937" alt="" class="wp-image-7158"/><figcaption class="wp-element-caption">Looks like we got root creds.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>It actually works.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":7160,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-539.png?w=778" alt="" class="wp-image-7160"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":7161,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/10/image-540.png?w=845" alt="" class="wp-image-7161"/></figure>
<!-- /wp:image -->
