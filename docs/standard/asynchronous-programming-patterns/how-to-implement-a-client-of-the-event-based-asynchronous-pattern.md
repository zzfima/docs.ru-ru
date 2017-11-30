---
title: "Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях"
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
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="e4e34-102">Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="e4e34-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="e4e34-103">В следующем примере кода показано, как использовать компонент, который соответствует [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4e34-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="e4e34-104">В форме, в этом примере используется `PrimeNumberCalculator` компонента, описываемые в [как: реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="e4e34-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="e4e34-105">При запуске проекта, использующего в этом примере вы увидите «Calculator простых чисел» формы с сеткой и две кнопки: **новая задача** и **отменить**.</span><span class="sxs-lookup"><span data-stu-id="e4e34-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="e4e34-106">Можно щелкнуть **новая задача** несколько раз подряд, и для каждого нажатия асинхронной операции начинается вычисление, чтобы определить, является ли число случайным образом созданный тест простым.</span><span class="sxs-lookup"><span data-stu-id="e4e34-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="e4e34-107">В форме будет периодически отображаться ход выполнения и добавочных результатов.</span><span class="sxs-lookup"><span data-stu-id="e4e34-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="e4e34-108">Каждой операции присвоен уникальный идентификатор задачи.</span><span class="sxs-lookup"><span data-stu-id="e4e34-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="e4e34-109">Результат вычисления отображается в **результат** столбца; Если проверяемое число не является простым, оно помечается как **составной,** и отображается первый делитель.</span><span class="sxs-lookup"><span data-stu-id="e4e34-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="e4e34-110">Все ожидающие операции может быть отменена с **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="e4e34-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="e4e34-111">Можно сделать выбор нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="e4e34-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4e34-112">Большинство чисел не будут простыми.</span><span class="sxs-lookup"><span data-stu-id="e4e34-112">Most numbers will not be prime.</span></span> <span data-ttu-id="e4e34-113">Если после нескольких завершенных операций не найдены простых чисел, просто запустите дополнительные задачи, и в итоге вы найдете некоторые простые числа.</span><span class="sxs-lookup"><span data-stu-id="e4e34-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4e34-114">Пример</span><span class="sxs-lookup"><span data-stu-id="e4e34-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="e4e34-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4e34-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
