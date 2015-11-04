---
ID: 1473
post_title: PDF Security
author: GravityBot
post_date: 2015-10-20 02:24:48
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-pdf-security/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/access-denied.png" alt="Access Denied to PDF" />

Ensuring your data is protected is our <em>top priority</em> and we've implemented a number of security protocols to prevent unauthorised access to PDF documents generated with Gravity PDF. Also, all PDF rendering is done directly on your web server so no third-party PDF service has access to your data.

Once you've installed the plugin it's <strong>strongly recommended</strong> you review the security settings and <strong>thoroughly test</strong> they are working correctly.

<hr />

<h3>Default Security <a href="#default-security" title="" id="default-security">#default-security</a></h3>

<blockquote>
  <strong>tl;dr</strong> – The default security settings allow the user who submits the entry to view their own PDF. Site Administrators and Network Super Administrators can view all PDFs.
</blockquote>

The software ships with conservative defaults that provides a well-balanced mix of PDF access and security. By default, the following users will be able to access PDFs:

<ol>
<li>Administrator and Super Administrator users (if running multisite) can access all PDFs.</li>
<li>Any user with a <a href="https://codex.wordpress.org/Roles_and_Capabilities">WordPress role</a> that has the <a href="https://www.gravityhelp.com/documentation/article/role-management-guide/"><code>gravity_forms_view_entries</code> capability</a> (by default this is only Administrators and Super Administrators) can access all PDFs. You can change this behaviour by modifying the <a href="https://gpdfv4.pv/v4-docs/global-settings/#user-restriction">User Restrictions</a> option in the global settings, or adding the <code>gravity_forms_view_entries</code> capability to an existing role (use a <a href="https://wordpress.org/plugins/user-role-editor/">role editor plugin</a>).</li>
<li>The original Gravity Form entry owner (the end-user who completed the form) can access their PDF. The protocols used to determine if a user is the owner include:

<ul>
<li>The software will compare the user's IP address against the one stored with the entry and if they match the PDF will be displayed. Because <a href="http://whatismyipaddress.com/keeps-changing">IP addresses do change</a>, a time-based security measure has also been implemented which only allows logged-out user access to the PDF for 30 minutes after submitting the form. This behaviour can be changed using the <a href="https://gpdfv4.pv/v4-docs/global-settings/#logged-out-timeout">Logged Out Timeout</a> option in the global settings. </li>
<li>If the user's IP doesn't match, or the 30-minute timeout window has expired, AND the entry owner was originally logged in when completing the form they will be redirected to a login page. Once authenticated, the software will compare the user's ID with the one stored in the entry. If they match the PDF will be displayed.</li>
</ul></li>
</ol>

To correctly test the owner security policy you'll need to submit a new entry using a web proxy like <a href="https://hide.me/en/proxy">hide.me</a> so that the IP address differs from your own.

<hr />

<h3>PDFs and the File System <a href="#filesystem" title="" id="filesystem">#filesystem</a></h3>

<blockquote>
  <strong>tl;dr</strong> – PDFs stored on the disk have a limited lifespan, and are usually protected from direct access, but it's advisable to use <a href="#">the <code>gfpdf_tmp_directory_location</code> filter</a> to change the PDF directory to somewhere outside your public directory structure.
</blockquote>

Currently, the only time a PDF is actually saved to disk is when it's configured to be <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#notifications">attached to a form's notification(s)</a>, or the <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#save-pdf"><em>Always Save PDF</em> setting</a> is enabled. These PDFs are saved locally to <code>/wp-content/uploads/PDF_EXTENDED_TEMPLATES/tmp</code> by default but are cleaned up automatically from the disk once the Gravity Forms submission process has been completed. Any stray documents older than 12 hours are also automatically cleaned up.

The PDFs are not cached on the file system and they are dynamically generated upon request. Caching is on our features list so this behaviour may change in the future.

<h4>Direct PDF Access <a href="#direct-pdf-access" title="" id="direct-pdf-access">#direct-pdf-access</a></h4>

While we only store PDFs in the <code>tmp</code> directory for short periods, this behaviour may change in future with the introduction of caching. With that in mind, we use a <code>.htaccess</code> file to prevent direct access to those PDFs saved to disk. Users running <strong>Apache</strong> or <strong>LiteSpeed</strong> web servers are <strong>automatically secured</strong>, however Nginx, IIS and other web servers will need manual intervention – refer to your web server manuals on the proper methods to prevent direct file access to a directory. If you aren't sure how to do this see the <a href="#private-pdf-directory">#private-pdf-directory</a> section.

<h4>Private PDF Directory <a href="#private-pdf-directory" title="" id="private-pdf-directory">#private-pdf-directory</a></h4>

The simplest approach to protect the PDFs saved to disk – without having to worry about specific web server configuration – is to move the <code>tmp</code> folder outside the public directory structure. This can be done using the <code>gfpdf_tmp_directory_location</code> filter. Place the following snippet in your theme's <code>functions.php</code> file or create a <a href="https://codex.wordpress.org/Must_Use_Plugins">Must Use plugin</a>.

<pre><code class="php">add_filter( 'gfpdf_tmp_directory_location', function( $path ) {
      return '/private/tmp/directory/path/';
} );
</code></pre>

To test your the filter works correctly submit a new Gravity Form entry and look for the private folder you've set. Inside should be a <code>.htaccess</code> file and a number of PHP files. Once the new location has been verified delete the old <code>tmp</code> directory from your server.

<hr />

<h3>Prevent Owner Access <a href="#prevent-owner-access" title="" id="prevent-owner-access">#prevent-owner-access</a></h3>

If your PDF is never meant to be viewed by the end user you can enable the <a href="#"><em>Prevent Owner Access</em></a> security setting. This will ensure only logged in users with roles assigned the capabilities set in the <a href="https://gpdfv4.pv/v4-docs/global-settings/#user-restriction"><em>User Restriction</em></a> setting have access to the document.

<hr />

<h3>Enable Public Access <a href="#enable-public-access" title="" id="enable-public-access">#enable-public-access</a></h3>

If you want to enable public access to the PDFs generated from your Gravity Form you can do so with the <a href="#"><em>Enable Public Access</em></a> option. Use this option sparingly as it will allow anyone worldwide to access PDFs generated from your form – search engines may even index the documents. In the majority of cases the standard security protocols are sufficient.

<hr />

<h3>Sensitive User Information <a href="#sensitive-user-information" title="" id="sensitive-user-information">#sensitive-user-information</a></h3>

If you are collecting sensitive data from your users there are a number of best-practice protocols you should consider implementing to protect that information. These include:

<ol>
<li>Install an <a href="https://www.namecheap.com/support/knowledgebase/article.aspx/786/38/what-is-an-ssl-certificate-and-what-is-it-used-for">SSL certificate</a> and correctly enable HTTPS on your website. For better trust between you and your users <a href="https://www.namecheap.com/security/ssl-certificates/extended-validation.aspx">you might opt for an EV Certificate</a>. Test your HTTPS implementation by <a href="https://www.ssllabs.com/ssltest/">running an SSL Server test</a> – aim for an "A+".</li>
<li>Use dedicated web hosting (or similar). Ensure the hosting service you choose meets your country's regulations in regard to the data being collected – an example being <a href="http://aws.amazon.com/compliance/">Amazon's Cloud Compliance</a>. </li>
<li>If you collect and store credit card details on your server you should (read: must) <a href="https://www.pcisecuritystandards.org/merchants/">be PCI-compliant</a>. Even if you aren't storing payment details, the user information you are storing may be sensitive enough that you could follow PCI best-practice. </li>
<li>Encrypt your dedicated server's file system as well as the database. </li>
<li>Ensure WordPress and its plugins are regularly updated. </li>
<li>Do not send sensitive user information via email. This includes in the email body or as an attachment. Instead use the <a href="https://gpdfv4.pv/v4-docs/shortcodes/#notifications"><code>[gravitypdf]</code> shortcode</a> to send a link to the PDF, or place a download link <a href="https://gpdfv4.pv/v4-docs/shortcodes/#confirmation">on the confirmation page</a>.</li>
<li>Enable PDF password protection and use a strong password (over 10 characters using a mix of letters, numbers and symbols). PDFs use 128-bit encryption. </li>
<li>Implement strong password policies and two-step authentication for all accounts. </li>
<li>Install security plugins like <a href="https://wordpress.org/plugins/sucuri-scanner/">Sucuri Security</a>, <a href="https://wordpress.org/plugins/wordfence/">Wordfence Security</a> or <a href="https://wordpress.org/plugins/better-wp-security/">iThemes Security</a> (to prevent conflicts only install and run one of these security plugins).</li>
</ol>

The list above is just some of the ways you can keep your website and user data secure. Remember, security is not "set and forget". It is an on-going process and you should remain ever vigilant.