---
title: "Tutorial for your soul"
date: 2023-03-20T21:28:22+05:30
draft: false 
# cover:
#   image: ''
#   alt: 'Solution info banner'
#   caption: 'Solutions to spam smtp error'
tags: ["gmail", "smtp"]
categories: ["tech"]
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

{{< calculator >}}

```
421-4.7.0 Our system has detected an unusual rate of unsolicited mail originating from your IP address. To protect our users from spam, mail sent from your IP address has been temporarily blocked. For more information
```

Your domain is being blocked because of being identified as spam or due to a drastic increase in email sending rates.
