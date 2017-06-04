---
title: "Упорядоченная обработка сообщений в режиме единого параллелизма | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Упорядоченная обработка сообщений в режиме единого параллелизма
WCF гарантирует порядок обработки сообщений только в том случае, когда нижележащий канал связан с сеансами. Например, служба WCF, использующая канал MsmqInputChannel, который не связан с сеансами, не сможет обрабатывать сообщения по порядку. В некоторых обстоятельствах разработчику может потребоваться упорядоченная обработка сообщений без использования сеансов.В этом разделе описано, как настроить такое поведение, когда служба запущена в режиме Single Concurrency.  
  
## Упорядоченная обработка сообщений  
 В <xref:System.ServiceModel.ServiceBehaviorAttribute> добавлен новый атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A>.Если <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> задано значение true и <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> задается значение <xref:System.ServiceModel.ConcurrencyMode>, сообщения, отправленные службе, будут обработаны по порядку.В следующем фрагменте кода показано, как задать эти атрибуты.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
  
```  
  
 Если <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> имеет любое другое значение, выдается исключение <xref:System.InvalidOperationException>.  
  
## См. также  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Параллельность](../../../../docs/framework/wcf/samples/concurrency.md)