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
ms.openlocfilehash: 5923895e1e6cf86f8de30405dbfdb0a603d708d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="9ea41-102">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="9ea41-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="9ea41-103">В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="9ea41-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="9ea41-104">Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.</span><span class="sxs-lookup"><span data-stu-id="9ea41-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="9ea41-105">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="9ea41-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="9ea41-106">См. также [Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9ea41-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea41-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9ea41-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ea41-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9ea41-108">Compiling the Code</span></span>  
 <span data-ttu-id="9ea41-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9ea41-109">This example requires:</span></span>  
  
-   <span data-ttu-id="9ea41-110">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9ea41-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9ea41-111">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9ea41-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9ea41-112">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="9ea41-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9ea41-113">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9ea41-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9ea41-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="9ea41-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9ea41-115">При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="9ea41-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="9ea41-116">Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../../docs/standard/threading/managed-threading-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="9ea41-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea41-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9ea41-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="9ea41-118">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="9ea41-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="9ea41-119">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="9ea41-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
