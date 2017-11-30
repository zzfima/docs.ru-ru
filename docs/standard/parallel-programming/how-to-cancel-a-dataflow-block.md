---
title: "Практическое руководство. Отмена блока потока данных"
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
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="4269a-102">Практическое руководство. Отмена блока потока данных</span><span class="sxs-lookup"><span data-stu-id="4269a-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="4269a-103">В этом документе показано, как включить отмену в приложении.</span><span class="sxs-lookup"><span data-stu-id="4269a-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="4269a-104">В этом примере используется Windows Forms для отображения позиции активности рабочих элементов в конвейере потока данных, а также последствий отмены.</span><span class="sxs-lookup"><span data-stu-id="4269a-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4269a-105">Библиотека потоков данных TPL (пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4269a-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="4269a-106">Чтобы установить <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск в Интернете `Microsoft.Tpl.Dataflow` пакета.</span><span class="sxs-lookup"><span data-stu-id="4269a-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="4269a-107">Создание приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4269a-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="4269a-108">Создайте проект **Приложение Windows Forms** на C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4269a-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="4269a-109">На следующих этапах проекту дается название `CancellationWinForms`.</span><span class="sxs-lookup"><span data-stu-id="4269a-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="4269a-110">В конструкторе форм главной формы Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) добавьте элемент управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4269a-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="4269a-111">Добавьте элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4269a-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="4269a-112">Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойства <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> и <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства **Добавить рабочие элементы**.</span><span class="sxs-lookup"><span data-stu-id="4269a-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="4269a-113">Добавьте второй элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4269a-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="4269a-114">Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойства <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства **отменить**и <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> свойства `False`.</span><span class="sxs-lookup"><span data-stu-id="4269a-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="4269a-115">Добавьте четыре объекта <xref:System.Windows.Forms.ToolStripProgressBar> в элемент управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4269a-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="4269a-116">Создание конвейера потока данных</span><span class="sxs-lookup"><span data-stu-id="4269a-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="4269a-117">В этом разделе описано, как создать конвейер потока данных, который обрабатывает рабочие элементы и обновляет индикаторы выполнения.</span><span class="sxs-lookup"><span data-stu-id="4269a-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="4269a-118">Создание конвейера потока данных</span><span class="sxs-lookup"><span data-stu-id="4269a-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="4269a-119">В проекте добавьте ссылку на System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="4269a-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="4269a-120">Убедитесь, что Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) содержит следующие операторы `using` (`Imports` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4269a-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="4269a-121">Добавьте класс `WorkItem` как внутренний тип класса `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4269a-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="4269a-122">Добавьте в класс `Form1` следующие данные-члены.</span><span class="sxs-lookup"><span data-stu-id="4269a-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="4269a-123">Добавьте в класс `CreatePipeline` метод `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4269a-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="4269a-124">Поскольку блоки потоков данных `incrementProgress` и `decrementProgress` работают с интерфейсом пользователя, важно, чтобы эти действия происходили в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4269a-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="4269a-125">Для этого в процессе создания каждый из этих объектов предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, в котором свойству <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> задано значение <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4269a-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4269a-126">Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации.</span><span class="sxs-lookup"><span data-stu-id="4269a-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="4269a-127">Поскольку конструктор `Form1` вызывается из потока пользовательского интерфейса, действия для блоков потоков данных `incrementProgress` и `decrementProgress` также выполняются в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4269a-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="4269a-128">В этом примере задается свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> при создании частей конвейера.</span><span class="sxs-lookup"><span data-stu-id="4269a-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="4269a-129">Поскольку свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> полностью отменяет выполнение блока потока данных, весь конвейер должен быть заново создан после того, как пользователь отменит операцию и затем захочет добавить нескольких рабочих элементов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="4269a-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="4269a-130">Пример, демонстрирующий альтернативный способ отмены блока потока данных, чтобы другие работы могли выполняться после отмены операции, см. в разделе [Пошаговое руководство. Использование потока данных в приложении Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="4269a-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="4269a-131">Подключение конвейера потока данных к пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="4269a-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="4269a-132">В этом разделе описывается, как подключить конвейер потока данных к интерфейсу пользователя.</span><span class="sxs-lookup"><span data-stu-id="4269a-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="4269a-133">Как созданием конвейера, так и добавлением рабочих элементов в конвейере управляет обработчик событий для кнопки **Добавление рабочих элементов**.</span><span class="sxs-lookup"><span data-stu-id="4269a-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="4269a-134">Отмена инициируется кнопкой **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="4269a-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="4269a-135">Когда пользователь нажимает какую-либо из этих кнопок, соответствующее действие выполняется асинхронным образом.</span><span class="sxs-lookup"><span data-stu-id="4269a-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="4269a-136">Подключение конвейера потока данных к пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="4269a-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="4269a-137">В конструкторе форм главной формы создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событий для **Добавить рабочие элементы** кнопки.</span><span class="sxs-lookup"><span data-stu-id="4269a-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="4269a-138">Реализуйте <xref:System.Windows.Forms.ToolStripItem.Click> событий для **Добавить рабочие элементы** кнопки.</span><span class="sxs-lookup"><span data-stu-id="4269a-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="4269a-139">В конструкторе форм главной формы создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="4269a-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="4269a-140">Реализуйте <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="4269a-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="4269a-141">Пример</span><span class="sxs-lookup"><span data-stu-id="4269a-141">Example</span></span>  
 <span data-ttu-id="4269a-142">В следующем примере приведен полный код Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4269a-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="4269a-143">Ниже показано запущенное приложение.</span><span class="sxs-lookup"><span data-stu-id="4269a-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="4269a-144">![Приложение Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="4269a-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4269a-145">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4269a-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4269a-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4269a-146">See Also</span></span>  
 [<span data-ttu-id="4269a-147">Поток данных</span><span class="sxs-lookup"><span data-stu-id="4269a-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
