---
title: Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f44f3a58e0a8283753cb682f25cf2f167450724
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="a11a6-102">Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF</span><span class="sxs-lookup"><span data-stu-id="a11a6-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="a11a6-103">Очереди обеспечивают возможность надежного обмена сообщениями между клиентом и службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], даже если служба недоступна в процессе взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a11a6-103">Queues ensure that reliable messaging can occur between a client and a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="a11a6-104">В процедурах ниже показана методика обеспечения устойчивого взаимодействия между клиентом и службой за счет использования стандартной поставленной в очередь привязки при реализации службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a11a6-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="a11a6-105">В этом разделе объясняется, как использовать класс <xref:System.ServiceModel.NetMsmqBinding> для взаимодействия с использованием очередей между клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a11a6-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="a11a6-106">Использование очередей в службе WCF.</span><span class="sxs-lookup"><span data-stu-id="a11a6-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="a11a6-107">Определите контракт службы с использованием интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a11a6-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="a11a6-108">Пометьте операции в интерфейсе, которые являются частью контракта службы с <xref:System.ServiceModel.OperationContractAttribute> и задайте их как односторонние, так как методу ответ не возвращается.</span><span class="sxs-lookup"><span data-stu-id="a11a6-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="a11a6-109">Следующий код представляет пример контракта службы и определение его операций.</span><span class="sxs-lookup"><span data-stu-id="a11a6-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="a11a6-110">Необходимо определить контракты данных для определяемых пользователем типов, если их передает контракт службы.</span><span class="sxs-lookup"><span data-stu-id="a11a6-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="a11a6-111">В следующем коде показано два контракта данных - `PurchaseOrder` и `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="a11a6-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="a11a6-112">Эти два типа определяют данные, отправляемые службе.</span><span class="sxs-lookup"><span data-stu-id="a11a6-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="a11a6-113">(Обратите внимание, что классы, определяющие этот контракт данных, определяют и число методов.</span><span class="sxs-lookup"><span data-stu-id="a11a6-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="a11a6-114">Эти методы не являются частью контракта данных.</span><span class="sxs-lookup"><span data-stu-id="a11a6-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="a11a6-115">Частью контракта данных являются только члены, объявленные с атрибутом `DataMember`.)</span><span class="sxs-lookup"><span data-stu-id="a11a6-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="a11a6-116">Реализуйте методы контракта службы, определенные в интерфейсе в классе.</span><span class="sxs-lookup"><span data-stu-id="a11a6-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="a11a6-117">Заметьте, что в методе <xref:System.ServiceModel.OperationBehaviorAttribute> указывается атрибут `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="a11a6-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="a11a6-118">Это значит, что данная операция должна вызываться в рамках транзакции, которая автоматически завершается при завершении метода.</span><span class="sxs-lookup"><span data-stu-id="a11a6-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="a11a6-119">Создайте очередь транзакций с использованием <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="a11a6-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="a11a6-120">Вместо этого можно создать очередь с использованием консоли управления (MMC) «Очередь сообщений Майкрософт (MSMQ)».</span><span class="sxs-lookup"><span data-stu-id="a11a6-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="a11a6-121">В этом случае убедитесь, что создается очередь транзакций.</span><span class="sxs-lookup"><span data-stu-id="a11a6-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="a11a6-122">Определите класс <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая задает адрес службы и использует стандартную привязку <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="a11a6-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="a11a6-123">Дополнительные сведения об использовании [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конфигурации, в разделе [Настройка приложений Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="a11a6-123">For more information about using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="a11a6-124">Создайте узел для службы `OrderProcessing` с использованием <xref:System.ServiceModel.ServiceHost>, считывающий и обрабатывающий сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="a11a6-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="a11a6-125">Откройте узел службы для обеспечения доступности службы.</span><span class="sxs-lookup"><span data-stu-id="a11a6-125">Open the service host to make the service available.</span></span> <span data-ttu-id="a11a6-126">Выведите для пользователя сообщение о том, что нужно нажать любую клавишу для завершения службы.</span><span class="sxs-lookup"><span data-stu-id="a11a6-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="a11a6-127">Вызовите метод `ReadLine`, чтобы включить ожидания нажатия клавиши, а затем закройте службу.</span><span class="sxs-lookup"><span data-stu-id="a11a6-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="a11a6-128">Создание клиента для службы в очереди</span><span class="sxs-lookup"><span data-stu-id="a11a6-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="a11a6-129">В следующем примере показано, как запустить ведущее приложение и использовать программу Svcutil.exe для создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a11a6-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="a11a6-130">Определите объект <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая указывает адрес и использует стандартную привязку <xref:System.ServiceModel.NetMsmqBinding>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a11a6-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="a11a6-131">Создайте область транзакции для записи в очередь транзакций, вызовите операцию `SubmitPurchaseOrder` и закройте клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a11a6-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="a11a6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="a11a6-132">Example</span></span>  
 <span data-ttu-id="a11a6-133">В следующих примерах показан код службы, ведущее приложение, файл App.config и код клиента для этого примера.</span><span class="sxs-lookup"><span data-stu-id="a11a6-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="a11a6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a11a6-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="a11a6-135">Привязка MSMQ с поддержкой транзакций</span><span class="sxs-lookup"><span data-stu-id="a11a6-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="a11a6-136">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="a11a6-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="a11a6-137">Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="a11a6-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="a11a6-138">Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="a11a6-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="a11a6-139">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="a11a6-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="a11a6-140">Образцы привязки интеграции очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="a11a6-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="a11a6-141">Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a11a6-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="a11a6-142">Безопасность сообщений при использовании очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="a11a6-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
