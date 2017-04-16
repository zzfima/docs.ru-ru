---
title: "&lt;claimTypeRequirements&gt; для &lt;message&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;claimTypeRequirements&gt; для &lt;message&gt;
Задает коллекцию обязательных типов утверждений.  
  
 Коллекция используется службой, чтобы задать обязательные и необязательные утверждения, которые должны содержаться в выданном маркере, используемом клиентом для доступа к службе.  Служба предоставляет обязательные типы утверждений в метаданных, если публикация WDSL включена, но WCF не требует, чтобы выданный маркер содержал заданные типы утверждений.  Службы, для которых необходимо принудительное наличие обязательных типов утверждений, должны использовать политику авторизации.  
  
 В федеративных клиентах эта коллекция содержит список обязательных и необязательных утверждений, который отправляется службе маркеров безопасности в запросе клиента для выданного маркера.  
  
## См. также  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>