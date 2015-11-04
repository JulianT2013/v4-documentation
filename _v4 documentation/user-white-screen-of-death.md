---
ID: 1722
post_title: White Screen of Death
author: GravityBot
post_date: 2015-10-22 03:26:47
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-white-screen-of-death/
published: true
---
If you are experiencing the "white screen of death", or when submitting Gravity Forms the page loads endlessly, you should follow these steps to try resolve the problem:

<ol>
<li>If you are <strong>unable to access your WordPress admin area</strong> you should FTP into your website and rename or delete the <code>/wp-content/plugins/gravity-forms-pdf-extended</code> folder. Once done, attempt to access your admin area again. This technique will automatically disable Gravity PDF so if it's the problem you should get access back to your website (try refresh the page a couple of times if the problem persists).</p></li>
<li><p>If the you still have full or partial access to your admin area you can verify Gravity PDF is the problem by disabling it on your plugins page. If the problem persists after disabling the software then the issue is unrelated to Gravity PDF. When this is the case you should disable all plugins then enable them one by one until you discover the problem plugin.</p></li>
<li><p>Once you've determined Gravity PDF is the issue, you'll want to review your error logs. If you are unsure where to find these you can enable error logging in your browser:

<ol>
<li>FTP into your website and download the <code>wp-config.php</code> file. </li>
<li>Look for the line <code>define('WP_DEBUG', false);</code> and change <code>false</code> to <code>true</code>. If the line is not present in the file you can add it to the top of the file (on the line after <code>&lt;?php</code>). </li>
<li>Save then upload the file back to your server. If it worked you'll start seeing PHP errors at the top of your browser window which can help you debug the issue.</li>
</ol></li>
<li>If the problem occurs when submitting a Gravity Form first ensure AJAX is disabled by removing <code>ajax="true"</code> from the <code>[gravityform]</code> shortcode. Once done, submit the form and review the error messages to help you debug the problem.</p></li>
<li><p>If the problem occurs while viewing the PDF then view the PDF from your admin area and review the error messages to help you debug the problem.</p></li>
<li><p>Once finished set <code>WP_DEBUG</code> back to <code>false</code> in your <code>wp-config.php</code> file and upload the file.</p></li>
</ol>

<p>If you are unsure how to resolve the errors <a href="#">get in touch with our support team</a> and our friendly staff will provide feedback on how you can resolve the issue.