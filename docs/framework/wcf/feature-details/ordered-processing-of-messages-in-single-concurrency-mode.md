---
title: Упорядоченная обработка сообщений в режиме единого параллелизма
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: bbbc1f62931abda438c3d06b514518b1199b649e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
