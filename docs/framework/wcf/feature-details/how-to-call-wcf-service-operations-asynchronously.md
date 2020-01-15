---
title: Практическое руководство. Асинхронный вызов операций службы WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 5eae08ab6b8dee5ebece66a1c41c87ebab3387bc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963279"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="7538d-102">Практическое руководство. Асинхронный вызов операций службы WCF</span><span class="sxs-lookup"><span data-stu-id="7538d-102">How to: Call WCF Service Operations Asynchronously</span></span>

<span data-ttu-id="7538d-103">В этой статье описывается, как клиент может асинхронно получить доступ к операции службы.</span><span class="sxs-lookup"><span data-stu-id="7538d-103">This article covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="7538d-104">Служба в этой статье реализует интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="7538d-104">The service in this article implements the `ICalculator` interface.</span></span> <span data-ttu-id="7538d-105">Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="7538d-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="7538d-106">(Дополнительные сведения о модели асинхронного вызова на основе событий см. [в разделе многопоточное программирование с асинхронной моделью, основанной на событиях](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span><span class="sxs-lookup"><span data-stu-id="7538d-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span></span> <span data-ttu-id="7538d-107">Пример, демонстрирующий асинхронную реализацию операции в службе, см. [в разделе как реализовать асинхронную операцию службы](../how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="7538d-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="7538d-108">Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [синхронные и асинхронные операции](../synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7538d-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7538d-109">Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="7538d-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="7538d-110">Дополнительные сведения о выполнении асинхронных вызовов с помощью <xref:System.ServiceModel.ChannelFactory%601>см. в разделе [инструкции. асинхронное вызов операций с помощью фабрики каналов](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="7538d-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="7538d-111">Процедура .</span><span class="sxs-lookup"><span data-stu-id="7538d-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="7538d-112">Асинхронный вызов операций службы WCF</span><span class="sxs-lookup"><span data-stu-id="7538d-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="7538d-113">Запустите средство [служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с параметрами команды `/async` и `/tcv:Version35`, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="7538d-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="7538d-114">В дополнение к синхронным и стандартным асинхронным операциям на основе делегата, клиентский класс WCF, содержащий:</span><span class="sxs-lookup"><span data-stu-id="7538d-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="7538d-115">Два <`operationName`>`Async` операции для использования с асинхронным вызовом на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7538d-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7538d-116">Например:</span><span class="sxs-lookup"><span data-stu-id="7538d-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="7538d-117">Операции завершенных событий в форме <`operationName`>`Completed` для использования с асинхронным вызовом на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7538d-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7538d-118">Например:</span><span class="sxs-lookup"><span data-stu-id="7538d-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="7538d-119"><xref:System.EventArgs?displayProperty=nameWithType> типы для каждой операции (формы <`operationName`>`CompletedEventArgs`) для использования с методом асинхронного вызова на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7538d-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7538d-120">Например:</span><span class="sxs-lookup"><span data-stu-id="7538d-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="7538d-121">В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7538d-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="7538d-122">Перед вызовом операции используйте новый универсальный <xref:System.EventHandler%601?displayProperty=nameWithType> типа <`operationName`>`EventArgs`, чтобы добавить метод обработчика (созданный на предыдущем шаге) в событие <`operationName`>`Completed`.</span><span class="sxs-lookup"><span data-stu-id="7538d-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="7538d-123">Затем вызовите метод <`operationName`>`Async`.</span><span class="sxs-lookup"><span data-stu-id="7538d-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="7538d-124">Например:</span><span class="sxs-lookup"><span data-stu-id="7538d-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="7538d-125">Пример</span><span class="sxs-lookup"><span data-stu-id="7538d-125">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7538d-126">Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="7538d-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="7538d-127">Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="7538d-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="7538d-128">При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="7538d-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="7538d-129">Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="7538d-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="7538d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="7538d-130">See also</span></span>

- [<span data-ttu-id="7538d-131">Практическое руководство. Асинхронная реализация операции службы</span><span class="sxs-lookup"><span data-stu-id="7538d-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
