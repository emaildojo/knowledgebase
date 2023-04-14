---
title: "Everything About BIMI Record"
date: 2023-04-13T19:05:46+05:30
draft: true
tags: ["bimi", "deliverability"]
categories: ["Email Deliverability"]
author: ["Vikram Sahu"]

---

## Introduction

Email communication is an essential part of modern business, and email marketers and senders have always tried to make their messages stand out from the crowd. One of the most effective ways to do this is through visual branding, which not only helps to increase brand recognition but also enhances trust and engagement with customers.

However, email authentication technologies such as SPF, DKIM, and DMARC have limited the ability of email senders to use their brand logos in email messages, as they require strict verification of sender identity.

This is where BIMI comes into play.

## What is BIMI?

BIMI, which stands for Brand Indicators for Message Identification, is an emerging email authentication standard that enables email senders to display their brand logos directly in the email client's interface.

BIMI provides a verified and standardized way to display brand logos in emails, enhancing the email experience for recipients while also increasing email security.

## How BIMI Works ?

BIMI works by using a combination of email authentication technologies and digital certificates. When an email sender sends a message, their email service provider includes a BIMI record in the email header, which contains information about the sender's domain, the location of the sender's brand logo, and a reference to the sender's Verified Mark Certificate (VMC).

The VMC is a digital certificate that verifies the sender's identity and their right to use their brand logo.

To obtain a VMC, the sender must go through a validation process with a trusted VMC provider. The VMC provider checks that the sender has the legal right to use the brand logo and that the logo meets certain technical requirements.

When the recipient's email client receives the email, it checks the BIMI record and verifies the sender's identity using SPF, DKIM, and DMARC. If the sender's identity is verified, the email client retrieves the brand logo from the location specified in the BIMI record and displays it in the email interface.

## Benefits of Implementing BIMI for email sender & receiver.

Implementing BIMI provides several benefits for email senders and receivers.

- For email senders, BIMI enhances their brand recognition and trust, as their logo is prominently displayed in the email client's interface.
  This helps to increase open rates and engagement with customers, as recipients are more likely to click on emails that they recognize and trust.

- For email receivers, BIMI enhances email security by providing a visual indicator of the sender's identity. This helps to prevent phishing and spoofing attacks, as recipients can quickly identify legitimate emails from trusted senders.

Additionally, BIMI enhances the overall email experience for recipients by providing a consistent visual brand identity across different email clients.

## How to Implement BIMI?

To implement BIMI, organizations need to follow these steps:

Step 1: Authenticate the email with DKIM and DMARC

Before implementing BIMI, organizations must first ensure that their email authentication protocols, DKIM and DMARC, are properly set up. DKIM ensures that emails are coming from legitimate senders and haven't been tampered with during transit, while DMARC provides instructions on how to handle emails that fail authentication.

Step 2: Create a BIMI-compliant logo

The next step is to create a BIMI-compliant logo that meets the technical specifications required for display in email inboxes. BIMI logos must be SVG files, and they should be a square with a minimum size of 144 x 144 pixels.

Step 3: Publish the logo on a web server

The logo must be published on a web server, and a DNS TXT record containing the URL for the logo must be created.

Step 4: Create a BIMI record

Organizations must create a BIMI record and publish it in their DNS. The record contains the URL for the logo, as well as the location of the VMC (Verified Mark Certificate) file that contains the public key needed to validate the logo.

Step 5: Submit the VMC file to a BIMI validator

Finally, organizations must submit the VMC file to a BIMI validator to ensure that the logo meets the technical requirements and that the domain is eligible for BIMI implementation.

## Common BIMI implementation issues

While implementing BIMI, organizations may face several common issues that can impact the success of their BIMI implementation.

Here are some of the most common issues and how to address them:

1. Improper email authentication: BIMI relies on proper email authentication with DKIM and DMARC, and if these protocols are not properly set up, BIMI will not work correctly.

Before implementing BIMI, organizations should ensure that their email authentication protocols are set up correctly and that emails are being properly authenticated.

2. Technical logo issues: BIMI requires logos to be SVG files, and they must meet certain technical specifications for size and format. If the logo is not properly formatted, it may not display correctly in email inboxes, or it may not display at all.

Organizations should ensure that their logos are properly formatted and meet the technical requirements for BIMI.

3. DNS configuration errors: To implement BIMI, organizations must publish a BIMI record in their DNS. If the DNS record is not properly configured, it may cause issues with logo display or may prevent BIMI from working altogether.

Organizations should ensure that their DNS records are properly configured and that the BIMI record is correctly published.

4. BIMI validation issues: Before the logo can be displayed in email inboxes, it must be validated by a BIMI validator to ensure that it meets the technical requirements. If the logo fails validation, it may not display in email inboxes, or it may not display correctly. Organizations should ensure that their logos pass BIMI validation before implementing BIMI.

5. Eligibility issues: BIMI is currently only available to organizations that meet certain eligibility requirements, such as having a DMARC policy of `p=quarantine` or `p=reject`. If an organization does not meet the eligibility requirements, they will not be able to implement BIMI. Organizations should ensure that they meet the eligibility requirements before attempting to implement BIMI.

## Benefits of BIMI

Implementing BIMI provides a range of benefits to organizations, including:

- Brand visibility and recognition: As mentioned earlier, BIMI enables organizations to display their logos in the recipient’s inbox, increasing brand visibility and recognition.

- Improved email engagement: When an email recipient sees a familiar logo, they are more likely to trust the message and engage with it. This can lead to improved email open rates and click-through rates.

- Better email deliverability: Email providers are more likely to deliver messages from authenticated senders with a BIMI record as it ensures the sender's identity is verified.

- Increased security: Implementing BIMI helps organizations protect their brand against phishing and spoofing attacks. By requiring an authorized DKIM signature and a valid DMARC policy, BIMI ensures that only legitimate messages from verified senders can display a logo.

## Conclusion

BIMI is an emerging email authentication protocol that provides a range of benefits to organizations. By displaying the sender’s logo in the recipient’s inbox, BIMI improves brand visibility and recognition, email engagement, and email deliverability while increasing security against phishing and spoofing attacks.

Implementing BIMI requires proper authentication with DKIM and DMARC, creating a BIMI-compliant logo, publishing the logo on a web server, creating a BIMI record, and submitting the VMC file to a BIMI validator.

By following these steps, organizations can enhance their email communication and build trust with their recipients.
