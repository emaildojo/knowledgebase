---
title: "Gmail Spam Smtp Error Codes and Solutions"
date: 2023-03-20T21:28:22+05:30
draft: false 
# cover:
#   image: ''
#   alt: 'Solution info banner'
#   caption: 'Solutions to spam smtp error'
tags: ["gmail", "smtp"]
categories: ["tech"]
author: ['hitesh pandey']
---

## Introduction

Often times we have delivery issues like rejected and dropped emails, and emails landing in spam. Usually, it takes a while for us to understand that these issues have occurred, and until then some damage is done either to the campaign result or the domain reputation which can be noticed earlier by fetching SMTP response codes.

In this blog, we are focusing on the response codes that are related to spam emails. This will help you to immediately act on the situations that may arise due to something going really wrong with your emails or your email sending domain. 

## FAQS
* [Error code 421 4.7.0 - Not in the whitelist, Authentication issue, Spam](#error-code-421-470---not-in-the-whitelist-authentication-issue-spam)
* [Error code 550 5.7.1 - Blocked, Marked as spam, Authentication](#.)
* [Error code 550 5.2.1 - Email sending limit reached](#.)
* [Error code 550 5.7.26 - DMARC policy failed](#.)
* [Error code 550 5.7.26 - SPF DKIM policy alignment failed](#.)
* [Error code 550 5.2.2 - SPF policy alignment failed](#.)

## Error code 421 4.7.0 - Not in the whitelist, Authentication issue, Spam

```
421-4.7.0 This message does not have authentication information or fails to pass authentication checks. To best protect our users from spam, the message has been blocked. Please visit https://support.google.com/mail/answer/81126#authentication for more information.
```

You may have issues with your SPF, DKIM, and DMARC alignment which is a part of Gmail's email authentication, you can check our detailed tutorials for that. Gmail has a strict policy for these and does that to prevent the Gmail users from any kind of malicious activities.

### Solution
* You can use checker tools to identify the issues and generate records.
  - [SPF Validator](#.)
  - [SPF Generator](#.)
  - [DKIM Validator](#.)
  - [DKIM Generator](#.)
  - [DMARC Validator](#.)
  - [DMARC Generator](#.)


* You can use checker tools to identify the issues and generate records.
  - [SPF](#.)
  - [DKIM](#.)
  - [DMARC](#.)

```
421-4.7.0 Our system has detected an unusual rate of unsolicited mail originating from your IP address. To protect our users from spam, mail sent from your IP address has been temporarily blocked. For more information
```

Your domain is being blocked because of being identified as spam or due to a drastic increase in email sending rates.

### Solution
* You can use checker tools to identify the issues and generate records.
  - Get your domain and IP checked if it is in an email blocklist
  - If in case it is in the blocklist, you will need to fix the issues with the email in the first place.
  - After a successful resolution of email issues, you can go for delisting of the domain/IP from the respective blocklist. You can take the assistance of the email tester for that. 

### A New email sending domain
- In case you have a relatively new email sending domain that is less than a year old, then it is not wise to send millions of emails on the first go. This is a sure way of getting marked as spam mail. You need to increase your email volume slowly if you are sending emails through a new domain. 
- Contact your Mail service providers, they will help you with this process called email warmup. This will make it easier for you to send emails and increase volume.

```
421-4.7.0 Our system has detected an unusual rate of unsolicited mail originating from your IP address. To protect our users from spam, mail sent from your IP address has been temporarily blocked. For more information
```
- This states that you are sending emails to an email id of which the user has created a whitelist, Which means that it will only allow emails from the domain that are explicitly mentioned by the owner of that particular email id.

### solution:-
-The only way this could be resolved is if somehow the email id admin adds your IP to the allowed list.
- You should immediately remove this user from your campaign list since they clearly don't want anyone else emailing them but a few exceptions.
- If possible you can contact the owner of the particular mail id to allow you into the valid sender whitelist, so that your emails won't get rejected.

## Error code 550 5.7.1 - Blocked, Marked as spam, Authentication
- Messages are rejected because the sending server's IP address is on an IP suspended list, it also can be that your sending domain is listed. You might get this error if you're sending mail using a shared IP with a poor reputation (which means you are on an email blacklist or being identified as spam due to being in a spam folder or bad email practices).
- This can also be due to the GCDP (Google Custom Domain Policies). This means that a user has set a custom policy that has denied your domain from being able to send email to the respective email id.
- The email content is another thing that you want to check out if your emails are landing in spam. The issues such as Mixed content, Spam keywords, Phishing links in the email, Non SSH links, External links in the email, and email size can be some of the issues that might cause an email to be marked as spam.

### Examples:-

Here are some of the examples of the error messages you might see.
```
550-5.7.1 Our system has detected that this message is likely unsolicited mail. To reduce the amount of spam sent to Gmail, this message has been blocked.
```

```
550-5.7.1 [XXX.XXX.XXX.XXX] Our system has detected an unusual rate of unsolicited mail originating from your IP address. To protect our users from spam, mail sent from your IP address has been blocked.
```

Your emails are probably being considered by the Gmail anti-spam filters as spam. This might affect All of your emails/Only a few emails/a Moderate amounts of emails.

### solution:-
- Check if your domain IP or domain is listed in the blocklist.
- In case it is listed, Find the reason why your domain or IP is listed on the blocklist. And remove the emails from the listing.

Here are some pointers on how you can identify issues with your email:
- Check your email domain authentication setup:- I.e SPF, DKIM, DMARC setup is valid or not. Gmail may reject many bulk emails that are not mail authentication compliant. Gmail checks these parameters to prevent any unwanted spam, phishing, and harmful emails from being sent to their users.
- Send emails to only opt-in users:- 
What does this mean? It means you send emails to the users who have subscribed/ requested emails from you and are expecting some emails from you. This will make sure your emails get opened, and plus they won’t move you to spam. (Very important)
  - If you have someplace in your website form that has a subscription box that takes a willing user's emails for subscription, make sure that you are verifying the email by sending an email with a confirmation link to the respective user email id. And add that email to your mailing list only once you get a confirmation for that email id. This prevents you from sending emails to someone who hasn’t subscribed to your services. You cannot expect people on the internet to be decent all the time.
  - Do not acquire/create an email sending list through web scraping or by downloading a list online (which is usually web scraped or gathered from unaware users)
  - Check your email volume rate. With that, we mean how much your email sending volume (The number of email recipients you are sending emails to) has increased over a few days. If your domain is relatively new, it is imperative that you do a warmup (i.e slowly ramp up your email sending volume)
  - Assess how you are acquiring your email list. Is it an organic way maybe a simple mail to subscribe to your services or a through an opt-in site form? If you are acquiring bulk mail from an agency or some website, that is not right and would definitely land you in spam traps.
- Monitoring and List cleanup: Use webhooks (a service provided by email sending services to send feedback regarding each and every email sent so that you can get critical data regarding your email campaigns) to remove the non-engaged users so that people that are not interested in opening your emails for a long time (usually a 1-2 weeks is more than enough time) are not forcefully sent an email.
  - This will clean up your emailing list and make sure that you have no issues in the future. The goal is to keep the open rates to the max.
  - If you can sustain that, that is really beneficial. In case a user is not opening an email for a long time, there’s a chance that the Gmail antispam might mark you as spam.
- Check your open rates from the email ids that you're sending emails to. A large number of non-opened emails indicates that either you were moved to spam or you were marked due to multiple emails not being opened by the same email user.
- In case you are listed in the Gmail blocklist, you will need to get your sending domain to be immediately de-listed from Gmail. Use the Google Postmaster tool for the identification of your domain/IP status.
- Check if your domain name is marked as unsafe from google: You can check here, by adding your domain URL here: https://transparencyreport.google.com/safe-browsing/search
- Clearly Stated Unsubscribe button/link: According to the email sending standards authority, it is imperative to send an email with an unsubscribe link. You just need to mention the unsubscribe link in the email very clearly.
- In case an unsubscribe link is not found, the anti-spam engine can identify that and mark you as spam.
Also, in case the user isn’t able to identify the unsubscribe button or link for some reason, it is a possibility that the user will be forced to move the email to spam in order to avoid the emails. 
- Check your email content and from address, and see if there are any mistakes in the from address. The email content needs to be scanned for spammy content.
- Verify the sending server PTR record. It is critical that the email sending server's sending IP address must match the IP address of the hostname specified in the Pointer (PTR) record. PTR records are also called Reverse DNS records.

The message is quite self-explanatory, your email sending servery is unauthorized as per Gmail to send email to its clients.

This could happen if you are not using an open SMTP server that is publicly available and anyone can send emails through it

There might also be an issue with IP Blocklisting in Gmail. Check Gmail postmaster tools for it.

### Solution:
  - If you're using a public SMTP server stop immediately and get an authentic paid SMTP service provider.
  - If you're indeed using a legitimate SMTP server that is provided to you by a reputable email service provider, then there are two things you can do
    - Contact your SMTP service provider and ask them to help with fixing the issue. This is the easiest way to fix the issue in this situation.
    - You can opt for a dedicated IP that will be a custom IP address that would be allocated to you, this is the case when you are having a really high email volume and you are sending millions of emails.

```
Our system has detected that this message is 421-4.7.0 suspicious due to the nature of the content and/or the links within. 421-4.7.0 To best protect our users from spam, the message has been blocked.
```
Here, the spam checker has identified the contents of the email as being malicious in some way. You will need to update the email content or subject line, so as to fix this.

These are some basic pointers on how to go about these points:

- Avoid spam keywords in the email: There are some keywords that are explicitly baked in the spam checkers so as to identify spammy marketing emails.
- Check your email structure. Usually, the email is an HTML document. Hidden contents, overuse of heavy images, external hyperlinks to a different domain from your own, and phishing links are responsible for spam identification of a good intent email. Remove these to fix the email issues.
- Also avoid hidden content or invisible text in the email, that will mark you as spam easily.
- The Size of the email can also be an issue. Especially with the images. The email sizes should be in KB. around 150 to 200 KB should be a good spot to be.
- The image-to-text ratio also affects the email rejection from the server. It is recommended to keep a ratio of 60:40 for text and image. The more the textual content, the better.
- Ensure that you do AB testing for each email template that you'll send to your subscribers.

These bullet points are just some of the common factors that affect your emails. You can check our Email Content Guide for a detailed tutorial on how you can fix the spam identification and what are different kinds of things to keep in mind with email content.

Even with the tutorial helping you, the number of things you will have to check for is quite daunting, so you can take the help of the Email tester, for a quick check.

```
550, "5.7.1": The user or domain that you are sending to (or from) has a policy that prohibits the mail that you sent. Please contact your domain administrator for further details. For more information, visit Sorry, a policy is in place that prevents your message from being sent.
```

In This Case, your email is getting blocked due to user policy, there’s no immediate fix to this. The receiving end-user has made some email policy that is causing your email to be rejected.

What you can do is currently stop sending emails to the user. In case you still want to send an email to the user, you might want to get in a one-on-one conversation with the user for the policy updates.