---
title: "Упорядоченная обработка сообщений в режиме единого параллелизма"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a1acf4c3edb51500c2ead2e4ba33c6d3cc9c953f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Упорядоченная обработка сообщений в режиме единого параллелизма
WCF не гарантирует порядок, в котором обрабатываются сообщения, если базовый канал сеанса.  Например службы WCF, использующей MsmqInputChannel, не являющийся канал сеанса, сможет обрабатывать сообщения по порядку. Иногда возникают ситуации, когда разработчик может в порядок обработки, но не хотите использовать сеансы. В этом разделе описано, как настроить такое поведение, когда служба запущена в режиме единого параллелизма.  
  
## <a name="in-order-message-processing"></a>Упорядоченная обработка сообщений  
 В <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> добавлен новый атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute>. Если <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> задано значение true и <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> задается значение <xref:System.ServiceModel.ConcurrencyMode.Single>, сообщения, отправленные службе, будут обработаны по порядку. В следующем фрагменте кода показано, как задать эти атрибуты.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Если <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> имеет любое другое значение, выдается исключение <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>См. также  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Параллелизм](../../../../docs/framework/wcf/samples/concurrency.md)
