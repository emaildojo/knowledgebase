---
title: "How to Set Up MX Records for a Domain Registered With Namecheap"
date: 2023-06-15T15:27:55+05:30
draft: false
tags: ["setup-mx"]
categories: ["Email Deliverability"]
author: ['Raj Shinde']
---

## Introduction

[MX records](https://emaildojo.io/mx-record-lookup) are essential for email delivery. They tell email servers where to send emails for a domain. MX records specify the mail servers responsible for handling email, their priority, and IP addresses. When sending an email, the client checks the recipient's domain's MX records to find the correct mail server. There are primary, backup, and round-robin MX record types. Setting up MX records involves accessing DNS settings and ensuring accuracy. Proper MX record configuration is crucial for reliable email delivery.

Know more about [MX records](https://emaildojo.io/knowledgebase/email-deliverability/introduction-to-mx-record-part-1/).

## Setting up

If your domain is currently using Namecheap BasicDNS, PremiumDNS, or FreeDNS, you can easily configure your mail service and MX records within your Namecheap account.
Please note that before proceeding with the setup of your mail service, it is important to ensure that no CNAME record exists for your bare domain (e.g., yourdomain.tld) in the Host records section. Having a CNAME record for the bare domain will interfere with the proper functioning of email services. CNAME records have the highest priority and take precedence over all other records, including MX Records, which are responsible for mail delivery.

## To set up MX records for your domain, follow these steps:

**Step-1:**  Sign into your Namecheap account in the top left corner of the page.

**Step-2:**  Select Domain List from account  in home page:

![AccountDomainList](https://i.imgur.com/gjuNflT.png)

**Step-3:**  Select Domain List in the left sidebar:

![DomainList](https://i.imgur.com/zTfK2E5.png)

**Step-4:** Click Manage next to the domain name you wish to set DNS records for:

![Manage](https://i.imgur.com/olq5O1q.png)

**Step-5:** Navigate to the Advanced DNS tab and go to the Mail Settings section:

![MailSettings](https://i.imgur.com/jim38nQ.png)
 
Here, you may choose one of the following Mail Settings depending on the mail service you wish to use:

- **No Email Service**- if you wish to use no mail service. Your domain will have no MX records.
- **Email Forwarding**- if you wish to create personalized e-mail addresses for a domain and forward emails to other email accounts of your choice. 
The MX records will be set up automatically after selecting this option:

![EmailForwarding](https://i.imgur.com/bkPSbPm.png)

- **MXE record** is used for forwarding mail to a mail server's IP address.

![mxe](https://i.imgur.com/U6KBEbf.png)
- **Custom MX** is used to set MX records for third-party mail services, like cPanel webmail service (if you wish to use cPanel mail service with default nameservers), Zoho mail, Outlook, etc.
![customMxe](https://i.imgur.com/z2LIfpG.png)
It is possible to indicate your own domain as the **mail server address** like mail.domain.tld or domain.tld. Please note that the corresponding A record pointing to the IP address of the mail server should be created in the DNS settings:
![mail](https://i.imgur.com/UcXaJs2.png)
**Private Email** - if you wish to set up MX records for the Namecheap Private email service. The MX records will be set up automatically after selecting this option:
![privateEmail](https://i.imgur.com/rBKOzCg.png)

**Gmail** - if you have a G Suite  subscription, select the Gmail option to set up the records needed for this mail service:
![gmail](https://i.imgur.com/KEJE4bR.png)
Once all necessary settings are selected, be sure to save changes. Normally, it takes 30 minutes for newly created records to take effect.


