---
ID: 1472
post_title: Increasing Memory Limit
author: GravityBot
post_date: 2015-10-22 00:25:33
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-increasing-memory-limit/
published: true
---
<blockquote>
  The following article is technical in nature so if you don't feel comfortable making changes to files via (s)FTP, or from your hosting control panel, you should contact your web hosting provider for assistance.
</blockquote>

When talking about a <em>memory limit</em> we're referring to PHP's maximum allowed memory per process. That just means the amount of resources your website is aloud to use while processing a request – or in our case, generating a PDF. When we talk about WordPress' maximum memory limit we're really referring to PHP's maximum memory limit.

It's worth explicitly stating that WordPress memory is different to server memory. Your VPS may have 4GB of memory, but WordPress and your web server are only allocated a small portion of this. Below are ways you can try increase your memory limit.

<hr />

<h3>wp-config.php <a href="#wp-config" title="" id="wp-config">#wp-config</a></h3>

Edit your WordPress <code>wp-config.php</code> file and add the following before the <code>/* That's all, stop editing! Happy blogging. */</code> line:

<pre><code class="php">define('WP_MEMORY_LIMIT', '128M');
</code></pre>

More details about the <code>WP_MEMORY_LIMIT</code> constant <a href="http://codex.wordpress.org/Editing_wp-config.php#Increasing_memory_allocated_to_PHP">can be found in the WordPress documentation</a>.

<hr />

<h3>php.ini <a href="#php-ini" title="" id="php-ini">#php-ini</a></h3>

If you have access to your <code>php.ini</code> file change the <code>memory_limit</code> line to the following:

<pre><code>memory_limit = 128M;
</code></pre>

A lot of shared and managed hosting don't allow you to edit the main <code>php.ini</code> file, but some do allow you to upload your own version which overrides these parameters. Check your web hosting provider's documentation to see if they support this.

<hr />

<h3>.htaccess <a href="#htaccess" title="" id="htaccess">#htaccess</a></h3>

If none of the above two options work you can try change the memory limit using the <code>.htaccess</code> file. Be aware that if this doesn't work <strong>it may cause a 500 Internal Server Error</strong> (remove the line if this happens).

<pre><code>php_value memory_limit 128M
</code></pre>

<hr />

<h3>Contact Hosting Provider <a href="#contact-hosting-provider" title="" id="contact-hosting-provider">#contact-hosting-provider</a></h3>

If none of the methods above work for you then get in touch with your web hosting provider and ask them for assistance.