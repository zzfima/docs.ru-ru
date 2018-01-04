---
title: "Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fec4a82ca2b6b5affce3ef3934a86adcd52a5b4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a><span data-ttu-id="0054c-102">Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов</span><span class="sxs-lookup"><span data-stu-id="0054c-102">How to: Call Operations Asynchronously Using a Channel Factory</span></span>
<span data-ttu-id="0054c-103">В этой теме описывается, каким образом клиент может асинхронно обратиться к операции службы при использовании клиентского приложения, основанного на <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="0054c-103">This topic covers how a client can access a service operation asynchronously when using a <xref:System.ServiceModel.ChannelFactory%601>-based client application.</span></span> <span data-ttu-id="0054c-104">(При вызове службы с помощью объекта <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> можно использовать управляемую событиями модель асинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="0054c-104">(When using a <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> object to invoke a service you can use the event-driven asynchronous calling model.</span></span> <span data-ttu-id="0054c-105">Дополнительные сведения см. в разделе [как: асинхронно вызывать операции службы](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="0054c-105">For more information, see [How to: Call Service Operations Asynchronously](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="0054c-106">Дополнительные сведения о на основе событий асинхронного вызова модели см. в разделе [многопоточного программирования с использованием асинхронной модели, основанной на событиях](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).)</span><span class="sxs-lookup"><span data-stu-id="0054c-106">For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).)</span></span>  
  
 <span data-ttu-id="0054c-107">Служба в этом разделе реализует интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="0054c-107">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="0054c-108">Клиент может асинхронно вызвать операции для этого интерфейса, это означает, что операции типа `Add` разделяются на два метода, `BeginAdd` и `EndAdd`, первый из них инициирует вызов, а второй извлекает результат после завершения операции.</span><span class="sxs-lookup"><span data-stu-id="0054c-108">The client can call the operations on this interface asynchronously, which means that operations like `Add` are split into two methods, `BeginAdd` and `EndAdd`, the former of which initiates the call and the latter of which retrieves the result when the operation completes.</span></span> <span data-ttu-id="0054c-109">Пример, показывающий, как реализовать операцию асинхронно, в службе см. в разделе [как: реализация асинхронной операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="0054c-109">For an example showing how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="0054c-110">Дополнительные сведения о синхронные и асинхронные операции в разделе [синхронной и асинхронной операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0054c-110">For details about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="0054c-111">Процедура</span><span class="sxs-lookup"><span data-stu-id="0054c-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="0054c-112">Асинхронный вызов операций службы WCF</span><span class="sxs-lookup"><span data-stu-id="0054c-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="0054c-113">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) со `/async` как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="0054c-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with the `/async` option as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     <span data-ttu-id="0054c-114">Результатом станет создание асинхронной версии клиента контракта службы для операции.</span><span class="sxs-lookup"><span data-stu-id="0054c-114">This generates an asynchronous client version of the service contract for the operation.</span></span>  
  
2.  <span data-ttu-id="0054c-115">Создайте функцию обратного вызова, вызываемую после завершения асинхронной операции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0054c-115">Create a callback function to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  <span data-ttu-id="0054c-116">Чтобы асинхронно обратиться к операции службы, создайте клиент и вызовите `Begin[Operation]` (например `BeginAdd`) и задайте функцию обратного вызова, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0054c-116">To access a service operation asynchronously, create the client and call the `Begin[Operation]` (for example, `BeginAdd`) and specify a callback function, as shown in the following sample code.</span></span>  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     <span data-ttu-id="0054c-117">При выполнении функции обратного вызова клиент вызывает `End<operation>` (например `EndAdd`), чтобы извлечь результат.</span><span class="sxs-lookup"><span data-stu-id="0054c-117">When the callback function executes, the client calls `End<operation>` (for example, `EndAdd`) to retrieve the result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0054c-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0054c-118">Example</span></span>  
 <span data-ttu-id="0054c-119">Служба, используемая с клиентским кодом, который применяется в предыдущей процедуре, реализует интерфейс `ICalculator`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0054c-119">The service that is used with the client code that is used in the preceding procedure implements the `ICalculator` interface as shown in the following code.</span></span> <span data-ttu-id="0054c-120">На стороне службы операции контракта `Add` и `Subtract` вызываются синхронно во время выполнения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], даже если на предыдущих этапах клиента выполнялся асинхронный вызов для клиента.</span><span class="sxs-lookup"><span data-stu-id="0054c-120">On the service side, the `Add` and `Subtract` operations of the contract are invoked synchronously by the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] run time, even though the preceding client steps are invoked asynchronously on the client.</span></span> <span data-ttu-id="0054c-121">Операции `Multiply` и `Divide` используются для асинхронного вызова службы на стороне службы, даже если клиент вызывает их синхронно.</span><span class="sxs-lookup"><span data-stu-id="0054c-121">The `Multiply` and `Divide` operations are used to invoke the service asynchronously on the service side, even if the client invokes them synchronously.</span></span> <span data-ttu-id="0054c-122">В этом примере свойству <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> присваивается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0054c-122">This example sets the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property to `true`.</span></span> <span data-ttu-id="0054c-123">Этот параметр свойства в сочетании с реализацией асинхронной модели [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] сообщает среде выполнения о необходимости асинхронного вызова операции.</span><span class="sxs-lookup"><span data-stu-id="0054c-123">This property setting, in combination with the implementation of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] asynchronous pattern, tells the run time to invoke the operation asynchronously.</span></span>  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0054c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0054c-124">See Also</span></span>  
 [<span data-ttu-id="0054c-125">Контракт службы: Пример асинхронного</span><span class="sxs-lookup"><span data-stu-id="0054c-125">Service Contract: Asynchronous Sample</span></span>](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7)
