---
title: Практическое руководство. Фоновое выполнение операции
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
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591610"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="77bb1-102">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="77bb1-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="77bb1-103">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="77bb1-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="77bb1-104">В примере ниже показано, как запустить операцию, занимающую длительное время, в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="77bb1-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="77bb1-105">В форме есть кнопки **Пуск** и **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="77bb1-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="77bb1-106">Кнопка **Пуск** служит для запуска асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="77bb1-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="77bb1-107">Кнопка **Отмена** служит для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="77bb1-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="77bb1-108">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="77bb1-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="77bb1-109">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="77bb1-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="77bb1-110">Также см. в разделе [Пошаговое руководство: Выполнение операции в фоновом режиме](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="77bb1-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77bb1-111">Пример</span><span class="sxs-lookup"><span data-stu-id="77bb1-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="77bb1-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="77bb1-112">Compiling the Code</span></span>  
 <span data-ttu-id="77bb1-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="77bb1-113">This example requires:</span></span>  
  
- <span data-ttu-id="77bb1-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="77bb1-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77bb1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="77bb1-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="77bb1-116">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="77bb1-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="77bb1-117">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="77bb1-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)
