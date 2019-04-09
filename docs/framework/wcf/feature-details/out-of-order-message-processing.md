---
title: Обработка неупорядоченных сообщений
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141405"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="d8af8-102">Обработка неупорядоченных сообщений</span><span class="sxs-lookup"><span data-stu-id="d8af8-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="d8af8-103">Службы рабочих процессов могут зависеть от порядка отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8af8-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="d8af8-104">Служба рабочих процессов содержит одно или несколько действий <xref:System.ServiceModel.Activities.Receive>. Каждое из этих действий <xref:System.ServiceModel.Activities.Receive> рассчитано на определенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="d8af8-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="d8af8-105">Поскольку доставка данных не гарантируется, отправляемые клиентами сообщения могут задерживаться и доставляться в порядке, на который служба рабочих процессов не рассчитана.</span><span class="sxs-lookup"><span data-stu-id="d8af8-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="d8af8-106">Реализация службы рабочих процессов, которая не требует отправки сообщений в определенном порядке, обычно осуществляется с использованием параллельных действий.</span><span class="sxs-lookup"><span data-stu-id="d8af8-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="d8af8-107">В результате усложнения протокола приложения рабочий процесс также слишком быстро становится сложным.</span><span class="sxs-lookup"><span data-stu-id="d8af8-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="d8af8-108">Из неупорядоченные сообщения, обработке функции в Windows Communication Foundation (WCF) позволяет создавать такой рабочий процесс исключив сложности реализации вложенных параллельных действий.</span><span class="sxs-lookup"><span data-stu-id="d8af8-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="d8af8-109">Обработка сообщений из неупорядоченные поддерживается только каналами, поддерживающими <xref:System.ServiceModel.Channels.ReceiveContext> например привязок WCF MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d8af8-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="d8af8-110">Реализация обработки внеочередных сообщений</span><span class="sxs-lookup"><span data-stu-id="d8af8-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="d8af8-111">Чтобы включить обработку внеочередных сообщений, в WorkflowService установите свойство <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d8af8-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="d8af8-112">В следующем примере кода показана установка свойства <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в коде.</span><span class="sxs-lookup"><span data-stu-id="d8af8-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="d8af8-113">Можно также применить атрибут `AllowBufferedReceive` к службе рабочих процессов в XAML, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d8af8-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8af8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d8af8-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="d8af8-115">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d8af8-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="d8af8-116">Очереди и надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="d8af8-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
