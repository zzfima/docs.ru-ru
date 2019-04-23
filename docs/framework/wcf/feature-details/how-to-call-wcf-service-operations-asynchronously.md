---
title: Практическое руководство. Асинхронный вызов операций службы WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2815757bf9b00375f763673f18180bfbf51a165a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317451"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="18218-102">Практическое руководство. Асинхронный вызов операций службы WCF</span><span class="sxs-lookup"><span data-stu-id="18218-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="18218-103">В этом разделе описано, каким образом клиент может асинхронно обратиться к операции службы.</span><span class="sxs-lookup"><span data-stu-id="18218-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="18218-104">Служба в этом разделе реализует интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="18218-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="18218-105">Клиент может асинхронно вызывать операции этого интерфейса с помощью управляемой событиями модели асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="18218-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="18218-106">(Дополнительные сведения об управляемой событиями модели асинхронного вызова см. в разделе [многопоточное программирование с использованием асинхронной модели на основе событий](https://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="18218-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="18218-107">Пример, в котором демонстрируется реализация асинхронной операции в службе, см. в разделе [как: Реализация асинхронной операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="18218-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="18218-108">Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [синхронные и асинхронные операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="18218-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18218-109">Управляемая событиями модель асинхронных вызовов не поддерживается при использовании класса <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="18218-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="18218-110">Сведения об асинхронных вызовах с использованием <xref:System.ServiceModel.ChannelFactory%601>, см. в разделе [как: Вызов операций асинхронно с использованием фабрики каналов](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="18218-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="18218-111">Процедура</span><span class="sxs-lookup"><span data-stu-id="18218-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="18218-112">Асинхронный вызов операций службы WCF</span><span class="sxs-lookup"><span data-stu-id="18218-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="18218-113">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство с обоими `/async` и `/tcv:Version35` параметрами командной строки как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="18218-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="18218-114">Это приводит к возникновению ошибки, помимо синхронной операции и стандартной делегатов асинхронными операциями, класс клиента WCF, который содержит:</span><span class="sxs-lookup"><span data-stu-id="18218-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    -   <span data-ttu-id="18218-115">Два <`operationName` > `Async` операций для использования с основанной на событиях асинхронных вызовами.</span><span class="sxs-lookup"><span data-stu-id="18218-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="18218-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="18218-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="18218-117">События с завершенными операциями в форме <`operationName` > `Completed` для использования с основанной на событиях асинхронных вызовами.</span><span class="sxs-lookup"><span data-stu-id="18218-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="18218-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="18218-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <span data-ttu-id="18218-119"><xref:System.EventArgs?displayProperty=nameWithType> типы для каждой операции (в формате <`operationName`>`CompletedEventArgs`) для использования с основанной на событиях асинхронных вызовами.</span><span class="sxs-lookup"><span data-stu-id="18218-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="18218-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="18218-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="18218-121">В вызывающем приложении создайте метод обратного вызова, вызываемый после завершения асинхронной операции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="18218-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="18218-122">Перед вызовом операции используйте новый универсальный <xref:System.EventHandler%601?displayProperty=nameWithType> типа <`operationName` > `EventArgs` добавляемый метод обработчика (созданный на предыдущем шаге) <`operationName` > `Completed` событий.</span><span class="sxs-lookup"><span data-stu-id="18218-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="18218-123">Затем вызовите <`operationName` > `Async` метод.</span><span class="sxs-lookup"><span data-stu-id="18218-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="18218-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="18218-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="18218-125">Пример</span><span class="sxs-lookup"><span data-stu-id="18218-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18218-126">Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="18218-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="18218-127">Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>. Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="18218-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="18218-128">При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="18218-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="18218-129">Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="18218-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="18218-130">См. также</span><span class="sxs-lookup"><span data-stu-id="18218-130">See also</span></span>

- [<span data-ttu-id="18218-131">Практическое руководство. Реализация асинхронной операции службы</span><span class="sxs-lookup"><span data-stu-id="18218-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
