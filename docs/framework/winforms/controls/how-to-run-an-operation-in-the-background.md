---
title: Практическое руководство. Выполнение операции в фоновом режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 83be9440eb566740566025c659c0a4909e634b73
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711178"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="1d06d-102">Практическое руководство. Выполнение операции в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="1d06d-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="1d06d-103">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="1d06d-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="1d06d-104">В примере ниже показано, как запустить операцию, занимающую длительное время, в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="1d06d-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="1d06d-105">В форме есть кнопки **Пуск** и **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="1d06d-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="1d06d-106">Кнопка **Пуск** служит для запуска асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1d06d-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="1d06d-107">Кнопка **Отмена** служит для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1d06d-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="1d06d-108">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="1d06d-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="1d06d-109">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="1d06d-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="1d06d-110">Также см. в разделе [Пошаговое руководство: Выполнение операции в фоновом режиме](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="1d06d-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d06d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1d06d-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d06d-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1d06d-112">Compiling the Code</span></span>  
 <span data-ttu-id="1d06d-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1d06d-113">This example requires:</span></span>  
  
-   <span data-ttu-id="1d06d-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1d06d-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1d06d-115">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1d06d-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1d06d-116">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="1d06d-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d06d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1d06d-117">See also</span></span>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="1d06d-118">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="1d06d-118">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="1d06d-119">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="1d06d-119">BackgroundWorker Component</span></span>](backgroundworker-component.md)
