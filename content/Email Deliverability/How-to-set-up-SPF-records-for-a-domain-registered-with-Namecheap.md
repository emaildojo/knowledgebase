---
title: "How to Set Up SPF Records for a Domain Registered With Namecheap"
date: 2023-06-19T16:15:37+05:30
draft: false
tags: ["setup-SPF"]
categories: ["Email Deliverability"]
author: ['Raj Shinde']
---


## Introduction

If your domain is pointed to Namecheap's BasicDNS, PremiumDNS, or FreeDNS, you can set up TXT, [SPF](https://maemaildojo.io/spf-record-checker), [DKIM](https://emaildojo.io/dkim-checker), and [DMARC](https://emaildojo.io/dmarc-checker) records in your Namecheap account. These records help enhance email security and authentication.

SPF (Sender Policy Framework) is a DNS text entry that specifies the authorized mail servers for a domain. It helps prevent email spoofing by allowing receiving mail servers to verify that the incoming email is sent from an authorized server. To create an SPF record, you would typically add a TXT record to your domain's DNS settings. Here's an example of a basic SPF record:

`example.com   TXT     v=spf1 a ~all`

This record states that the IP address associated with the domain's A record (a) is allowed to send emails, and the tilde (~) indicates a soft fail, meaning that if the SPF check fails, the email should still be accepted but marked as potentially suspicious.

To set up SPF records in your Namecheap account, log in to your Namecheap control panel, navigate to your domain's DNS settings, and add the appropriate TXT record with your desired SPF configuration.

Remember, SPF records can vary depending on your specific email setup and requirements, so it's recommended to consult with your email service provider or IT team for guidance on configuring SPF properly for your domain.

Know more about [SPF records](https://emaildojo.io/knowledgebase/email-deliverability/introduction-to-spf-records/).

## Setting up SPF record

To add a required record to your domain using Namecheap's BasicDNS, PremiumDNS, or FreeDNS, follow these steps:

**To set up SPF records for your domain, follow these steps:**

**Step-1:**  Sign into your Namecheap account in the top left corner of the page.

**Step-2:**  Select Domain List from account  in home page:

![AccountDomainList](https://i.imgur.com/gjuNflT.png)

**Step-3:**  Select Domain List in the left sidebar:

![DomainList](https://i.imgur.com/zTfK2E5.png)

**Step-4:** Click Manage next to the domain name you wish to set DNS records for:

![Manage](https://i.imgur.com/olq5O1q.png)

**Step-5:** In the DNS Management interface, locate the option to add a new record and select "TXT Record" as the record type.

![txt record](https://i.imgur.com/DkOcSTD.png)

**Step-6:** Add generated spf record in value. You can use a [SPF record Generator](https://emaildojo.io/spf-record-generator) to generate SPF Record.

![set records](https://i.imgur.com/RbR16kX.png)

**Step-7:** Click on the Save all changes button. Normally, it takes 30 minutes for newly created host records to take effect.



