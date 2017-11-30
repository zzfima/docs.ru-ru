---
title: "Практическое руководство. Прослушивание нескольких запросов на отмену"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="cc6a2-102">Практическое руководство. Прослушивание нескольких запросов на отмену</span><span class="sxs-lookup"><span data-stu-id="cc6a2-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="cc6a2-103">В этом примере показано, как для ожидания передачи данных двумя токенами отмены одновременно, чтобы можно было отменить операцию, если любой из токенов запрашивает ее.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc6a2-104">Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом".</span><span class="sxs-lookup"><span data-stu-id="cc6a2-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="cc6a2-105">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-105">This error is benign.</span></span> <span data-ttu-id="cc6a2-106">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="cc6a2-107">Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc6a2-108">Пример</span><span class="sxs-lookup"><span data-stu-id="cc6a2-108">Example</span></span>  
 <span data-ttu-id="cc6a2-109">В следующем примере <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> метод используется для объединения двух токенов в один токен.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="cc6a2-110">Это позволяет токен должен быть передан методов, которые принимают в качестве аргумента токен отмены лишь один.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="cc6a2-111">В примере демонстрируется типичный сценарий, в котором метод должен учитывать как токен, переданный из вне класса и токен, созданный внутри класса.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="cc6a2-112">Если связанный токен создает <xref:System.OperationCanceledException>, маркер, который передается на исключение является связанный токен, а не один из предшествующих токенов.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="cc6a2-113">Чтобы определить, какой из токенов был отменен, проверьте состояние предшествующих токенов напрямую.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="cc6a2-114">В этом примере <xref:System.AggregateException> никогда не должны создаваться, но оно возникает из-за в реальных сценариях другие исключения, кроме <xref:System.OperationCanceledException> , возникающие из делегата задачи упаковываются в <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="cc6a2-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6a2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc6a2-115">See Also</span></span>  
 [<span data-ttu-id="cc6a2-116">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="cc6a2-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
