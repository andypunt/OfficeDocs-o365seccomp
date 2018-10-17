---
title: "Unregistered Domain Email"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: "If you send a high volume of unregistered domain email, you run the risk of your email getting blocked. Read this article to learn more."
---

# Unregistered Domain Email: What you need to know

Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.

## Problems with unregistered domains

The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.

Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:

- 550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains

## Unblocking tenant in order to send again

There are several things you need to do if you get blocked for sending from unregistered domains:

1. Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Check for newly created inbound connectors. More information on getting a list of your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).

3. Lock down your on-premise servers and ensure that they are not compromised.

> [!NOTE]
> There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able to make sure that all mail leaving your servers are legitimate.

4. Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## For more information

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Email non-delivery reports in Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configure email forwarding for a mailbox](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[How to set up a multifunction device or application to send email using Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
