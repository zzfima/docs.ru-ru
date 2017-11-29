---
title: "Пример. Фоновое выполнение операции"
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
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de485eb0b9c67ee9c3c897b6521971f50aaf751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="fc1b2-102">Пример. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="fc1b2-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="fc1b2-103">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="fc1b2-104">Полный код, используемый в этом примере, в разделе [как: выполнение операции в фоновом режиме](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="fc1b2-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc1b2-105">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fc1b2-106">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="fc1b2-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fc1b2-107">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fc1b2-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="fc1b2-108">Для запуска операции в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="fc1b2-108">To run an operation in the background</span></span>  
  
1.  <span data-ttu-id="fc1b2-109">Форма будет открыта в конструкторе Windows Forms, перетащите два <xref:System.Windows.Forms.Button> управляет из **элементов** форму, а затем присвойте `Name` и <xref:System.Windows.Forms.Control.Text%2A> свойства кнопок согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="fc1b2-110">Кнопка</span><span class="sxs-lookup"><span data-stu-id="fc1b2-110">Button</span></span>|<span data-ttu-id="fc1b2-111">Имя</span><span class="sxs-lookup"><span data-stu-id="fc1b2-111">Name</span></span>|<span data-ttu-id="fc1b2-112">Text</span><span class="sxs-lookup"><span data-stu-id="fc1b2-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="fc1b2-113">**Start**</span><span class="sxs-lookup"><span data-stu-id="fc1b2-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="fc1b2-114">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="fc1b2-114">**Cancel**</span></span>|  
  
2.  <span data-ttu-id="fc1b2-115">Откройте **элементов**, нажмите кнопку **компоненты** , а затем перетащите <xref:System.ComponentModel.BackgroundWorker> в форму компонент.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="fc1b2-116">`backgroundWorker1` Компонент появится в **область компонентов**.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3.  <span data-ttu-id="fc1b2-117">В **свойства** задайте <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4.  <span data-ttu-id="fc1b2-118">В **свойства** щелкните на **событий** кнопку, а затем дважды щелкните <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> событий для создания обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5.  <span data-ttu-id="fc1b2-119">Вставка кода требует много времени в <xref:System.ComponentModel.BackgroundWorker.DoWork> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6.  <span data-ttu-id="fc1b2-120">Параметры, необходимые для операции с <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs> параметр.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7.  <span data-ttu-id="fc1b2-121">Присвойте результат вычисления <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="fc1b2-122">Это будет доступен для <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  <span data-ttu-id="fc1b2-123">Вставьте код для получения результата операции в <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="fc1b2-124">Выполните метод `TimeConsumingOperation`.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="fc1b2-125">В конструкторе Windows Forms дважды щелкните `startButton` для создания <xref:System.Windows.Forms.Control.Click> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="fc1b2-126">Вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `startButton`.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="fc1b2-127">В конструкторе Windows Forms дважды щелкните `cancelButton` для создания <xref:System.Windows.Forms.Control.Click> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="fc1b2-128">Вызовите <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="fc1b2-129">В верхней части файла импортируйте пространства имен System.ComponentModel и System.Threading.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="fc1b2-130">Нажмите клавишу F6 для построения решения и нажмите клавиши CTRL-F5 для запуска приложения вне отладчика.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc1b2-131">Если нажать клавишу F5 для запуска приложения в отладчике, то исключение, возникающее в `TimeConsumingOperation` метод перехватывается и отображается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="fc1b2-132">При запуске приложения вне отладчика, <xref:System.ComponentModel.BackgroundWorker> обрабатывает исключение и кэширует его в <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> свойство <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1.  <span data-ttu-id="fc1b2-133">Нажмите кнопку **запустить** для запуска асинхронной операции, а затем нажмите **отменить** кнопку для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="fc1b2-134">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fc1b2-135">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fc1b2-135">Next Steps</span></span>  
  
-   <span data-ttu-id="fc1b2-136">Реализация формы, в которой отображается ход выполнения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="fc1b2-137">Дополнительные сведения см. в разделе [как: реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="fc1b2-137">For more information, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="fc1b2-138">Реализуйте класс, поддерживающий асинхронную модель для компонентов.</span><span class="sxs-lookup"><span data-stu-id="fc1b2-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="fc1b2-139">Дополнительные сведения см. в разделе [реализации асинхронной модели, основанной на событиях](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fc1b2-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1b2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="fc1b2-140">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="fc1b2-141">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="fc1b2-141">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="fc1b2-142">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="fc1b2-142">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="fc1b2-143">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="fc1b2-143">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
