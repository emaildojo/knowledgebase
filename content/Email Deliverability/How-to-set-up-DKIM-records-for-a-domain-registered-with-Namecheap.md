---
title: "How to Set Up DKIM Records for a Domain Registered With Namecheap"
date: 2023-06-19T18:23:58+05:30
draft: false
tags: ["setup-dmarc"]
categories: ["Email Deliverability"]
author: ['Raj Shinde']
---


## Introduction

[DKIM](https://emaildojo.io/dkim-checker) (DomainKeys Identified Mail) is a method used to ensure the integrity of email messages by verifying that their content remains unchanged from the moment they left the initial mail server. This verification is achieved through the implementation of a standard public/private key signing process.

To establish trust, the domain owners include a DNS entry containing the public DKIM key. Receivers can then use this key to verify the correctness of the DKIM signature in the message. On the sender side, the mail server signs entitled messages with the corresponding private key.

[DKIM records are implemented as text records (TXT)](https://emaildojo.io/dkim-checker). They are created for a subdomain, which has a unique selector associated with the key. The format includes the protocol name '_domainkey' and the domain name itself. The record type is TXT, and the value includes the key type followed by the actual key.

Both 1024-bit and 2048-bit keys are supported for DKIM implementation, allowing for increased security and key strength.

By using DKIM, email senders can enhance the trustworthiness and integrity of their messages, providing recipients with a means to verify that the content has not been tampered with since it left the original mail server.

`example:- selector1._domainkey.yourdomain.com        TXT     k=rsa;p=J8eTB32324i086iK`


Know more about [DKIM records](https://emaildojo.io/knowledgebase/email-deliverability/introduction-to-dkim-records/).


## Setting up DKIM record

**To add a required record to your domain using Namecheap's BasicDNS, PremiumDNS, or FreeDNS, follow these steps:**


**Step-1:**  Sign into your Namecheap account in the top left corner of the page.

**Step-2:**  Select Domain List from account  in home page:

![AccountDomainList](https://i.imgur.com/gjuNflT.png)

**Step-3:**  Select Domain List in the left sidebar:

![DomainList](https://i.imgur.com/zTfK2E5.png)

**Step-4:** Click Manage next to the domain name you wish to set DNS records for:

![Manage](https://i.imgur.com/olq5O1q.png)

**Step-5:** In the DNS Management interface, locate the option to add a new record and select "TXT Record" as the record type.

![txt record](https://i.imgur.com/DkOcSTD.png)
 
**NOTE:** When adding a TXT record for a specific subdomain like "something._domainkey.yourdomain.tld," it's important to remember that you should only enter "something._domainkey" in the Host field. The domain itself should not be included. This is a system requirement that ensures proper record configuration. So, make sure to follow this guideline even if your service provider instructs you otherwise.

- **DKIM selector** is specified in the DKIM-Signature header and indicates where the public key portion of the DKIM keypair exists in DNS. The receiving server uses the DKIM selector to locate and retrieve the public key to verify that the email message is authentic and unaltered.
![Dkim Selector](https://i.imgur.com/ShKcgB5.png)

**Step-6:** Add generated DKIM record in value. You can use any [DKIM record Generator](https://emaildojo.io/dkim-generator) to generate DKIM Record.

![set records](https://i.imgur.com/uSsDIXS.png)


**Step-7:** Click on the Save all changes button. Normally, it takes 30 minutes for newly created host records to take effect.



