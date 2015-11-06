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
> One of the most common support request we get is users who aren't getting Gravity Form notification emails in their inbox. While we don't normally support Gravity Forms functionality – instead having users contact the [Gravity Forms support team](https://www.gravityhelp.com/support/) directly – we feel this issue is prevalent and complex enough to discuss.

There's a fine art to configuring your website's emails so they steer clear of spam filters and get delivered to inboxes. The solution involves using the correct settings in Gravity Forms and utilising a dedicated mail delivery service with correctly set up SPF and DKIM DNS records. It sounds complex, but the tools we discuss will make this relatively painless for you to configure.

### Gravity Forms [#gravityforms](#gravityforms){#gravityforms}

![Gravity Forms Notification Setup](https://gpdfv4.pv/app/uploads/2015/10/gravityforms.png)

One of the great things about Gravity Forms is how much freedom and choice the software gives users. But when email is concerned we feel there's not enough guidance for users so we've put together this best-practice guide for you.

When setting up a notification the *From Email* field **must** contain an email address that includes your website's domain name. For instance, if your domain is `www.mynextproperty.info` the email must include `mynextproperty.info` after the `@` symbol. That could be `admin@mynextproperty.info` or `no-reply@mynextproperty.info`. To our knowledge, in terms of mail delivery what's to the left of the `@` symbol doesn't matter. You could use an email that hasn't been set up with your mail server (like our `no-reply@mynextproperty.info` example above), but in most cases you are better off using an email your users can reply to. 

**But what if you want the notification to be from the user?** In this case you should add the user's email address to the *Reply To* field. If you used an invalid email in the *From Email* field but still want to get replies you can enter a valid email in the *Reply To* field as well. With this setup, when a user replies to an email it will be sent to the address in the *Reply To* field, and not the email in the *From Email* field.

### Dedicated Mail Delivery Service [#dedicated-mail-delivery](#dedicated-mail-delivery){#dedicated-mail-delivery}

Having the correct Gravity Forms mail settings is a good start, but it doesn't guarantee your emails will always hit the mark. At the beginning of the article we mentioned SPF and DKIM DNS records. These two records are used by mail servers to verify an email is legitimate and hasn't been sent by a spammer – they're like email border control. All quality mail delivery services will instruct you in how to configure these two DNS records and verify they are set up correctly. The best part is, once you start sending emails through the mail service they will correctly sign all outgoing mail automatically (like an official stamp, or seal of approval) and log the status of all emails.

#### Which Service to Choose? [#which-service-to-choose](#which-service-to-choose){#which-service-to-choose}

There are a number of premium mail services you can choose from, including [Mandrill](http://mandrill.com/), [SendGrid](https://sendgrid.com/) and [Mailjet](https://www.mailjet.com/). However, we recommend [Mailgun](http://www.mailgun.com/) because they have a free tier which allows you to send 10,000 emails per month.

#### Setting up Mailgun [#setting-up-mailgun](#setting-up-mailgun){#setting-up-mailgun}

While Mailgun touts they are the "Email Service For Developers" there's no need to be worried. Yes, they do have a lot of weird looking code samples during the sign up process but you can ignore all that. We're going to configure WordPress to send mail using SMTP.

1.  First, install the [WP Mail SMTP plugin](https://wordpress.org/plugins/wp-mail-smtp/) on your WordPress website and activate the plugin. A new settings page called `Email` will be available under the `Settings` tab, but we're not going to configure the plugin just yet.
1.  Head to [Mailgun's signup page](https://mailgun.com/signup) and fill out the form. It's your standard name, email, password type form. ![Mailgun Signup Page](https://gpdfv4.pv/app/uploads/2015/10/initial-signup.png)
1.  On the next page you'll see it is split into two sections:

    1.  Try Sending An Email From the Sandbox
    1.  Add Your Own Domain

    You can skip the first section and move straight onto `Add Your Domain`. 

    ![Add Domain to Mailgun](https://gpdfv4.pv/app/uploads/2015/10/add-domain.png)

1.  Enter the domain name you want to configure. Mailgun recommends you use a subdomain instead of your top level domain – eg. mail.mynextproperty.info. Click `Add Domain` when completed. 

    ![Add your domain to Mailgun](https://gpdfv4.pv/app/uploads/2015/10/enter-domain.png)

1.  Next you'll need to login to your DNS provider. A lot of the time the company that hosts your website also hosts your DNS, but this isn't always the case. Mailgun will give you detailed instructions on what new DNS settings you need to add. Once you complete the changes it can take 24-48 hours for Mailgun to recognise your new settings (this is a limitation of DNS and not Mailgun). When completed, continue to the next page. 

    ![Mailgun DNS Configuration](https://gpdfv4.pv/app/uploads/2015/10/dns-config.png) 
    ![DNS Setting Setup](https://gpdfv4.pv/app/uploads/2015/10/dns-config-2.png)

1.  Before we go any further you'll need to ensure Mailgun has verified your DNS settings are correct. They have a handy `Check DNS Records Now` button that can be used to ping your current DNS settings. If there are any problems ensure you correct them (remember, it can take 24-48 hours for your changes to be recognised). ![Verify DNS Settings Correct](https://gpdfv4.pv/app/uploads/2015/10/dns-verification.png)

1.  At this stage you should also activate your Mailgun account. To do this find the email they sent to the address provided during signup and click the activation link.

1.  Once your DNS settings are correctly setup we need to get your SMTP details so we can configure WordPress. Under the `Domain Information` section in Mailgun is a link to *Manage SMTP credentials*. Follow the link and you will be taken to your SMTP management area. Click the gear icon next to the existing `postmaster` user and set a password. ![SMTP Setup Link](https://gpdfv4.pv/app/uploads/2015/10/manage-credentials.png) ![Set new Mailgun SMTP password](https://gpdfv4.pv/app/uploads/2015/10/set-smtp-password.png)

1.  Now we can go back to WordPress, navigate to `Settings -> Email` and fill in the credentials. Add a default *From Email* and *From Name* (remembering the instructions we provided in the [#gravityforms](#gravityforms){#gravityforms} section), then go down to the SMTP Options section and use the details provided on the Mailgun SMTP Credentials page. 

    The *SMTP Host* should be `smtp.mailgun.org`, the *SMTP Port* is `25`, leave *Encryption* set to `No encryption` (they force encryption automatically using [STARTTLS](https://en.wikipedia.org/wiki/STARTTLS)), set *Authentication* to `Yes: Use SMTP authentication` and enter your SMTP username and password credentials (the one you set up in the previous step). When done click `Save Changes`. 
    ![Setup STMP settings in WordPress](https://gpdfv4.pv/app/uploads/2015/10/smtp-settings.png)

1. Finally, you can test everything works correctly by sending a test email. This can be done straight from the WordPress SMTP plugin admin page and is found just under the form you completed in the last step. If everything was successful the result should be `bool(true)`. If it wasn't, review the `SMTP debugging output` for hints on what went wrong.

Now sit back and enjoy the fact your emails have the best chance of reaching their intended destination.

#### Do I Really Need This? [#do-I-really-need-this](#do-I-really-need-this){#do-I-really-need-this}

Unless you're a server administrator who can setup a mail server correctly, then yes. You really do need this. To reiterate, these services help ensure **emails are landing in inboxes**, but if there is a problem their analytic tools will let you know what went wrong.
                    