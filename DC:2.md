<!-- wp:paragraph -->
<p><a href="https://www.vulnhub.com/entry/dc-2,311/" target="_blank" rel="noreferrer noopener">https://www.vulnhub.com/entry/dc-2,311/</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Enumerate all ports</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Webserver is under wordpress</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use WPscan to enumerate users</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>The first flag gives a clue on using cewl to generate wordlists</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use WPscan with the cewl wordlists to bruteforce</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Find for flag clues in the wordpress admin page</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Login to user via SSH</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Escape the restrictive shell with vi</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Switch to the next user and check for sudo permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Use GTFOBins to gain root access </li>
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

<!-- wp:image {"id":4681,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-305.png?w=660" alt="" class="wp-image-4681"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4682,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-306.png?w=1024" alt="" class="wp-image-4682"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a clue in port 80</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4661,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-295.png?w=1024" alt="" class="wp-image-4661"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We need to use cewl to generate a wordlist.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4669,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-299.png?w=855" alt="" class="wp-image-4669"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4662,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-296.png?w=1024" alt="" class="wp-image-4662"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Since the site runs under wordpress , let's use wpscan to enumerate.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4665,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-297.png?w=709" alt="" class="wp-image-4665"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found 3 users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4667,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-298.png?w=844" alt="" class="wp-image-4667"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use cewl to generate a wordlist.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4671,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-300.png?w=792" alt="" class="wp-image-4671"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Create a user list with the users found in the scan and start another wpscan with the user list wordlists.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4673,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-301.png?w=778" alt="" class="wp-image-4673"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found two passwords.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4675,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-302.png?w=1024" alt="" class="wp-image-4675"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>jerry</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4677,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-303.png?w=1024" alt="" class="wp-image-4677"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found the 2nd flag in pages.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4679,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-304.png?w=1017" alt="" class="wp-image-4679"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>tom user has nothing important inside.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's SSH into the tom user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4684,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-307.png?w=781" alt="" class="wp-image-4684"/><figcaption class="wp-element-caption">Able to gain access but with a restrictive shell.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are only able to use the following commands.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4686,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-308.png?w=464" alt="" class="wp-image-4686"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can use the following commands from GTFOBins</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4688,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-309.png?w=876" alt="" class="wp-image-4688"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Then export the path to escape the restrictive shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4690,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-310.png?w=1024" alt="" class="wp-image-4690"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can switch user to jerry and look at sudo permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4691,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-311.png?w=1024" alt="" class="wp-image-4691"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Check GTFOBins for git exploits. We can use the 2nd option to gain root access.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4693,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-312.png?w=872" alt="" class="wp-image-4693"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4694,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-313.png?w=523" alt="" class="wp-image-4694"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We get the final flag.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4695,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/09/image-314.png?w=713" alt="" class="wp-image-4695"/></figure>
<!-- /wp:image -->
