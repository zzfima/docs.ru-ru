---
title: "Практическое руководство. Прослушивание запросов на отмену, содержащих дескрипторы ожидания"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="2692e-102">Практическое руководство. Прослушивание запросов на отмену, содержащих дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="2692e-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="2692e-103">Если метод блокируется на время ожидания сигнала события, не может проверить значение токена отмены и своевременно ответить.</span><span class="sxs-lookup"><span data-stu-id="2692e-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="2692e-104">Первый пример показано, как решить эту проблему, при работе с событиями, такие как <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> , не поддерживаются унифицированная инфраструктура отмены.</span><span class="sxs-lookup"><span data-stu-id="2692e-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="2692e-105">Второй пример показывает более простой подход, который использует <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, который поддерживает универсальную отмену.</span><span class="sxs-lookup"><span data-stu-id="2692e-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2692e-106">Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом".</span><span class="sxs-lookup"><span data-stu-id="2692e-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2692e-107">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="2692e-107">This error is benign.</span></span> <span data-ttu-id="2692e-108">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="2692e-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2692e-109">Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.</span><span class="sxs-lookup"><span data-stu-id="2692e-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2692e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2692e-110">Example</span></span>  
 <span data-ttu-id="2692e-111">В следующем примере используется <xref:System.Threading.ManualResetEvent> для демонстрации разблокирования дескрипторов ожидания, не поддерживающих универсальную отмену.</span><span class="sxs-lookup"><span data-stu-id="2692e-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="2692e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="2692e-112">Example</span></span>  
 <span data-ttu-id="2692e-113">В следующем примере используется <xref:System.Threading.ManualResetEventSlim> для демонстрации разблокировать координации примитивы, которые поддерживают универсальную отмену.</span><span class="sxs-lookup"><span data-stu-id="2692e-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="2692e-114">Тот же подход можно использовать с других простых примитивов взаимодействия, таких как <xref:System.Threading.Semaphore> `Slim` и <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="2692e-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2692e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2692e-115">See Also</span></span>  
 [<span data-ttu-id="2692e-116">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="2692e-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
