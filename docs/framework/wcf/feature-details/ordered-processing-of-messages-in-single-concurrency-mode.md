---
title: Упорядоченная обработка сообщений в режиме единого параллелизма
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: c9f2460a1def19212d3ba866b0b443830e9b69bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745857"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="63eaf-102">Упорядоченная обработка сообщений в режиме единого параллелизма</span><span class="sxs-lookup"><span data-stu-id="63eaf-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="63eaf-103">WCF не дает никаких гарантий относительно порядка, в которой обрабатываются сообщения, если нижележащий канал связан с связанный с сеансом.</span><span class="sxs-lookup"><span data-stu-id="63eaf-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="63eaf-104">Например службы WCF, использующей MsmqInputChannel, который не канал сеанса, не сможет обрабатывать сообщения в порядке.</span><span class="sxs-lookup"><span data-stu-id="63eaf-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="63eaf-105">Иногда возникают ситуации, когда разработчик может потребоваться упорядоченная обработка поведение, но нежелательно использовать сеансы.</span><span class="sxs-lookup"><span data-stu-id="63eaf-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="63eaf-106">В этом разделе описано, как настроить такое поведение, когда служба запущена в режиме единого параллелизма.</span><span class="sxs-lookup"><span data-stu-id="63eaf-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="63eaf-107">Упорядоченная обработка сообщений</span><span class="sxs-lookup"><span data-stu-id="63eaf-107">In-order Message Processing</span></span>  
 <span data-ttu-id="63eaf-108">В <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> добавлен новый атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="63eaf-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="63eaf-109">Если <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> задано значение true и <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> задается значение <xref:System.ServiceModel.ConcurrencyMode.Single>, сообщения, отправленные службе, будут обработаны по порядку.</span><span class="sxs-lookup"><span data-stu-id="63eaf-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="63eaf-110">В следующем фрагменте кода показано, как задать эти атрибуты.</span><span class="sxs-lookup"><span data-stu-id="63eaf-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="63eaf-111">Если <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> имеет любое другое значение, выдается исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="63eaf-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63eaf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="63eaf-112">See also</span></span>
- [<span data-ttu-id="63eaf-113">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="63eaf-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="63eaf-114">Параллелизм</span><span class="sxs-lookup"><span data-stu-id="63eaf-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
