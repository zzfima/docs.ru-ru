---
title: Группирование сообщений в очереди в рамках сеанса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 231310e5c427f507141e3c144cb02b8e848d4fbf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185159"
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="afa30-102">Группирование сообщений в очереди в рамках сеанса</span><span class="sxs-lookup"><span data-stu-id="afa30-102">Grouping Queued Messages in a Session</span></span>
<span data-ttu-id="afa30-103">Windows Communication Foundation (WCF) предоставляет сеанс, который позволяет группировать набор связанных сообщений для обработки одним приемным приложением.</span><span class="sxs-lookup"><span data-stu-id="afa30-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="afa30-104">Сообщения, являющиеся частью сеанса, должны быть часть одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="afa30-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="afa30-105">Так как все сообщения являются частью одной транзакции, в случае сбоя обработки одного сообщения производится откат всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="afa30-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="afa30-106">Сеансы имеют аналогичные поведения в отношении очередей недоставленных сообщений и очередей подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="afa30-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="afa30-107">Свойство "срок жизни" (TTL), заданное в настроенной для сеансов привязке, поддерживающей очередь, применяется ко всему сеансу.</span><span class="sxs-lookup"><span data-stu-id="afa30-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="afa30-108">Если до истечения срока TTL отправлена только часть сообщений из сеанса, весь сеанс помещается в очередь недоставленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="afa30-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="afa30-109">Аналогично, если сообщения из сеанса не отправлены приложению из очереди приложения, весь сеанс помещается в очередь подозрительных сообщений (при наличии).</span><span class="sxs-lookup"><span data-stu-id="afa30-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="afa30-110">Пример группирования сообщений</span><span class="sxs-lookup"><span data-stu-id="afa30-110">Message Grouping Example</span></span>  
 <span data-ttu-id="afa30-111">Одним из примеров, когда группировка сообщений полезна, является реализация приложения для обработки заказов в качестве службы WCF.</span><span class="sxs-lookup"><span data-stu-id="afa30-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="afa30-112">Например, клиент передает в это приложение заказ, содержащий несколько позиций.</span><span class="sxs-lookup"><span data-stu-id="afa30-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="afa30-113">Для каждой позиции клиент вызывает службу, что приводит к отправке отдельного сообщения.</span><span class="sxs-lookup"><span data-stu-id="afa30-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="afa30-114">Возможно, что первая позиция будет получена сервером A, а вторая позиция - сервером B.</span><span class="sxs-lookup"><span data-stu-id="afa30-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="afa30-115">При каждом добавлении позиции сервер, обрабатывающий эту позицию, должен найти соответствующий заказ и добавить в него позицию, что крайне неэффективно.</span><span class="sxs-lookup"><span data-stu-id="afa30-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="afa30-116">Низкая эффективность работы сохраняется и в случае, когда все запросы обрабатываются одним сервером, так как сервер должен отслеживать все текущие обрабатываемые заказы и определять, к какому из них относится новая позиция.</span><span class="sxs-lookup"><span data-stu-id="afa30-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="afa30-117">Группирование всех запросов для одного заказа значительно упрощает реализацию такого приложения.</span><span class="sxs-lookup"><span data-stu-id="afa30-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="afa30-118">Клиентское приложение отправляет все позиции для одного заказа в сеансе, поэтому когда служба обрабатывает заказ, она обрабатывает сразу весь сеанс.</span><span class="sxs-lookup"><span data-stu-id="afa30-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="afa30-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="afa30-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="afa30-120">Настройка контракта службы для использования сеансов</span><span class="sxs-lookup"><span data-stu-id="afa30-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="afa30-121">Определите контракт службы, для которого требуются сеансы.</span><span class="sxs-lookup"><span data-stu-id="afa30-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="afa30-122">Сделайте это <xref:System.ServiceModel.ServiceContractAttribute> с атрибутом, указав:</span><span class="sxs-lookup"><span data-stu-id="afa30-122">Do this with the <xref:System.ServiceModel.ServiceContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="afa30-123">Пометьте операции в контракте как односторонние, так как эти методы ничего не возвращают.</span><span class="sxs-lookup"><span data-stu-id="afa30-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="afa30-124">Это делается <xref:System.ServiceModel.OperationContractAttribute> с атрибутом, указывая:</span><span class="sxs-lookup"><span data-stu-id="afa30-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="afa30-125">Реализуйте контракт службы и укажите для <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> значение <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="afa30-125">Implement the service contract and specify an <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span></span> <span data-ttu-id="afa30-126">В результате для каждого сеанса создается только один экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="afa30-126">This instantiates the service only once for each session.</span></span>  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="afa30-127">Для каждой операции службы требуется транзакция.</span><span class="sxs-lookup"><span data-stu-id="afa30-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="afa30-128">Это задается с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="afa30-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="afa30-129">Для операции, завершающей транзакцию, параметр <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> должен иметь значение `true`.</span><span class="sxs-lookup"><span data-stu-id="afa30-129">The operation that completes the transaction should also set <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> to `true`.</span></span>  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. <span data-ttu-id="afa30-130">Настройте конечную точку, использующую предоставляемую системой привязку `NetMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="afa30-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="afa30-131">Создайте очередь транзакций с использованием <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="afa30-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="afa30-132">Можно также создать очередь с помощью MSMQ или MMC.</span><span class="sxs-lookup"><span data-stu-id="afa30-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="afa30-133">В таком случае создайте транзакционную очередь.</span><span class="sxs-lookup"><span data-stu-id="afa30-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="afa30-134">Создайте узел для данной службы с помощью <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="afa30-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="afa30-135">Откройте узел службы для обеспечения доступности службы.</span><span class="sxs-lookup"><span data-stu-id="afa30-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="afa30-136">Закройте узел службы.</span><span class="sxs-lookup"><span data-stu-id="afa30-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="afa30-137">Настройка клиента</span><span class="sxs-lookup"><span data-stu-id="afa30-137">To set up a client</span></span>  
  
1. <span data-ttu-id="afa30-138">Создайте область транзакции для записи в транзакционную очередь.</span><span class="sxs-lookup"><span data-stu-id="afa30-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="afa30-139">Создайте клиент WCF с помощью инструмента [ServiceModel Metadata Utility Tool (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)</span><span class="sxs-lookup"><span data-stu-id="afa30-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="afa30-140">Сделайте заказ.</span><span class="sxs-lookup"><span data-stu-id="afa30-140">Place the order.</span></span>  
  
4. <span data-ttu-id="afa30-141">Закройте клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="afa30-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa30-142">Пример</span><span class="sxs-lookup"><span data-stu-id="afa30-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="afa30-143">Описание</span><span class="sxs-lookup"><span data-stu-id="afa30-143">Description</span></span>  
 <span data-ttu-id="afa30-144">В следующем примере приводится код для службы `IProcessOrder` и клиента, использующего эту службу.</span><span class="sxs-lookup"><span data-stu-id="afa30-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="afa30-145">Он показывает, как WCF использует сеансы в очереди для обеспечения поведения группирования.</span><span class="sxs-lookup"><span data-stu-id="afa30-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="afa30-146">Код для службы</span><span class="sxs-lookup"><span data-stu-id="afa30-146">Code for the Service</span></span>  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="afa30-147">Код для клиента</span><span class="sxs-lookup"><span data-stu-id="afa30-147">Code for the Client</span></span>  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="afa30-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afa30-148">See also</span></span>

- [<span data-ttu-id="afa30-149">Сеансы и очереди</span><span class="sxs-lookup"><span data-stu-id="afa30-149">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [<span data-ttu-id="afa30-150">Общие сведения об очередях</span><span class="sxs-lookup"><span data-stu-id="afa30-150">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
