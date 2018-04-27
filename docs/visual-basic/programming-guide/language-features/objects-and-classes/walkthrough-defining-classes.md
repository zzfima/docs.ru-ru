---
title: Определение классов (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="56398-102">Пошаговое руководство. Определение классов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56398-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="56398-103">В этом пошаговом руководстве показано, как определить классы, которые затем можно использовать для создания объектов.</span><span class="sxs-lookup"><span data-stu-id="56398-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="56398-104">Также показано, как добавлять свойства и методы в новый класс и показано, как инициализировать объект.</span><span class="sxs-lookup"><span data-stu-id="56398-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="56398-105">Определение класса</span><span class="sxs-lookup"><span data-stu-id="56398-105">To define a class</span></span>
  
1.  <span data-ttu-id="56398-106">Создайте проект, щелкнув **новый проект** на **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="56398-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="56398-107">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="56398-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="56398-108">Выберите приложение Windows из списка шаблонов проектов Visual Basic для отображения нового проекта.</span><span class="sxs-lookup"><span data-stu-id="56398-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="56398-109">Добавьте новый класс в проект, щелкнув **добавить класс** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="56398-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="56398-110">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="56398-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="56398-111">Выберите **класса** шаблона.</span><span class="sxs-lookup"><span data-stu-id="56398-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="56398-112">Имя для нового класса `UserNameInfo.vb`, а затем нажмите кнопку **добавить** для отображения в код для нового класса.</span><span class="sxs-lookup"><span data-stu-id="56398-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  <span data-ttu-id="56398-113">В Visual Basic можно использовать **редактор кода** Чтобы добавить класс в форму запуска, введя `Class` ключевое слово, за которым следует имя нового класса.</span><span class="sxs-lookup"><span data-stu-id="56398-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="56398-114">**Редактор кода** предоставляет соответствующий `End Class` инструкции для вас.</span><span class="sxs-lookup"><span data-stu-id="56398-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="56398-115">Определите закрытое поле для класса, добавив следующий код между `Class` и `End Class` инструкции:</span><span class="sxs-lookup"><span data-stu-id="56398-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="56398-116">Объявление полей как `Private` означает, он может использоваться только внутри класса.</span><span class="sxs-lookup"><span data-stu-id="56398-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="56398-117">Можно сделать поля доступными извне класса с помощью модификаторов доступа, таких как `Public` , обеспечивающие более высокий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="56398-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="56398-118">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="56398-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="56398-119">Определите свойства для класса, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="56398-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  <span data-ttu-id="56398-120">Определите метод для класса, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="56398-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="56398-121">Определите параметризованный конструктор для нового класса, добавив процедуру с именем `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="56398-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="56398-122">`Sub New` Конструктор вызывается автоматически при создании объекта на основе данного класса.</span><span class="sxs-lookup"><span data-stu-id="56398-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="56398-123">Этот конструктор задает значение поля, которое содержит имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="56398-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="56398-124">Создание кнопки для тестирования класса</span><span class="sxs-lookup"><span data-stu-id="56398-124">To create a button to test the class</span></span>
  
1.  <span data-ttu-id="56398-125">Изменить форму запуска в режим конструктора, щелкните правой кнопкой мыши его имя в **обозревателе решений** и выбрав **конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="56398-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="56398-126">По умолчанию форма запуска для проектов приложений Windows с именем Form1.vb.</span><span class="sxs-lookup"><span data-stu-id="56398-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="56398-127">Затем появится главная форма.</span><span class="sxs-lookup"><span data-stu-id="56398-127">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="56398-128">Добавьте в главную форму кнопку и дважды щелкните его, чтобы открыть код `Button1_Click` обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="56398-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="56398-129">Добавьте следующий код, чтобы вызвать процедуру тестирования:</span><span class="sxs-lookup"><span data-stu-id="56398-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="56398-130">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="56398-130">To run your application</span></span>
  
1.  <span data-ttu-id="56398-131">Запустите приложение, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="56398-131">Run your application by pressing F5.</span></span> <span data-ttu-id="56398-132">Нажмите кнопку на форме, чтобы вызвать процедуру тестирования.</span><span class="sxs-lookup"><span data-stu-id="56398-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="56398-133">Будет выведено сообщение о том, что исходный `UserName` — «MOORE, BOBBY», поскольку процедурой вызван `Capitalize` метод объекта.</span><span class="sxs-lookup"><span data-stu-id="56398-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="56398-134">Нажмите кнопку **ОК** , чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="56398-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="56398-135">`Button1 Click` Процедура изменяет значение `UserName` свойства и отображает сообщение о том, что новое значение `UserName` «Worden, Joe».</span><span class="sxs-lookup"><span data-stu-id="56398-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56398-136">См. также</span><span class="sxs-lookup"><span data-stu-id="56398-136">See also</span></span>

<span data-ttu-id="56398-137">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56398-137">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md)</span></span>  
[<span data-ttu-id="56398-138">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="56398-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)