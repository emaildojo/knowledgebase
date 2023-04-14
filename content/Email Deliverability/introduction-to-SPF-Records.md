---
title: "Introduction to SPF Records"
date: 2023-04-13T17:36:46+05:30
draft: false
tags: ["SPF", "SPF Checker"]
categories: ["Email Deliverability"]
author: ["Vikram Sahu"]
---

## Introduction

One of the most popular methods of communication for both personal and professional goals is email. But, email consumers are increasingly getting concerned about email fraud and spam. In reality, research has revealed that a sizable portion of emails sent globally are spam or fraudulent in nature. As a result, email authentication mechanisms like Sender Policy Framework (SPF) were created to help address these problems.

The SPF email authentication system, which is based on DNS, enables email domain owners to specify which mail servers are permitted to send emails on their behalf. As it contains the data required to verify the sender's domain, an SPF record is an essential part of the protocol.

In this post, we'll explore the crucial elements of SPF records, such as their function, syntax, elements, generation, testing, typical mistakes, and best practises. You will have a thorough grasp of SPF records by the end of this article, including how they can increase email deliverability and safeguard your domain from email fraud.

## What are SPF records?

Sender Policy Framework (SPF) records are a type of Domain Name System (DNS) record that is used to specify which mail servers are authorized to send emails on behalf of a particular domain. SPF records are used for email authentication purposes and are a key component in preventing email fraud and spam.

SPF records contain a list of authorized mail servers, known as the "SPF mechanism", that are permitted to send emails from a particular domain. When an email is received, the receiving mail server can check the SPF record of the sender's domain to verify if the sending mail server is authorized to send emails on behalf of that domain.

If the sending mail server is not authorized, the receiving mail server can reject the email or flag it as spam. SPF records are an important part of email authentication and can help improve email deliverability and protect against email fraud.

## Purpose of SPF records

The primary purpose of SPF records is to prevent email fraud and spam by verifying the authenticity of the sender's domain.

- Verify the authenticity of the sender's domain to prevent email fraud and spoofing.

- Specify which mail servers are authorized to send emails on behalf of a domain.

- Improve email deliverability by reducing the likelihood of legitimate emails being marked as spam or rejected.

- Provide a means for receiving mail servers to verify the legitimacy of emails and reduce false positives and false negatives in spam filtering.

- Authorize third-party email services to send emails on behalf of a domain, such as email marketing services or cloud-based email services.

- Help ensure that emails sent through these services are delivered to the intended recipients and not marked as spam.

## Understanding SPF record's syntax & Components

The syntax of an SPF record consists of a series of mechanisms and qualifiers that define which mail servers are authorized to send emails on behalf of a particular domain. Here is the basic syntax of an SPF record:

`v=spf1 [mechanisms] [qualifiers]`

Let's break this down further:

- `v=spf1` - This specifies the version of the SPF record being used. Currently, SPF version 1 (SPFv1) is the only version in use.

- `[mechanisms]` - These are the mechanisms that define which mail servers are authorized to send emails on behalf of the domain. There are several mechanisms available, including:

  - **a** - Allows the domain's A record to send emails
  - **mx** - Allows the domain's MX record to send emails
  - **ip4** - Allows a specific IPv4 address or range of addresses to send emails
  - **ip6** - Allows a specific IPv6 address or range of addresses to send emails
  - **include** - Allows another domain's SPF record to be included in the current record

- `[qualifiers]` - These are optional and define how the mechanisms should be evaluated. There are two qualifiers available:

  - **+** - Pass (authorize) the email if the mechanism is matched
  - **-** - Fail (reject) the email if the mechanism is matched

- `all` mechanism - The all mechanism specifies the default action to take for emails that do not match any of the specified mechanisms. There are two possible actions:

  - **-** : Fail (reject) the email if it does not match any of the specified mechanisms.
  - **~** : Soft fail the email if it does not match any of the specified mechanisms. A soft fail means that the email may still be delivered, but it will be marked as potentially suspicious.

Here is an example of an SPF record that authorizes a domain's A and MX records, as well as a specific IP address, to send emails:

```bash
v=spf1 a mx ip4:192.0.2.1 -all
```

This record specifies that the domain's A and MX records, as well as the IP address 192.0.2.1, are authorized to send emails, and all other mail servers should fail the SPF check.

## How to create a SPF record?

Creating an SPF (Sender Policy Framework) record from scratch involves a few steps:

1. Determine the domains and IP addresses that will be authorized to send email on behalf of your domain.

2. Write a TXT record that contains the SPF information. The record should be added to the DNS records for your domain.

3. Test the record to ensure that it is working properly.

Here are the detailed steps to create an SPF record from scratch:

Step 1: Determine the domains and IP addresses

You need to determine which domains and IP addresses are authorized to send email on behalf of your domain. This information should include:

- The IP addresses of your email servers
- The IP addresses of any third-party email services that you use
- The domains of any third-party email services that you use

Step 2: Write the SPF record

Once you have determined the domains and IP addresses that are authorized to send email on behalf of your domain, you need to create a TXT record that contains the SPF information. Here's an example:

```bash
v=spf1 ip4:192.0.2.0/24 include:\_spf.example.com ~all
```

Let's break this down:

- v=spf1: This specifies the SPF version.
- ip4:192.0.2.0/24: This allows the IP range 192.0.2.0 to 192.0.2.255 to send email on behalf of your domain.
- include:\_spf.example.com: This includes the SPF record for the domain \_spf.example.com. This is useful if you use a third-party email service that provides its own SPF record.
- ~all: This indicates that any email that does not match the authorized domains or IP addresses should be treated as suspicious.

You can use other mechanisms in your SPF record to specify other IP addresses or domains that are authorized to send email on behalf of your domain. The available mechanisms include:

- a: Allows the domain name of the A record for the domain to send email.
- mx: Allows the domain name of the MX record for the domain to send email.
- include: Includes the SPF record of another domain.
- redirect: Redirects to another domain's SPF record.

Step 3: Test the SPF record

Once you have created the SPF record, you need to test it to ensure that it is working properly.

You can use your terminal or various online tools to check your SPF record, such as [Emaildojo's SPF Checker](https://emaildojo.io/spf-record-checker). If any issues are detected, you can make adjustments to your SPF record until it is functioning correctly. You can also generate new SPF record using [**Free** SPF Generator](https://emaildojo.io/spf-record-generator) just keep your server details handy.

Finally, remember to add the SPF record to the DNS records for your domain. This can usually be done through your domain registrar or hosting provider.

## How to check SPF record using terminal?

To check the SPF record for a domain in the terminal, you can use the dig command on a Unix-based system (such as Linux or macOS) that has the command-line tool installed. Here's how:

1. Open a terminal window.

2. Type the following command, replacing "example.com" with the domain you want to check:

```bash
dig example.com TXT +short
```

3. Press Enter.

4. The command output will display the TXT record for the domain, which should include the SPF record if it exists. Look for a line that starts with "v=spf1" or "spf2.0" to confirm the presence of an SPF record.

Note that some domains may have multiple TXT records, so you may need to look through the output to find the one that contains the SPF record. Also, keep in mind that some domains may have their SPF records stored in a subdomain (such as "\_spf.example.com"), in which case you would need to modify the command to check that subdomain instead.

If you want to check if a particular IP address is allowed to send email on behalf of the domain, you can use an SPF checker tool or use the dig command with the +short and txt options followed by the IP address and domain, like this:

```bash
dig +short TXT <IP address>.<domain>
```

Replace <IP address> and <domain> with the relevant values. If the output contains the IP address, it means that the address is authorized to send email for that domain according to the SPF record.

## Common errors in SPF records

There are several common errors that can occur when creating an SPF record:

1. **Syntax errors**: This can occur if the syntax of the SPF record is incorrect. For example, forgetting to include the "v=spf1" statement or using the wrong syntax for a mechanism or modifier.

2. **Missing or incorrect mechanisms**: This can occur if the SPF record does not include all the necessary mechanisms for authorizing email from legitimate sources. For example, forgetting to include the "a" mechanism for the domain's own email servers or not including a mechanism for a third-party email service that sends email on behalf of the domain.

3. **Overlapping or conflicting mechanisms**: This can occur if the SPF record contains overlapping or conflicting mechanisms that result in email being incorrectly classified as spam or rejected. For example, having multiple "mx" mechanisms that authorize different sets of email servers or having both "include" and "redirect" mechanisms that point to different SPF records.

4. **Incorrect CIDR notation**: This can occur if the CIDR notation for an IP address range is incorrect. For example, using a subnet mask instead of a CIDR notation or using an incorrect number of bits in the CIDR notation.

5. **Too many DNS lookups**: This can occur if the SPF record includes too many mechanisms that require DNS lookups, which can cause delays or timeouts in email delivery. This is especially a problem for domains that use multiple third-party email services, each with their own SPF records.

To avoid these errors, it is important to carefully review the syntax and content of the SPF record before publishing it, and to test the record using SPF checker tools to ensure that it is working correctly.

Additionally, it's important to keep the SPF record up-to-date and revise it as needed to reflect changes in the domain's email infrastructure.

## Conclusion

In conclusion, an SPF record is a kind of DNS record that guards against spam and phishing assaults as well as email spoofing. It shows which email servers are permitted to send email on behalf of a domain and gives recipient mail servers instructions on how to deal with email that doesn't pass SPF checks.

Domain owners can increase email deliverability and prevent their domain from being used for fraudulent purposes by setting and keeping an accurate and current SPF record. To verify that an SPF record is functioning properly, it's crucial to use SPF checker tools and be aware of typical mistakes that can happen when creating one.
