---
title: Как выполнить Реализация формы, в который выполняется фоновая операция
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
ms.openlocfilehash: a472226103f077975c9c6ddc744d419cfcc390cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532140"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="f8c47-102">Как выполнить Реализация формы, в который выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="f8c47-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="f8c47-103">В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="f8c47-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="f8c47-104">Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.</span><span class="sxs-lookup"><span data-stu-id="f8c47-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="f8c47-105">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="f8c47-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="f8c47-106">Также см. в разделе [Пошаговое руководство: Реализация формы, в который выполняется фоновая операция](https://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f8c47-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](https://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8c47-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f8c47-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8c47-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8c47-108">Compiling the Code</span></span>  
 <span data-ttu-id="f8c47-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f8c47-109">This example requires:</span></span>  
  
-   <span data-ttu-id="f8c47-110">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f8c47-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f8c47-111">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f8c47-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f8c47-112">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="f8c47-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="f8c47-113">Также см. раздел [Как Компиляция и выполнение примера кода завершения Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f8c47-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f8c47-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f8c47-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f8c47-115">При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="f8c47-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="f8c47-116">Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../../docs/standard/threading/managed-threading-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="f8c47-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c47-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f8c47-117">See also</span></span>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="f8c47-118">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="f8c47-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="f8c47-119">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="f8c47-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
