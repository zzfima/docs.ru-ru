---
title: Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: ab6ca46fad8ee1ededef5cc14a9654b79b2e6a8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494661"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="b05cc-102">Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF</span><span class="sxs-lookup"><span data-stu-id="b05cc-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="b05cc-103">Очереди обеспечивают возникновение надежный обмен сообщениями между клиентом и службой Windows Communication Foundation (WCF), даже если служба недоступна во время обмена данными.</span><span class="sxs-lookup"><span data-stu-id="b05cc-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="b05cc-104">Ниже показана методика обеспечения устойчивого взаимодействия между клиентом и службой за счет использования стандартной поставленной в очередь привязки при реализации службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b05cc-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="b05cc-105">В этом разделе описывается использование <xref:System.ServiceModel.NetMsmqBinding> для взаимодействия с использованием очередей между клиентом WCF и службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b05cc-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="b05cc-106">Использование очередей в службе WCF.</span><span class="sxs-lookup"><span data-stu-id="b05cc-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="b05cc-107">Определите контракт службы с использованием интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b05cc-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="b05cc-108">Пометьте операции в интерфейсе, которые являются частью контракта службы с <xref:System.ServiceModel.OperationContractAttribute> и задайте их как односторонние, так как методу ответ не возвращается.</span><span class="sxs-lookup"><span data-stu-id="b05cc-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="b05cc-109">Следующий код представляет пример контракта службы и определение его операций.</span><span class="sxs-lookup"><span data-stu-id="b05cc-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="b05cc-110">Необходимо определить контракты данных для определяемых пользователем типов, если их передает контракт службы.</span><span class="sxs-lookup"><span data-stu-id="b05cc-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="b05cc-111">В следующем коде показано два контракта данных - `PurchaseOrder` и `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="b05cc-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="b05cc-112">Эти два типа определяют данные, отправляемые службе.</span><span class="sxs-lookup"><span data-stu-id="b05cc-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="b05cc-113">(Обратите внимание, что классы, определяющие этот контракт данных, определяют и число методов.</span><span class="sxs-lookup"><span data-stu-id="b05cc-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="b05cc-114">Эти методы не являются частью контракта данных.</span><span class="sxs-lookup"><span data-stu-id="b05cc-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="b05cc-115">Частью контракта данных являются только члены, объявленные с атрибутом `DataMember`.)</span><span class="sxs-lookup"><span data-stu-id="b05cc-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="b05cc-116">Реализуйте методы контракта службы, определенные в интерфейсе в классе.</span><span class="sxs-lookup"><span data-stu-id="b05cc-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="b05cc-117">Заметьте, что в методе <xref:System.ServiceModel.OperationBehaviorAttribute> указывается атрибут `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="b05cc-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="b05cc-118">Это значит, что данная операция должна вызываться в рамках транзакции, которая автоматически завершается при завершении метода.</span><span class="sxs-lookup"><span data-stu-id="b05cc-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="b05cc-119">Создайте очередь транзакций с использованием <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="b05cc-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="b05cc-120">Вместо этого можно создать очередь с использованием консоли управления (MMC) «Очередь сообщений Майкрософт (MSMQ)».</span><span class="sxs-lookup"><span data-stu-id="b05cc-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="b05cc-121">В этом случае убедитесь, что создается очередь транзакций.</span><span class="sxs-lookup"><span data-stu-id="b05cc-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="b05cc-122">Определите класс <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая задает адрес службы и использует стандартную привязку <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="b05cc-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="b05cc-123">Дополнительные сведения об использовании конфигурации WCF см. в разделе [Настройка приложений Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="b05cc-123">For more information about using WCF configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="b05cc-124">Создайте узел для службы `OrderProcessing` с использованием <xref:System.ServiceModel.ServiceHost>, считывающий и обрабатывающий сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="b05cc-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="b05cc-125">Откройте узел службы для обеспечения доступности службы.</span><span class="sxs-lookup"><span data-stu-id="b05cc-125">Open the service host to make the service available.</span></span> <span data-ttu-id="b05cc-126">Выведите для пользователя сообщение о том, что нужно нажать любую клавишу для завершения службы.</span><span class="sxs-lookup"><span data-stu-id="b05cc-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="b05cc-127">Вызовите метод `ReadLine`, чтобы включить ожидания нажатия клавиши, а затем закройте службу.</span><span class="sxs-lookup"><span data-stu-id="b05cc-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="b05cc-128">Создание клиента для службы в очереди</span><span class="sxs-lookup"><span data-stu-id="b05cc-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="b05cc-129">В следующем примере показано, как запустить ведущее приложение и использовать средство Svcutil.exe для создания клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="b05cc-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="b05cc-130">Определите объект <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая указывает адрес и использует стандартную привязку <xref:System.ServiceModel.NetMsmqBinding>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b05cc-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="b05cc-131">Создайте область транзакции для записи в очередь транзакций, вызовите `SubmitPurchaseOrder` операции и закрытие клиента WCF, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b05cc-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="b05cc-132">Пример</span><span class="sxs-lookup"><span data-stu-id="b05cc-132">Example</span></span>  
 <span data-ttu-id="b05cc-133">В следующих примерах показан код службы, ведущее приложение, файл App.config и код клиента для этого примера.</span><span class="sxs-lookup"><span data-stu-id="b05cc-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="b05cc-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b05cc-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="b05cc-135">Привязка MSMQ с поддержкой транзакций</span><span class="sxs-lookup"><span data-stu-id="b05cc-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="b05cc-136">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="b05cc-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="b05cc-137">Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="b05cc-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="b05cc-138">Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="b05cc-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="b05cc-139">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="b05cc-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="b05cc-140">Образцы привязки интеграции очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="b05cc-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="b05cc-141">Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b05cc-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="b05cc-142">Безопасность сообщений при использовании очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="b05cc-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
