---
title: "Определение классов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5b470b8ba9b60dfb1cd1bbb207e02217f5311c27
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="2f5f3-102">Пошаговое руководство. Определение классов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f5f3-102">Walkthrough: Defining Classes (Visual Basic)</span></span>
<span data-ttu-id="2f5f3-103">В этом пошаговом руководстве показано, как определять классы, которые затем можно использовать для создания объектов.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="2f5f3-104">Также показано, как добавить свойства и методы в новый класс и показано, как инициализировать объект.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a><span data-ttu-id="2f5f3-105">Определение класса</span><span class="sxs-lookup"><span data-stu-id="2f5f3-105">To define a class</span></span>  
  
1.  <span data-ttu-id="2f5f3-106">Создайте проект, нажав кнопку **новый проект** на **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="2f5f3-107">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="2f5f3-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2f5f3-108">Выберите приложение Windows из списка [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проект шаблоны для отображения нового проекта.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-108">Select Windows Application from the list of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="2f5f3-109">Добавьте новый класс в проект, нажав кнопку **добавить класс** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="2f5f3-110">**Add New Item** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="2f5f3-111">Выберите **класса** шаблона.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="2f5f3-112">Назовите новый класс `UserNameInfo.vb`, а затем нажмите кнопку **добавить** чтобы отобразить код для нового класса.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     <span data-ttu-id="2f5f3-113">[!code-vb[VbVbalrOOP&#5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-113">[!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f5f3-114">Можно использовать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **редактор кода** Чтобы добавить класс в форму запуска, введя `Class` ключевое слово, за которым следует имя нового класса.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-114">You can use the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="2f5f3-115">**Редактор кода** предоставляет соответствующий `End Class` инструкции для вас.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="2f5f3-116">Определите закрытое поле для класса, добавив следующий код между `Class` и `End Class` инструкции:</span><span class="sxs-lookup"><span data-stu-id="2f5f3-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     <span data-ttu-id="2f5f3-117">[!code-vb[VbVbalrOOP&#7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-117">[!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span></span>  
  
     <span data-ttu-id="2f5f3-118">Объявление полей как `Private` означает могут использоваться только внутри класса.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-118">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="2f5f3-119">Можно сделать поля доступными извне класса с помощью модификаторов доступа, такие как `Public` , обеспечивают дополнительный доступ.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-119">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="2f5f3-120">Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2f5f3-120">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="2f5f3-121">Определите свойство класса, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="2f5f3-121">Define a property for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="2f5f3-122">[!code-vb[VbVbalrOOP №&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-122">[!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span></span>  
  
8.  <span data-ttu-id="2f5f3-123">Определите метод для класса, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="2f5f3-123">Define a method for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="2f5f3-124">[!code-vb[VbVbalrOOP №&9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-124">[!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span></span>  
  
9. <span data-ttu-id="2f5f3-125">Определите параметризованный конструктор для нового класса, добавив процедуру с именем `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="2f5f3-125">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     <span data-ttu-id="2f5f3-126">[!code-vb[VbVbalrOOP&#10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-126">[!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span></span>  
  
     <span data-ttu-id="2f5f3-127">`Sub New` Конструктор вызывается автоматически при создании объекта на основе данного класса.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-127">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="2f5f3-128">Этот конструктор задает значение поля, которое содержит имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-128">This constructor sets the value of the field that holds the user name.</span></span>  
  
### <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="2f5f3-129">Создание кнопки для тестирования класса</span><span class="sxs-lookup"><span data-stu-id="2f5f3-129">To create a button to test the class</span></span>  
  
1.  <span data-ttu-id="2f5f3-130">Переключите форму запуска в режим конструктора, щелкнув правой кнопкой мыши его имя в **обозревателе решений** и выбрав **конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-130">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="2f5f3-131">По умолчанию форма запуска для проектов приложений Windows называется Form1.vb.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-131">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="2f5f3-132">Затем появится главная форма.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-132">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="2f5f3-133">Добавьте в главную форму кнопку и дважды щелкните его, чтобы отобразить код для `Button1_Click` обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-133">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="2f5f3-134">Добавьте следующий код, чтобы вызвать процедуру тестирования:</span><span class="sxs-lookup"><span data-stu-id="2f5f3-134">Add the following code to call the test procedure:</span></span>  
  
     <span data-ttu-id="2f5f3-135">[!code-vb[VbVbalrOOP&#12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f5f3-135">[!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span></span>  
  
### <a name="to-run-your-application"></a><span data-ttu-id="2f5f3-136">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="2f5f3-136">To run your application</span></span>  
  
1.  <span data-ttu-id="2f5f3-137">Запустите приложение, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-137">Run your application by pressing F5.</span></span> <span data-ttu-id="2f5f3-138">Нажмите кнопку на форме, чтобы вызвать процедуру тестирования.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-138">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="2f5f3-139">Будет выведено сообщение о том, что исходный `UserName` — «MOORE, BOBBY», поскольку процедурой вызван `Capitalize` метода объекта.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-139">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="2f5f3-140">Щелкните **ОК** чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="2f5f3-140">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="2f5f3-141">`Button1 Click` Процедура изменяет значение `UserName` свойства и отображает сообщение о том, что новое значение `UserName` «Worden, Joe».</span><span class="sxs-lookup"><span data-stu-id="2f5f3-141">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5f3-142">См. также</span><span class="sxs-lookup"><span data-stu-id="2f5f3-142">See Also</span></span>  
 <span data-ttu-id="2f5f3-143">[Объектно ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span><span class="sxs-lookup"><span data-stu-id="2f5f3-143">[Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span></span>  
<span data-ttu-id="2f5f3-144"> [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="2f5f3-144"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>

