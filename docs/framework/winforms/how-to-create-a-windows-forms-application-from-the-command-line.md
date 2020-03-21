---
title: Создание приложения Windows Forms из командной строки
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181987"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="14cd6-102">Как: Создать приложение Windows Forms из командной строки</span><span class="sxs-lookup"><span data-stu-id="14cd6-102">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="14cd6-103">В процедурах ниже описаны основные шаги, которые необходимо выполнить для создания и запуска приложения Windows Forms из командной строки.</span><span class="sxs-lookup"><span data-stu-id="14cd6-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="14cd6-104">Visual Studio предлагает расширенную поддержку этих процедур.</span><span class="sxs-lookup"><span data-stu-id="14cd6-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="14cd6-105">Также смотрите [Пошагово: Хостинг Управления формами Windows в WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="14cd6-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="14cd6-106">Процедура</span><span class="sxs-lookup"><span data-stu-id="14cd6-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="14cd6-107">Создание формы</span><span class="sxs-lookup"><span data-stu-id="14cd6-107">To create the form</span></span>  
  
1. <span data-ttu-id="14cd6-108">В пустом файле кода `Imports` `using` введите следующие или операторы:</span><span class="sxs-lookup"><span data-stu-id="14cd6-108">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="14cd6-109">Объявить класс, названный, `Form1` который наследует от класса формы:</span><span class="sxs-lookup"><span data-stu-id="14cd6-109">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="14cd6-110">Создайте безпаралисастого конструктора для. `Form1`</span><span class="sxs-lookup"><span data-stu-id="14cd6-110">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="14cd6-111">В следующий процедуре будет добавлен дополнительный код конструктора.</span><span class="sxs-lookup"><span data-stu-id="14cd6-111">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="14cd6-112">Добавьте в класс метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="14cd6-112">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="14cd6-113">Примените <xref:System.STAThreadAttribute> метод `Main` C,, чтобы указать, что ваше приложение Windows Forms является однопоточной квартирой.</span><span class="sxs-lookup"><span data-stu-id="14cd6-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="14cd6-114">(Атрибут не является необходимым в Visual Basic, так как Windows формирует приложения, разработанные с Visual Basic, используют однопонищенную модель апартаментов по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="14cd6-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="14cd6-115">Вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> для применения стилей операционной системы в приложении.</span><span class="sxs-lookup"><span data-stu-id="14cd6-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="14cd6-116">Создайте экземпляр формы и запустите его.</span><span class="sxs-lookup"><span data-stu-id="14cd6-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="14cd6-117">Компиляция и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="14cd6-117">To compile and run the application</span></span>  
  
1. <span data-ttu-id="14cd6-118">В командной строке .NET Framework перейдите к папке, в которой содержится класс `Form1`.</span><span class="sxs-lookup"><span data-stu-id="14cd6-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="14cd6-119">Скомпилируйте форму.</span><span class="sxs-lookup"><span data-stu-id="14cd6-119">Compile the form.</span></span>  
  
    - <span data-ttu-id="14cd6-120">Если вы используете C q, введите:`csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="14cd6-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="14cd6-121">Если вы используете Visual Basic, введите:`vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="14cd6-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="14cd6-122">В командной строке введите следующий текст: `Form1.exe`.</span><span class="sxs-lookup"><span data-stu-id="14cd6-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="14cd6-123">Добавление элемента управления и обработки события</span><span class="sxs-lookup"><span data-stu-id="14cd6-123">Adding a control and handling an event</span></span>

<span data-ttu-id="14cd6-124">В предыдущей процедуре продемонстрировано, как создать простейшую форму Windows Forms, скомпилировать и запустить ее.</span><span class="sxs-lookup"><span data-stu-id="14cd6-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="14cd6-125">В следующей процедуре будет показано, как создать и добавить в форму элемент управления и как обрабатывать событие для него.</span><span class="sxs-lookup"><span data-stu-id="14cd6-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="14cd6-126">Для получения дополнительной информации об элементах [Windows Forms Controls](./controls/index.md)управления, которые можно добавить в формы Windows, см.</span><span class="sxs-lookup"><span data-stu-id="14cd6-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="14cd6-127">Помимо понимания способов создания приложений Windows Forms, следует обладать общими знаниями о программировании на основе событий и способах обработки данных, введенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="14cd6-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="14cd6-128">Для получения дополнительной информации [Handling User Input](./controls/handling-user-input.md) см. [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="14cd6-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="14cd6-129">Объявление элемента управления типа "Кнопка" и обработка событий щелчка мышью для нее</span><span class="sxs-lookup"><span data-stu-id="14cd6-129">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="14cd6-130">Объявите элемент управления типа "Кнопка" с именем `button1`.</span><span class="sxs-lookup"><span data-stu-id="14cd6-130">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="14cd6-131">В конструкторе создайте кнопку и задайте ее свойства <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="14cd6-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="14cd6-132">Добавьте кнопку в форму.</span><span class="sxs-lookup"><span data-stu-id="14cd6-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="14cd6-133">Следующий пример кода показывает, как объявить управление кнопкой:</span><span class="sxs-lookup"><span data-stu-id="14cd6-133">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="14cd6-134">Создайте метод для обработки события <xref:System.Windows.Forms.Control.Click> для кнопки.</span><span class="sxs-lookup"><span data-stu-id="14cd6-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="14cd6-135">В обработчике событий щелчка мышью выведите элемент управления <xref:System.Windows.Forms.MessageBox> с сообщением "Здравствуй, мир".</span><span class="sxs-lookup"><span data-stu-id="14cd6-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="14cd6-136">Следующий пример кода демонстрирует, как обрабатывать событие нажатия кнопки:</span><span class="sxs-lookup"><span data-stu-id="14cd6-136">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="14cd6-137">Свяжите событие <xref:System.Windows.Forms.Control.Click> с созданным методом.</span><span class="sxs-lookup"><span data-stu-id="14cd6-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="14cd6-138">В примере кода ниже показано, как связать событие с методом.</span><span class="sxs-lookup"><span data-stu-id="14cd6-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="14cd6-139">Скомпилируйте и запустите приложение, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="14cd6-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14cd6-140">Пример</span><span class="sxs-lookup"><span data-stu-id="14cd6-140">Example</span></span>  

<span data-ttu-id="14cd6-141">Следующий пример кода является полным примером из предыдущих процедур:</span><span class="sxs-lookup"><span data-stu-id="14cd6-141">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="14cd6-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14cd6-142">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="14cd6-143">Изменение внешнего вида Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14cd6-143">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="14cd6-144">Усовершенствование приложений Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14cd6-144">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="14cd6-145">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14cd6-145">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
