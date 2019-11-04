---
title: Запрос состояния асинхронной операции
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: ff9cefc73adfe1ece1bf7545c75ccb6cc618e89f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123964"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="e5fc2-102">Запрос состояния асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="e5fc2-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="e5fc2-103">Приложения, которые могут выполнять работу во время ожидания результатов асинхронной операции, не должны блокироваться до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="e5fc2-104">Используйте один из следующих вариантов, чтобы продолжить выполнение инструкций в период ожидания асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="e5fc2-105">Чтобы определить, завершена ли операция, используется свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin**_имя_операции_ асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="e5fc2-106">Именно этот подход, именуемый стратегией опросов, демонстрируется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="e5fc2-107">Используйте делегат <xref:System.AsyncCallback> для обработки результатов асинхронной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="e5fc2-108">Пример, демонстрирующий этот подход, см. в разделе [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="e5fc2-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5fc2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e5fc2-109">Example</span></span>  
 <span data-ttu-id="e5fc2-110">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="e5fc2-111">Код примера запускает асинхронную операцию, а затем выводит в консоль точки (".") до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="e5fc2-112">Обратите внимание, что в параметрах <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> и <xref:System.Object> передается значение **NULL** (**Nothing** в Visual Basic), так как при таком подходе эти аргументы не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="e5fc2-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e5fc2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e5fc2-113">See also</span></span>

- [<span data-ttu-id="e5fc2-114">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="e5fc2-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="e5fc2-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="e5fc2-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
