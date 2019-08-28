---
title: Практическое руководство. Реализация формы, в которой выполняется фоновая операция
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: e06b18558f6b3fa3cef47613bbaef16fb7c740f0
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046192"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="dc8a0-102">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="dc8a0-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="dc8a0-103">В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="dc8a0-104">Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="dc8a0-105">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="dc8a0-106">См. [также раздел Пошаговое руководство. Реализация формы, использующей фоновую операцию](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="dc8a0-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc8a0-107">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8a0-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc8a0-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="dc8a0-108">Compiling the Code</span></span>  
 <span data-ttu-id="dc8a0-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="dc8a0-109">This example requires:</span></span>  
  
- <span data-ttu-id="dc8a0-110">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dc8a0-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="dc8a0-111">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="dc8a0-112">При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="dc8a0-113">Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../standard/threading/managed-threading-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="dc8a0-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8a0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dc8a0-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="dc8a0-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="dc8a0-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="dc8a0-116">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="dc8a0-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
