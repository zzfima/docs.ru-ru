---
title: "Как: Создание приложения Windows Forms из командной строки"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-winforms
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6ddb27f724e30071be339ac753cfd85599ccd86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="5008b-102">Как: Создание приложения Windows Forms из командной строки</span><span class="sxs-lookup"><span data-stu-id="5008b-102">How to: Create a Windows Forms application from the command line</span></span>
<span data-ttu-id="5008b-103">В процедурах ниже описаны основные шаги, которые необходимо выполнить для создания и запуска приложения Windows Forms из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5008b-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="5008b-104">Visual Studio предлагает расширенную поддержку этих процедур.</span><span class="sxs-lookup"><span data-stu-id="5008b-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="5008b-105">См. также [Пошаговое руководство: создание простой формы Windows Forms](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.100\)).</span><span class="sxs-lookup"><span data-stu-id="5008b-105">Also see [Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.100\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="5008b-106">Процедура</span><span class="sxs-lookup"><span data-stu-id="5008b-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="5008b-107">Создание формы</span><span class="sxs-lookup"><span data-stu-id="5008b-107">To create the form</span></span>  
  
1.  <span data-ttu-id="5008b-108">В пустом файле кода введите следующие операторы import или using:</span><span class="sxs-lookup"><span data-stu-id="5008b-108">In an empty code file, type the following import or using statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="5008b-109">Объявите класс с именем `Form1`, наследуемый от класса Form.</span><span class="sxs-lookup"><span data-stu-id="5008b-109">Declare a class named `Form1` that inherits from the Form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  <span data-ttu-id="5008b-110">Создайте конструктор по умолчанию для класса `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5008b-110">Create a default constructor for `Form1`.</span></span>  
  
     <span data-ttu-id="5008b-111">В следующий процедуре будет добавлен дополнительный код конструктора.</span><span class="sxs-lookup"><span data-stu-id="5008b-111">You will add more code to the constructor in a subsequent procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="5008b-112">Добавьте в класс метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="5008b-112">Add a `Main` method to the class.</span></span>  
  
    1.  <span data-ttu-id="5008b-113">Примените <xref:System.STAThreadAttribute> к методу `Main`, чтобы указать, что приложение Windows Forms использует однопотоковое подразделение.</span><span class="sxs-lookup"><span data-stu-id="5008b-113">Apply the <xref:System.STAThreadAttribute> to the `Main` method to specify your Windows Forms application is a single threaded apartment.</span></span>  
  
    2.  <span data-ttu-id="5008b-114">Вызовите <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> для придания приложению внешнего вида в стиле Windows XP.</span><span class="sxs-lookup"><span data-stu-id="5008b-114">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to give a Windows XP appearance to your application.</span></span>  
  
    3.  <span data-ttu-id="5008b-115">Создайте экземпляр формы и запустите его.</span><span class="sxs-lookup"><span data-stu-id="5008b-115">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="5008b-116">Компиляция и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="5008b-116">To compile and run the application</span></span>  
  
1.  <span data-ttu-id="5008b-117">В командной строке .NET Framework перейдите к папке, в которой содержится класс `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5008b-117">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2.  <span data-ttu-id="5008b-118">Скомпилируйте форму.</span><span class="sxs-lookup"><span data-stu-id="5008b-118">Compile the form.</span></span>  
  
    -   <span data-ttu-id="5008b-119">Если вы используете C#, введите:`csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="5008b-119">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    -   <span data-ttu-id="5008b-120">Если вы используете Visual Basic, введите:`vbc form1.vb /r:system.dll,system.drawing.dll,system.windows.forms.dll`</span><span class="sxs-lookup"><span data-stu-id="5008b-120">If you are using Visual Basic, type: `vbc form1.vb /r:system.dll,system.drawing.dll,system.windows.forms.dll`</span></span>  
  
3.  <span data-ttu-id="5008b-121">В командной строке введите следующую команду:`Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="5008b-121">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="5008b-122">Добавление элемента управления и обработка события</span><span class="sxs-lookup"><span data-stu-id="5008b-122">Adding a Control and Handling an Event</span></span>  
 <span data-ttu-id="5008b-123">В предыдущей процедуре продемонстрировано, как создать простейшую форму Windows Forms, скомпилировать и запустить ее.</span><span class="sxs-lookup"><span data-stu-id="5008b-123">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="5008b-124">В следующей процедуре будет показано, как создать и добавить в форму элемент управления и как обрабатывать событие для него.</span><span class="sxs-lookup"><span data-stu-id="5008b-124">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="5008b-125">Дополнительные сведения об элементах управления, можно добавить в форму Windows Forms см. в разделе [элементов управления Windows Forms](../../../docs/framework/winforms/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="5008b-125">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](../../../docs/framework/winforms/controls/index.md).</span></span>  
  
 <span data-ttu-id="5008b-126">Помимо понимания способов создания приложений Windows Forms, следует обладать общими знаниями о программировании на основе событий и способах обработки данных, введенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="5008b-126">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="5008b-127">Дополнительные сведения см. в разделе [Создание обработчиков событий в Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md), и [Обработка введенных пользователем данных](../../../docs/framework/winforms/controls/handling-user-input.md)</span><span class="sxs-lookup"><span data-stu-id="5008b-127">For more information, see [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md), and [Handling User Input](../../../docs/framework/winforms/controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="5008b-128">Объявление элемента управления типа "Кнопка" и обработка событий щелчка мышью для нее</span><span class="sxs-lookup"><span data-stu-id="5008b-128">To declare a button control and handle its click event</span></span>  
  
1.  <span data-ttu-id="5008b-129">Объявите элемент управления типа "Кнопка" с именем `button1`.</span><span class="sxs-lookup"><span data-stu-id="5008b-129">Declare a button control named `button1`.</span></span>  
  
2.  <span data-ttu-id="5008b-130">В конструкторе создайте кнопку и задайте ее свойства <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="5008b-130">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3.  <span data-ttu-id="5008b-131">Добавьте кнопку в форму.</span><span class="sxs-lookup"><span data-stu-id="5008b-131">Add the button to the form.</span></span>  
  
     <span data-ttu-id="5008b-132">В примере кода ниже показано, как объявить элемент управления типа "Кнопка".</span><span class="sxs-lookup"><span data-stu-id="5008b-132">The following code example demonstrates how to declare the button control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="5008b-133">Создайте метод для обработки события <xref:System.Windows.Forms.Control.Click> для кнопки.</span><span class="sxs-lookup"><span data-stu-id="5008b-133">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5.  <span data-ttu-id="5008b-134">В обработчике событий щелчка мышью выведите элемент управления <xref:System.Windows.Forms.MessageBox> с сообщением "Здравствуй, мир".</span><span class="sxs-lookup"><span data-stu-id="5008b-134">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="5008b-135">В примере кода ниже демонстрируется, как обрабатывать событие щелчка мышью для элемента управления типа "Кнопка".</span><span class="sxs-lookup"><span data-stu-id="5008b-135">The following code example demonstrates how to handle the button control's click event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  <span data-ttu-id="5008b-136">Свяжите событие <xref:System.Windows.Forms.Control.Click> с созданным методом.</span><span class="sxs-lookup"><span data-stu-id="5008b-136">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="5008b-137">В примере кода ниже показано, как связать событие с методом.</span><span class="sxs-lookup"><span data-stu-id="5008b-137">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  <span data-ttu-id="5008b-138">Скомпилируйте и запустите приложение, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="5008b-138">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5008b-139">Пример</span><span class="sxs-lookup"><span data-stu-id="5008b-139">Example</span></span>  
 <span data-ttu-id="5008b-140">В примере кода ниже полностью представлены все предыдущие процедуры.</span><span class="sxs-lookup"><span data-stu-id="5008b-140">Following code example is the complete example from the previous procedures.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5008b-141">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5008b-141">Compiling the Code</span></span>  
  
-   <span data-ttu-id="5008b-142">Для компиляции кода следуйте инструкциям из предыдущей процедуры, описывающим, как скомпилировать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="5008b-142">To compile the code, follow the instructions in the proceeding procedure that describe how to compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5008b-143">См. также</span><span class="sxs-lookup"><span data-stu-id="5008b-143">See Also</span></span>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Control>  
 [<span data-ttu-id="5008b-144">Изменение внешнего вида Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5008b-144">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 [<span data-ttu-id="5008b-145">Усовершенствование приложений Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5008b-145">Enhancing Windows Forms Applications</span></span>](../../../docs/framework/winforms/advanced/index.md)  
 [<span data-ttu-id="5008b-146">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5008b-146">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
