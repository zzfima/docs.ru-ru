---
title: Обработка неупорядоченных сообщений
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7d908be84f22835bea744de74d278689516f3185
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698015"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="48593-102">Обработка неупорядоченных сообщений</span><span class="sxs-lookup"><span data-stu-id="48593-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="48593-103">Службы рабочих процессов могут зависеть от порядка отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="48593-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="48593-104">Служба рабочих процессов содержит одно или несколько действий <xref:System.ServiceModel.Activities.Receive>. Каждое из этих действий <xref:System.ServiceModel.Activities.Receive> рассчитано на определенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="48593-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="48593-105">Поскольку доставка данных не гарантируется, отправляемые клиентами сообщения могут задерживаться и доставляться в порядке, на который служба рабочих процессов не рассчитана.</span><span class="sxs-lookup"><span data-stu-id="48593-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="48593-106">Реализация службы рабочих процессов, которая не требует отправки сообщений в определенном порядке, обычно осуществляется с использованием параллельных действий.</span><span class="sxs-lookup"><span data-stu-id="48593-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="48593-107">В результате усложнения протокола приложения рабочий процесс также слишком быстро становится сложным.</span><span class="sxs-lookup"><span data-stu-id="48593-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="48593-108">Из неупорядоченные сообщения, обработке функции в Windows Communication Foundation (WCF) позволяет создавать такой рабочий процесс исключив сложности реализации вложенных параллельных действий.</span><span class="sxs-lookup"><span data-stu-id="48593-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="48593-109">Обработка сообщений из неупорядоченные поддерживается только каналами, поддерживающими <xref:System.ServiceModel.Channels.ReceiveContext> например привязок WCF MSMQ.</span><span class="sxs-lookup"><span data-stu-id="48593-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="48593-110">Реализация обработки внеочередных сообщений</span><span class="sxs-lookup"><span data-stu-id="48593-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="48593-111">Чтобы включить обработку внеочередных сообщений, в WorkflowService установите свойство <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="48593-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="48593-112">В следующем примере кода показана установка свойства <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в коде.</span><span class="sxs-lookup"><span data-stu-id="48593-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="48593-113">Можно также применить атрибут `AllowBufferedReceive` к службе рабочих процессов в XAML, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="48593-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48593-114">См. также</span><span class="sxs-lookup"><span data-stu-id="48593-114">See also</span></span>
- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="48593-115">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="48593-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="48593-116">Очереди и надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="48593-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
