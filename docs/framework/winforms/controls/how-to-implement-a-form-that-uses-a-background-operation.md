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
ms.openlocfilehash: df7c6caf7b23824a596e94e1bd62205907b0b56a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592408"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4d152-102">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="4d152-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="4d152-103">В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="4d152-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="4d152-104">Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.</span><span class="sxs-lookup"><span data-stu-id="4d152-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="4d152-105">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="4d152-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="4d152-106">Также см. в разделе [Пошаговое руководство: Реализация формы, в который выполняется фоновая операция](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4d152-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d152-107">Пример</span><span class="sxs-lookup"><span data-stu-id="4d152-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d152-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4d152-108">Compiling the Code</span></span>  
 <span data-ttu-id="4d152-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4d152-109">This example requires:</span></span>  
  
- <span data-ttu-id="4d152-110">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4d152-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4d152-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4d152-111">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4d152-112">При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="4d152-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="4d152-113">Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../standard/threading/managed-threading-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="4d152-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d152-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4d152-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="4d152-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="4d152-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="4d152-116">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="4d152-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
