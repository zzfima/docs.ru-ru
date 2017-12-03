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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c677ed869c0e5dd0df1288de48668ba403df5aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="9588d-102">Упорядоченная обработка сообщений в режиме единого параллелизма</span><span class="sxs-lookup"><span data-stu-id="9588d-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="9588d-103">WCF не гарантирует порядок, в котором обрабатываются сообщения, если базовый канал сеанса.</span><span class="sxs-lookup"><span data-stu-id="9588d-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="9588d-104">Например службы WCF, использующей MsmqInputChannel, не являющийся канал сеанса, сможет обрабатывать сообщения по порядку.</span><span class="sxs-lookup"><span data-stu-id="9588d-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="9588d-105">Иногда возникают ситуации, когда разработчик может в порядок обработки, но не хотите использовать сеансы.</span><span class="sxs-lookup"><span data-stu-id="9588d-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="9588d-106">В этом разделе описано, как настроить такое поведение, когда служба запущена в режиме единого параллелизма.</span><span class="sxs-lookup"><span data-stu-id="9588d-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="9588d-107">Упорядоченная обработка сообщений</span><span class="sxs-lookup"><span data-stu-id="9588d-107">In-order Message Processing</span></span>  
 <span data-ttu-id="9588d-108">В <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> добавлен новый атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9588d-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="9588d-109">Если <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> задано значение true и <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> задается значение <xref:System.ServiceModel.ConcurrencyMode.Single>, сообщения, отправленные службе, будут обработаны по порядку.</span><span class="sxs-lookup"><span data-stu-id="9588d-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="9588d-110">В следующем фрагменте кода показано, как задать эти атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9588d-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="9588d-111">Если <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> имеет любое другое значение, выдается исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="9588d-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9588d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9588d-112">See Also</span></span>  
 [<span data-ttu-id="9588d-113">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="9588d-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="9588d-114">Параллелизм</span><span class="sxs-lookup"><span data-stu-id="9588d-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
