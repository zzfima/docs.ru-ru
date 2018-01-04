---
title: "Практическое руководство. Фоновое выполнение операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9a92427310dc36392b35f22e39c1d4ae101db74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="ca72d-102">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="ca72d-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="ca72d-103">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="ca72d-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="ca72d-104">В примере ниже показано, как запустить операцию, занимающую длительное время, в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="ca72d-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="ca72d-105">В форме есть кнопки **Пуск** и **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="ca72d-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="ca72d-106">Кнопка **Пуск** служит для запуска асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="ca72d-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="ca72d-107">Кнопка **Отмена** служит для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="ca72d-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="ca72d-108">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="ca72d-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="ca72d-109">В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] предусмотрена расширенная поддержка этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ca72d-109">There is extensive support for this task in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="ca72d-110">См. также раздел [Пошаговое руководство. Фоновое выполнение операции](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ca72d-110">Also see [Walkthrough: Running an Operation in the Background](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca72d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ca72d-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca72d-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ca72d-112">Compiling the Code</span></span>  
 <span data-ttu-id="ca72d-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ca72d-113">This example requires:</span></span>  
  
-   <span data-ttu-id="ca72d-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ca72d-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ca72d-115">Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ca72d-115">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ca72d-116">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="ca72d-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="ca72d-117">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ca72d-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca72d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ca72d-118">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="ca72d-119">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="ca72d-119">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="ca72d-120">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="ca72d-120">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
