---
title: "Context variables for a bot | MicrosoftDocs"
description: "Context variables to use when configuring a bot in Omnichannel for Customer Service."
author: neeranelli
ms.author: nenellim
manager: shujoshi
ms.date: 11/11/2020 
ms.topic: article
ms.service: dynamics-365-customerservice
---

# Context variables for a bot

[!INCLUDE[cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

[!INCLUDE[cc-use-with-omnichannel](../../includes/cc-use-with-omnichannel.md)]

This topic lists the context variables that you can configure for a bot in Power Virtual Agents or Azure to use in Omnichannel for Customer Service.

## Context variables

The following table contains the list of variables in Omnichannel for Customer Service that can help you configure some of the context variables for a bot in [Power Virtual Agents](configure-bot-virtual-agent.md) or [Azure](configure-bot.md).

> [!IMPORTANT]
> Make sure of the following:
> - Names are not changed and used as is when you author flows in Power Virtual Agents or Azure bots.
> - The value that will be passed to the context variable doesn't exceed 4,000 characters so that the conversation can be successfully escalated to the agent.

| Context variable type | Context variable name | Description | How to map in Power Virtual Agents | How to map in Azure |
|-----|-----|-------|-------|-----|
| [Pre-conversation survey](configure-pre-chat-survey.md) | Use the question type that you create in Omnichannel for Customer Service. | The context variables for pre-conversation answers store the customer answers for questions in the pre-conversation survey. | Use the following information to map the question type variable in Omnichannel for Customer Service with the variable type in Power Virtual Agents:<br><ul><li> **Single line:** User’s entire response</li>**Multiple lines:** User's entire response<li>**Option set:** User's entire response</li><li>**User Consent:** Boolean</li></ul> |Use the following information to map the question type variable in Omnichannel for Customer Service with the variable type in Azure:<br><ul><li> **Single line:** String</li>**Multiple lines:** String<li>**Option set:** String</li><li>**User Consent:** Boolean</li></ul>|
| [Custom Context](../developer/how-to/send-context-starting-chat.md) | Use the variable name that you create in Omnichannel for Customer Service or pass using the setcontext API. | These are custom context variables that can be created and passed through the Livechat SDK. | Use the following information to map the custom context variable in Omnichannel for Customer Service with the variable type in Power Virtual Agents: <br><ul><li>**String:** User's entire response</li><li>**Boolean:** Boolean</li><li>**Number, Floating Number:** Number</li></ul> |Use the following information to map the custom context variable in Omnichannel for Customer Service with the variable type in Azure: <br><ul><li>**String:** String</li><li>**Boolean:** Boolean</li><li>**Number, Floating Number:** Number</li></ul>|
| Conversation | msdyn_liveworkitemid | Use the context variable that contains the conversation ID for the ongoing conversation and can fetch and perform operations on the record in Common Data Service. | Parse the JSON to extract the Conversation ID. |Parse the JSON to extract the Conversation ID.|
|[Customer](record-identification-rule.md) |msdyn_contact_msdyn_ocliveworkitem_Customer| Use this context variable that contains the record ID for the customer (contact or account) record that is linked to the conversation. When you set this variable, the customer will be linked to the conversation post flush.| Parse the JSON to extract the record ID. |Parse the JSON to extract the record ID.|
| Case | msdyn_incident_msdyn_ocliveworkitem | Use this context variable that contains the record ID for the case record linked to the conversation. When you set this variable, the case will be linked to the conversation post flush.|Parse the JSON to extract the record ID. |Parse the JSON to extract the record ID.|
|||||

### See also

[Integrate a Power Virtual Agents bot](configure-bot-virtual-agent.md)  
[Integrate an Azure bot](configure-bot.md)  
