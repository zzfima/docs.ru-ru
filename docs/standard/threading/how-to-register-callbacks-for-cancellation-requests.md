---
title: "Практическое руководство. Регистрация обратных вызовов для запросов на отмену"
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
helpviewer_keywords: cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85b15ed610d80958ac9d7e3762ac8ea7b781b8d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="dc1eb-102">Практическое руководство. Регистрация обратных вызовов для запросов на отмену</span><span class="sxs-lookup"><span data-stu-id="dc1eb-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="dc1eb-103">Приведенный ниже показано, как зарегистрировать делегат, который будет вызываться при <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство принимает значение true, если из-за вызова <xref:System.Threading.CancellationTokenSource.Cancel%2A> в объекте, который создал токен.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="dc1eb-104">Этот прием используется для отмены асинхронных операций, в которых отсутствует встроенная поддержка унифицированной инфраструктуры отмены, а также для разблокирования методов, ожидающих завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc1eb-105">Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом".</span><span class="sxs-lookup"><span data-stu-id="dc1eb-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="dc1eb-106">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-106">This error is benign.</span></span> <span data-ttu-id="dc1eb-107">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="dc1eb-108">Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc1eb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="dc1eb-109">Example</span></span>  
 <span data-ttu-id="dc1eb-110">В примере ниже метод <xref:System.Net.WebClient.CancelAsync%2A> регистрируется в качестве метода, вызываемого при запросе отмены с помощью токена отмены.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="dc1eb-111">Если при регистрации обратного вызова отмена уже была зарегистрирована, то этот обратный вызов гарантированно будет вызван.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="dc1eb-112">В этом случае метод <xref:System.Net.WebClient.CancelAsync%2A> не выполняет никаких действий (при отсутствии выполняющихся асинхронных операций), поэтому этот метод можно вызывать всегда.</span><span class="sxs-lookup"><span data-stu-id="dc1eb-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1eb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dc1eb-113">See Also</span></span>  
 [<span data-ttu-id="dc1eb-114">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="dc1eb-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
