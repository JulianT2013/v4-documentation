---
ID: 1473
post_title: PDF Security
author: GravityBot
post_date: 2015-10-20 02:24:48
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/documentation/v4/user-pdf-security/
published: true
kodex_post_likes_count:
  - "0"
kodex_post_dislikes_count:
  - "0"
---
![Access Denied to PDF](https://gpdfv4.pv/app/uploads/2015/10/access-denied.png) 

Ensuring your data is protected is our *top priority* and we've implemented a number of security protocols to prevent unauthorised access to PDF documents generated with Gravity PDF. Also, all PDF rendering is done directly on your web server so no third-party PDF service has access to your data. 

Once you've installed the plugin it's **strongly recommended** you review the security settings and **thoroughly test** they are working correctly.

---

### Default Security [#default-security](#default-security){#default-security}

> **tl;dr** – The default security settings allow the user who submits the entry to view their own PDF. Site Administrators and Network Super Administrators can view all PDFs.

The software ships with conservative defaults that provides a well-balanced mix of PDF access and security. By default, the following users will be able to access PDFs:

1. Administrator and Super Administrator users (if running multisite) can access all PDFs.

1. Any user with a [WordPress role](https://codex.wordpress.org/Roles_and_Capabilities) that has the [`gravity_forms_view_entries` capability](https://www.gravityhelp.com/documentation/article/role-management-guide/) (by default this is only Administrators and Super Administrators) can access all PDFs. You can change this behaviour by modifying the [User Restrictions](https://gpdfv4.pv/v4-docs/global-settings/#user-restriction) option in the global settings, or adding the `gravity_forms_view_entries` capability to an existing role (use a [role editor plugin](https://wordpress.org/plugins/user-role-editor/)).

1. The original Gravity Form entry owner (the end-user who completed the form) can access their PDF. The protocols used to determine if a user is the owner include:
    * The software will compare the user's IP address against the one stored with the entry and if they match the PDF will be displayed. Because [IP addresses do change](http://whatismyipaddress.com/keeps-changing), a time-based security measure has also been implemented which only allows logged-out user access to the PDF for 30 minutes after submitting the form. This behaviour can be changed using the [Logged Out Timeout](https://gpdfv4.pv/v4-docs/global-settings/#logged-out-timeout) option in the global settings.
    * If the user's IP doesn't match, or the 30-minute timeout window has expired, AND the entry owner was originally logged in when completing the form they will be redirected to a login page. Once authenticated, the software will compare the user's ID with the one stored in the entry. If they match the PDF will be displayed.

To correctly test the owner security policy you'll need to submit a new entry using a web proxy like [hide.me](https://hide.me/en/proxy) so that the IP address differs from your own.

---

### PDFs and the File System [#filesystem](#filesystem){#filesystem}

> **tl;dr** – PDFs stored on the disk have a limited lifespan, and are usually protected from direct access, but it's advisable to use [the `gfpdf_tmp_directory_location` filter](#) to change the PDF directory to somewhere outside your public directory structure.

Currently, the only time a PDF is actually saved to disk is when it's configured to be [attached to a form's notification(s)](https://gpdfv4.pv/v4-docs/setup-pdf/#notifications), or the [*Always Save PDF* setting](https://gpdfv4.pv/v4-docs/setup-pdf/#save-pdf) is enabled. These PDFs are saved locally to `/wp-content/uploads/PDF_EXTENDED_TEMPLATES/tmp` by default but are cleaned up automatically from the disk once the Gravity Forms submission process has been completed. Any stray documents older than 12 hours are also automatically cleaned up. 

The PDFs are not cached on the file system and they are dynamically generated upon request. Caching is on our features list so this behaviour may change in the future.

#### Direct PDF Access [#direct-pdf-access](#direct-pdf-access){#direct-pdf-access}

While we only store PDFs in the `tmp` directory for short periods, this behaviour may change in future with the introduction of caching. With that in mind, we use a `.htaccess` file to prevent direct access to those PDFs saved to disk. Users running **Apache** or **LiteSpeed** web servers are **automatically secured**, however Nginx, IIS and other web servers will need manual intervention – refer to your web server manuals on the proper methods to prevent direct file access to a directory. If you aren't sure how to do this see the [#private-pdf-directory](#private-pdf-directory) section.

#### Private PDF Directory [#private-pdf-directory](#private-pdf-directory){#private-pdf-directory}

The simplest approach to protect the PDFs saved to disk – without having to worry about specific web server configuration – is to move the `tmp` folder outside the public directory structure. This can be done using the `gfpdf_tmp_directory_location` filter. Place the following snippet in your theme's `functions.php` file or create a [Must Use plugin](https://codex.wordpress.org/Must_Use_Plugins).

```{.language-php}
add_filter( 'gfpdf_tmp_directory_location', function( $path ) {
      return '/private/tmp/directory/path/';
} );
```

To test the filter works correctly submit a new Gravity Form entry and look for the private folder you've set. Inside should be a `.htaccess` file and a number of PHP files. Once the new location has been verified delete the old `tmp` directory from your server.

---

### Prevent Owner Access [#prevent-owner-access](#prevent-owner-access){#prevent-owner-access}

If your PDF is never meant to be viewed by the end user you can enable the [*Restrict Owner* (TODO: add field to individual PDF)](#) security setting. This will ensure only logged in users with roles assigned the capabilities set in the [*User Restriction*](https://gpdfv4.pv/v4-docs/global-settings/#user-restriction) setting have access to the document.

---

### Enable Public Access [#enable-public-access](#enable-public-access){#enable-public-access}

If you want to enable public access to the PDFs generated from your Gravity Form you can do so with the [*Enable Public Access*](https://gpdfv4.pv/v4-docs/user-setup-pdf/#enable-public-access) option. Use this option sparingly as it will allow anyone worldwide to access PDFs generated from your form – search engines may even index the documents (but are discouraged to do so). In the majority of cases the standard security protocols are sufficient.

---

### Sensitive User Information [#sensitive-user-information](#sensitive-user-information){#sensitive-user-information}

If you are collecting sensitive data from your users there are a number of best-practice protocols you should consider implementing to protect that information. These include:

1. Install an [SSL certificate](https://www.namecheap.com/support/knowledgebase/article.aspx/786/38/what-is-an-ssl-certificate-and-what-is-it-used-for) and correctly enable HTTPS on your website. For better trust between you and your users [you might opt for an EV Certificate](https://www.namecheap.com/security/ssl-certificates/extended-validation.aspx). Test your HTTPS implementation by [running an SSL Server test](https://www.ssllabs.com/ssltest/) – aim for an "A+".

1. Use dedicated web hosting (or similar). Ensure the hosting service you choose meets your country's regulations in regard to the data being collected – an example being [Amazon's Cloud Compliance](http://aws.amazon.com/compliance/).

1. If you collect and store credit card details on your server you should (read: must) [be PCI-compliant](https://www.pcisecuritystandards.org/merchants/). Even if you aren't storing payment details, the user information you are storing may be sensitive enough that you could follow PCI best-practice.

1. Encrypt your dedicated server's file system as well as the database.

1. Ensure WordPress and its plugins are regularly updated.

1. Do not send sensitive user information via email. This includes in the email body or as an attachment. Instead use the [`[gravitypdf]` shortcode](https://gpdfv4.pv/v4-docs/shortcodes/#notifications) to send a link to the PDF, or place a download link [on the confirmation page](https://gpdfv4.pv/v4-docs/shortcodes/#confirmation).

1. Enable PDF password protection and use a strong password (over 10 characters using a mix of letters, numbers and symbols). PDFs use 128-bit encryption.

1. Implement strong password policies and two-step authentication for all accounts.

1. Install security plugins like [Sucuri Security](https://wordpress.org/plugins/sucuri-scanner/), [Wordfence Security](https://wordpress.org/plugins/wordfence/) or [iThemes Security](https://wordpress.org/plugins/better-wp-security/) (to prevent conflicts only install and run one of these security plugins).

The list above is just some of the ways you can keep your website and user data secure. Remember, security is not "set and forget". It is an on-going process and you should remain ever vigilant.