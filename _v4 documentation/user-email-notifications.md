---
ID: 1724
post_title: Email Notifications
author: GravityBot
post_date: 2015-10-22 03:27:46
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-email-notifications/
published: true
---
<blockquote>
  One of the most common support request we get is users who aren't getting Gravity Form notification emails in their inbox. While we don't normally support Gravity Forms functionality – instead having users contact the <a href="https://www.gravityhelp.com/support/">Gravity Forms support team</a> directly – we feel this issue is prevalent and complex enough to discuss.
</blockquote>

There's a fine art to configuring your website's emails so they steer clear of spam filters and get delivered to inboxes. The solution involves using the correct settings in Gravity Forms and utilising a dedicated mail delivery service with correctly set up SPF and DKIM DNS records. It sounds complex, but the tools we discuss will make this relatively painless for you to configure.

<h3>Gravity Forms <a href="#gravityforms" title="" id="gravityforms">#gravityforms</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/gravityforms.png" alt="Gravity Forms Notification Setup" />

One of the great things about Gravity Forms is how much freedom and choice the software gives users. But when email is concerned we feel there's not enough guidance for users.

When setting up a notification the <em>From Email</em> field <strong>must</strong> contain an email address that includes your website's domain name. For instance, if your domain is <code>www.mynextproperty.info</code> the email must include <code>mynextproperty.info</code> after the <code>@</code> symbol. That could be <code>admin@mynextproperty.info</code> or <code>no-reply@mynextproperty.info</code>. To our knowledge, in terms of mail delivery what's to the left of the <code>@</code> symbol doesn't matter. You could use an email that hasn't been set up with your mail server (like our <code>no-reply@mynextproperty.info</code> example above), but in most cases you are better off using an email your users can reply to.

<strong>But what if you want the notification to be from the user?</strong> In this case you should add the user's email address to the <em>Reply To</em> field. If you used an invalid email in the <em>From Email</em> field but still want to get replies you can enter a valid email in the <em>Reply To</em> field as well. With this setup, when a user replies to an email it will be sent to the address in the <em>Reply To</em> field, and not the email in the <em>From Email</em> field.

<h3>Dedicated Mail Delivery Service <a href="#dedicated-mail-delivery" title="" id="dedicated-mail-delivery">#dedicated-mail-delivery</a></h3>

Having the correct Gravity Forms mail settings is a good start, but it doesn't guarantee your emails will always hit the mark. At the beginning of the article we mentioned SPF and DKIM DNS records. These two records are used by mail servers to verify an email is legitimate and hasn't been sent by a spammer – they're like email border control. All quality mail delivery services will instruct you in how to configure these two DNS records and verify they are set up correctly. The best part is, once you start sending emails through the mail service they will correctly sign all outgoing mail automatically (like an official stamp, or seal of approval) and log the status of all emails.

<h4>Which Service to Choose? <a href="#which-service-to-choose" title="" id="which-service-to-choose">#which-service-to-choose</a></h4>

There are a number of premium mail services you can choose from, including <a href="http://mandrill.com/">Mandrill</a>, <a href="https://sendgrid.com/">SendGrid</a> and <a href="https://www.mailjet.com/">Mailjet</a>. However, we recommend <a href="http://www.mailgun.com/">Mailgun</a> because they have a free tier which allows you to send 10,000 emails per month.

<h4>Setting up Mailgun <a href="#setting-up-mailgun" title="" id="setting-up-mailgun">#setting-up-mailgun</a></h4>

While Mailgun touts they are the "Email Service For Developers" there's no need to be worried. Yes, they do have a lot of weird looking code samples during the sign up process but you can ignore all that. We're going to configure WordPress to send mail using SMTP.

<ol>
<li>First, install the <a href="https://wordpress.org/plugins/wp-mail-smtp/">WP Mail SMTP plugin</a> on your WordPress website and activate the plugin. A new settings page called <code>Email</code> will be available under the <code>Settings</code> tab, but we're not going to configure the plugin just yet. </li>
<li>Head to <a href="https://mailgun.com/signup">Mailgun's signup page</a> and fill out the form. It's your standard name, email, password type form. 
<img src="https://gpdfv4.pv/app/uploads/2015/10/initial-signup.png" alt="Mailgun Signup Page" /></p></li>
<li><p>On the next page you'll see it is split into two sections:

<ol>
<li>Try Sending An Email From the Sandbox</li>
<li>Add Your Own Domain</li>
</ol>

You can skip the first section and move straight onto <code>Add Your Domain</code>.
<img src="https://gpdfv4.pv/app/uploads/2015/10/add-domain.png" alt="Add Domain to Mailgun" title="" class="aligncenter" /></p></li>
<li><p>Enter the domain name you want to configure. Mailgun recommends you use a subdomain instead of your top level domain – eg. mail.mynextproperty.info. Click <code>Add Domain</code> when completed.
<img src="https://gpdfv4.pv/app/uploads/2015/10/enter-domain.png" alt="Add your domain to Mailgun" /></p></li>
<li><p>Next you'll need to login to your DNS provider. A lot of the time the company that hosts your website also hosts your DNS, but this isn't always the case. Mailgun will give you detailed instructions on what new DNS settings you need to add. Once you complete the changes it can take 24-48 hours for Mailgun to recognise your new settings (this is a limitation of DNS and not Mailgun). When completed, continue to the next page.
<img src="https://gpdfv4.pv/app/uploads/2015/10/dns-config.png" alt="Mailgun DNS Configuration" />
<img src="https://gpdfv4.pv/app/uploads/2015/10/dns-config-2.png" alt="DNS Setting Setup" /></p></li>
<li><p>Before we go any further you'll need to ensure Mailgun has verified your DNS settings are correct. They have a handy <code>Check DNS Records Now</code> button that can be used to ping your current DNS settings. If there are any problems ensure you correct them (remember, it can take 24-48 hours for your changes to be recognised). 
<img src="https://gpdfv4.pv/app/uploads/2015/10/dns-verification.png" alt="Verify DNS Settings Correct" title="" class="aligncenter" /></p></li>
<li><p>At this stage you should also activate your Mailgun account. To do this find the email they sent to the address provided during signup and click the activation link.</p></li>
<li><p>Once your DNS settings are correctly setup we need to get your SMTP details so we can configure WordPress. Under the <code>Domain Information</code> section is a link to <em>Manage SMTP credentials</em>. Follow the link and you will be taken to your SMTP management area. Click the gear icon next to the existing <code>postmaster</code> user and set a password. 
<img src="https://gpdfv4.pv/app/uploads/2015/10/manage-credentials.png" alt="SMTP Setup Link" title="" class="aligncenter" />
<img src="https://gpdfv4.pv/app/uploads/2015/10/set-smtp-password.png" alt="Set new Mailgun SMTP password" /></p></li>
<li><p>Now we can go back to WordPress, navigate to <code>Settings -&gt; Email</code> and fill in the credentials. Add a default <em>From Email</em> and <em>From Name</em> (remembering the instructions we provided in the <a href="#gravityforms">#gravityforms</a> section), then go down to the SMTP Options section and use the details provided on the Mailgun SMTP Credentials page. The <em>SMTP Host</em> should be <code>smtp.mailgun.org</code>, the <em>SMTP Port</em> is <code>25</code>, leave <em>Encryption</em> set to <code>No encryption</code> (they force encryption automatically using <a href="https://en.wikipedia.org/wiki/STARTTLS">STARTTLS</a>), set <em>Authentication</em> to <code>Yes: Use SMTP authentication</code> and enter your SMTP username and password credentials (the one you set up in the previous step). When done click <code>Save Changes</code>.
<img src="https://gpdfv4.pv/app/uploads/2015/10/smtp-settings.png" alt="Setup STMP settings in WordPress" /></p></li>
<li><p>Finally, you can test everything works correctly by sending a test email. This can be done straight from the WordPress SMTP plugin admin page and is found just under the form you completed in the last step. If everything was successful the result should be <code>bool(true)</code>. If it wasn't, review the <code>SMTP debugging output</code> for hints on what went wrong.</p></li>
</ol>

<p>Now sit back and enjoy the fact your emails have the best chance of reaching their intended destination.

<h4>Do I Really Need This? <a href="#do-I-really-need-this" title="" id="do-I-really-need-this">#do-I-really-need-this</a></h4>

Unless you're a server administrator who can setup a mail server correctly, then yes. You really do need this. To reiterate, these services help ensure <strong>emails are landing in inboxes</strong>, but if there is a problem their analytic tools will let you know what went wrong.