---
title: "How to Set Up DMARC Records for a Domain Registered With Namecheap"
date: 2023-06-19T16:45:31+05:30
draft: false
tags: ["setup-dmarc"]
categories: ["Email Deliverability"]
author: ['Raj Shinde']
---


## Introduction

DMARC (Domain-based Message Authentication, Reporting, and Conformance) is an email authentication protocol that helps prevent email spoofing and phishing attacks. It works by allowing email domain owners to specify how their emails should be handled when received by email receivers.

DMARC combines two existing email authentication methods: SPF (Sender Policy Framework) and DKIM (DomainKeys Identified Mail). SPF checks if the sender's IP address is authorized to send emails on behalf of a specific domain, while DKIM verifies the integrity of the email's content using digital signatures.

When an email is received, the recipient's email server checks the SPF and DKIM authentication results. Afterward, DMARC determines what action to take based on the alignment of the sender's domain with the domains authenticated by SPF and DKIM.

DMARC policies can be set to three different levels:

- "None" policy: The DMARC record requests no specific action to be taken when an email fails the DMARC checks. However, it allows the domain owner to receive aggregate reports about the email authentication results.
- "Quarantine" policy: The DMARC record instructs the email receiver to treat failed emails as suspicious and potentially deliver them to the recipient's spam or quarantine folder.
- "Reject" policy: The DMARC record directs the email receiver to reject emails that fail the DMARC checks, preventing them from reaching the recipient's inbox.
By implementing DMARC, domain owners can gain visibility into email authentication results, protect their domain reputation, and reduce the likelihood of successful email spoofing and phishing attacks.

example:- example.com TXT v=DMARC1; p=quarantine; fo=0:1:d:s; sp=quarantine; pct=17; adkim=r; aspf=s





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
 
 **Step-6:** Add generated DMARC record in value. You can use any [ DMARC record Generator](https://emaildojo.io/dmarc-record-generator) to generate DMARC Record.

![set records](https://i.imgur.com/AxAYFYF.png)

Make sure the record type is TXT, host is set to _dmarc, and value is set to the generated DMARC record. Click the green check button. Congratulations, you have added the record!

**Step-7:** Click on the Save all changes button. Normally, it takes 30 minutes for newly created host records to take effect.



