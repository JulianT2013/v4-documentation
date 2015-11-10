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
> The following article is technical in nature so if you don't feel comfortable making changes to files via (s)FTP, or from your hosting control panel, you should contact your web hosting provider for assistance.

When talking about a *memory limit* we're referring to PHP's maximum allowed memory per process. That just means the amount of resources your website is aloud to use while processing a request – or in our case, generating a PDF. When we talk about WordPress' maximum memory limit we're really referring to PHP's maximum memory limit. 

It's worth explicitly stating that WordPress memory is different to server memory. Your VPS may have 4GB of memory, but WordPress and your web server are only allocated a small portion of this. Below are ways you can try increase your memory limit.

---

### wp-config.php [#wp-config](#wp-config){#wp-config}

Edit your WordPress `wp-config.php` file and add the following before the `/* That's all, stop editing! Happy blogging. */` line:

```{.language-php}
define('WP_MEMORY_LIMIT', '128M');
```

More details about the `WP_MEMORY_LIMIT` constant [can be found in the WordPress documentation](http://codex.wordpress.org/Editing_wp-config.php#Increasing_memory_allocated_to_PHP).

---

### php.ini [#php-ini](#php-ini){#php-ini}

If you have access to your `php.ini` file change the `memory_limit` line to the following:

```
memory_limit = 128M;
```

A lot of shared and managed hosting don't allow you to edit the main `php.ini` file, but some do allow you to upload your own version which overrides these parameters. Check your web hosting provider's documentation to see if they support this.

---

### .htaccess [#htaccess](#htaccess){#htaccess}

If none of the above two options work you can try change the memory limit using the `.htaccess` file. Be aware that if this doesn't work **it may cause a 500 Internal Server Error** (remove the line if this happens).

```
php_value memory_limit 128M
```

---

### Contact Hosting Provider [#contact-hosting-provider](#contact-hosting-provider){#contact-hosting-provider}

If none of the methods above work for you then get in touch with your web hosting provider and ask them for assistance.