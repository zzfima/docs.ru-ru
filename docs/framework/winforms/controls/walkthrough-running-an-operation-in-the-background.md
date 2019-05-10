---
title: Пошаговое руководство. Фоновое выполнение операции
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
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: 6c705c6d6ff9bbd233bbddc3a73acf8aca13a547
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211515"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="0c8fe-102">Пошаговое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="0c8fe-102">Walkthrough: Running an Operation in the Background</span></span>

<span data-ttu-id="0c8fe-103">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>

<span data-ttu-id="0c8fe-104">Полный код, используемый в этом примере, см. в разделе [как: Фоновое выполнение операции](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="0c8fe-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>

## <a name="run-an-operation-in-the-background"></a><span data-ttu-id="0c8fe-105">Выполнение операции в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="0c8fe-105">Run an operation in the background</span></span>

1. <span data-ttu-id="0c8fe-106">Форма будет открыта в конструкторе Windows Forms в Visual Studio, перетащите два <xref:System.Windows.Forms.Button> управляет из **элементов** форму, а затем задайте `Name` и <xref:System.Windows.Forms.Control.Text%2A> свойства кнопок согласно следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-106">With your form active in the Windows Forms Designer in Visual Studio, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>

    |<span data-ttu-id="0c8fe-107">Кнопка</span><span class="sxs-lookup"><span data-stu-id="0c8fe-107">Button</span></span>|<span data-ttu-id="0c8fe-108">name</span><span class="sxs-lookup"><span data-stu-id="0c8fe-108">Name</span></span>|<span data-ttu-id="0c8fe-109">Текста</span><span class="sxs-lookup"><span data-stu-id="0c8fe-109">Text</span></span>|
    |------------|----------|----------|
    |`button1`|`startBtn`|<span data-ttu-id="0c8fe-110">**Запуск**</span><span class="sxs-lookup"><span data-stu-id="0c8fe-110">**Start**</span></span>|
    |`button2`|`cancelBtn`|<span data-ttu-id="0c8fe-111">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="0c8fe-111">**Cancel**</span></span>|

2. <span data-ttu-id="0c8fe-112">Откройте **элементов**, нажмите кнопку **компоненты** вкладке, а затем перетащите <xref:System.ComponentModel.BackgroundWorker> в форму компонент.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-112">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>

     <span data-ttu-id="0c8fe-113">`backgroundWorker1` Компонент появится в **область компонентов**.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-113">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>

3. <span data-ttu-id="0c8fe-114">В окне **Свойства** присвойте свойству <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-114">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>

4. <span data-ttu-id="0c8fe-115">В **свойства** щелкните **события** кнопку, а затем дважды щелкните <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> событий, чтобы создать обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-115">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>

5. <span data-ttu-id="0c8fe-116">Вставьте код требует много времени в <xref:System.ComponentModel.BackgroundWorker.DoWork> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-116">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>

6. <span data-ttu-id="0c8fe-117">Извлечение всех параметров, необходимые для операции из <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs> параметр.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-117">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>

7. <span data-ttu-id="0c8fe-118">Присвоить результат вычисления <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-118">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>

     <span data-ttu-id="0c8fe-119">Это будет предоставляться <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-119">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. <span data-ttu-id="0c8fe-120">Вставьте код для получения результата операции в <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-120">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. <span data-ttu-id="0c8fe-121">Выполните метод `TimeConsumingOperation`.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-121">Implement the `TimeConsumingOperation` method.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. <span data-ttu-id="0c8fe-122">В конструкторе Windows Forms дважды щелкните `startButton` для создания <xref:System.Windows.Forms.Control.Click> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-122">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

11. <span data-ttu-id="0c8fe-123">Вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `startButton`.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-123">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. <span data-ttu-id="0c8fe-124">В конструкторе Windows Forms дважды щелкните `cancelButton` для создания <xref:System.Windows.Forms.Control.Click> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-124">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

13. <span data-ttu-id="0c8fe-125">Вызовите <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> метод в <xref:System.Windows.Forms.Control.Click> обработчик событий для `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-125">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. <span data-ttu-id="0c8fe-126">В верхней части файла импортируйте пространства имен System.ComponentModel и System.Threading.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-126">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. <span data-ttu-id="0c8fe-127">Нажмите клавишу **F6** для построения решения, а затем нажмите клавишу **Ctrl**+**F5** для запуска приложения вне отладчика.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-127">Press **F6** to build the solution, and then press **Ctrl**+**F5** to run the application outside the debugger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c8fe-128">Если нажать клавишу **F5** для запуска приложения в отладчике, то исключение, возникающее в `TimeConsumingOperation` метод перехватывается и отображается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-128">If you press **F5** to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="0c8fe-129">При запуске приложения вне отладчика, <xref:System.ComponentModel.BackgroundWorker> обрабатывает исключение и кэширует его в <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> свойство <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-129">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>

16. <span data-ttu-id="0c8fe-130">Нажмите кнопку **запустить** для запуска асинхронной операции, а затем нажмите кнопку **отменить** кнопка для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-130">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>

     <span data-ttu-id="0c8fe-131">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-131">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c8fe-132">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="0c8fe-132">Next steps</span></span>

- <span data-ttu-id="0c8fe-133">Реализация формы, в которой отображается ход выполнения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-133">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="0c8fe-134">Дополнительные сведения см. в разделе [Как Реализация формы, в который выполняется фоновая операция](how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="0c8fe-134">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

- <span data-ttu-id="0c8fe-135">Реализуйте класс, поддерживающий асинхронную модель для компонентов.</span><span class="sxs-lookup"><span data-stu-id="0c8fe-135">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="0c8fe-136">Дополнительные сведения см. в разделе [реализации асинхронной модели на основе событий](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0c8fe-136">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c8fe-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0c8fe-137">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="0c8fe-138">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="0c8fe-138">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="0c8fe-139">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="0c8fe-139">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="0c8fe-140">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="0c8fe-140">BackgroundWorker Component</span></span>](backgroundworker-component.md)
