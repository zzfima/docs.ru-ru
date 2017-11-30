---
title: "Запрос состояния асинхронной операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="7ce2e-102">Запрос состояния асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="7ce2e-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="7ce2e-103">Приложения, которые могут выполнять другую работу во время ожидания результатов асинхронной операции не должны блокировать ожидание до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="7ce2e-104">Для продолжения выполнения инструкций при ожидании завершения асинхронной операции, используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7ce2e-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="7ce2e-105">Используйте <xref:System.IAsyncResult.IsCompleted%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод, чтобы определить, завершена ли операция.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="7ce2e-106">Такой подход известен как запрос и демонстрируются в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="7ce2e-107">Используйте <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="7ce2e-108">Пример, демонстрирующий этот способ см. в разделе [использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="7ce2e-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ce2e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7ce2e-109">Example</span></span>  
 <span data-ttu-id="7ce2e-110">В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен для компьютера, заданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="7ce2e-111">В этом примере запускает асинхронную операцию, а затем выводятся точки («.») с помощью консоли до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="7ce2e-112">Обратите внимание, что **null** (**ничего** в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> и <xref:System.Object> параметры так, как эти параметры не являются обязательными при использовании такого подхода.</span><span class="sxs-lookup"><span data-stu-id="7ce2e-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7ce2e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce2e-113">See Also</span></span>  
 [<span data-ttu-id="7ce2e-114">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="7ce2e-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="7ce2e-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="7ce2e-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
