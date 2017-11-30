---
title: "Создание и реализация интерфейсов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="bc13e-102">Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc13e-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="bc13e-103">Интерфейсы описывают характеристики свойств, методов и событий, но оставить сведения о реализации до структур или классов.</span><span class="sxs-lookup"><span data-stu-id="bc13e-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="bc13e-104">В этом пошаговом руководстве показано, как объявить и реализовать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc13e-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc13e-105">В этом пошаговом руководстве не предоставляет сведения о том, как создавать пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc13e-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="bc13e-106">Определение интерфейса</span><span class="sxs-lookup"><span data-stu-id="bc13e-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="bc13e-107">Откройте новый проект приложения Windows [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc13e-107">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="bc13e-108">Добавьте в проект новый модуль, щелкнув **добавить модуль** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="bc13e-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="bc13e-109">Назовите новый модуль `Module1.vb` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="bc13e-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="bc13e-110">Отображается код для нового модуля.</span><span class="sxs-lookup"><span data-stu-id="bc13e-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="bc13e-111">Определите интерфейс с именем `TestInterface` в `Module1` , введя `Interface TestInterface` между `Module` и `End Module` инструкции и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bc13e-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="bc13e-112">**Редактор кода** отступы `Interface` ключевое слово и добавляет `End Interface` инструкции для формирования блока кода.</span><span class="sxs-lookup"><span data-stu-id="bc13e-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="bc13e-113">Определение свойств, методов и событий интерфейса, установив следующий код между `Interface` и `End Interface` инструкции:</span><span class="sxs-lookup"><span data-stu-id="bc13e-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a><span data-ttu-id="bc13e-114">Реализация</span><span class="sxs-lookup"><span data-stu-id="bc13e-114">Implementation</span></span>  
 <span data-ttu-id="bc13e-115">Вы можете заметить, что синтаксис для объявления членов интерфейса отличается от синтаксиса, который используется для объявления членов класса.</span><span class="sxs-lookup"><span data-stu-id="bc13e-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="bc13e-116">Это различие отражает тот факт, что интерфейсы не могут содержать код реализации.</span><span class="sxs-lookup"><span data-stu-id="bc13e-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="bc13e-117">Реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="bc13e-117">To implement the interface</span></span>  
  
1.  <span data-ttu-id="bc13e-118">Добавьте класс с именем `ImplementationClass` , добавив следующую инструкцию, чтобы `Module1`после того, как `End Interface` инструкции перед вызовом `End Module` инструкции и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="bc13e-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     <span data-ttu-id="bc13e-119">При работе в интегрированной среде разработки, **редактор кода** подставит соответствующий `End Class` инструкция, при нажатии клавиши ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bc13e-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="bc13e-120">Добавьте следующие `Implements` инструкции `ImplementationClass`, который определяет реализуемый класс реализует:</span><span class="sxs-lookup"><span data-stu-id="bc13e-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     <span data-ttu-id="bc13e-121">Указанный отдельно от других элементов в верхней части класса или структуры, `Implements` инструкция указывает, что класс или структура реализуют интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc13e-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="bc13e-122">При работе в интегрированной среде разработки, **редактор кода** реализует члены класса, необходимые `TestInterface` при нажатии клавиши ВВОД, и следующий шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="bc13e-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="bc13e-123">Если вы работаете не в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="bc13e-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="bc13e-124">Добавьте следующий код в `ImplementationClass` реализовать `Event1`, `Method1`, и `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="bc13e-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     <span data-ttu-id="bc13e-125">`Implements` Инструкция имена интерфейсов и реализации члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc13e-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="bc13e-126">Завершите определение `Prop1` путем добавления закрытое поле для класса, который хранится значение свойства:</span><span class="sxs-lookup"><span data-stu-id="bc13e-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     <span data-ttu-id="bc13e-127">Возвращает значение `pval` из свойства метод доступа get.</span><span class="sxs-lookup"><span data-stu-id="bc13e-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     <span data-ttu-id="bc13e-128">Установите для параметра `pval` метод доступа set свойства.</span><span class="sxs-lookup"><span data-stu-id="bc13e-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  <span data-ttu-id="bc13e-129">Завершите определение `Method1` , добавив следующий код.</span><span class="sxs-lookup"><span data-stu-id="bc13e-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="bc13e-130">Чтобы проверить реализацию интерфейса</span><span class="sxs-lookup"><span data-stu-id="bc13e-130">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="bc13e-131">Щелкните правой кнопкой мыши форму запуска проекта в **обозревателе решений**и нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="bc13e-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="bc13e-132">Редактор отображает класс формы запуска.</span><span class="sxs-lookup"><span data-stu-id="bc13e-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="bc13e-133">По умолчанию форма запуска называется `Form1`.</span><span class="sxs-lookup"><span data-stu-id="bc13e-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="bc13e-134">Добавьте следующие `testInstance` на `Form1` класса:</span><span class="sxs-lookup"><span data-stu-id="bc13e-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     <span data-ttu-id="bc13e-135">Объявив `testInstance` как `WithEvents`, `Form1` класс может обрабатывать события.</span><span class="sxs-lookup"><span data-stu-id="bc13e-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="bc13e-136">Добавьте следующий обработчик событий `Form1` класса для обработки событий, вызванных `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="bc13e-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  <span data-ttu-id="bc13e-137">Добавить подпрограмму с именем `Test` для `Form1` класс, чтобы протестировать класс реализации:</span><span class="sxs-lookup"><span data-stu-id="bc13e-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     <span data-ttu-id="bc13e-138">`Test` Процедура используется для создания экземпляра класса, который реализует `MyInterface`, присваивает этот экземпляр `testInstance` поля, задает свойство и запускает метод через интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc13e-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="bc13e-139">Добавьте код для вызова `Test` процедуры из `Form1 Load` процедуры при запуске формы:</span><span class="sxs-lookup"><span data-stu-id="bc13e-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  <span data-ttu-id="bc13e-140">Запустите `Test` процедуры, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="bc13e-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="bc13e-141">Отображается сообщение «Prop1 было задано значение 9».</span><span class="sxs-lookup"><span data-stu-id="bc13e-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="bc13e-142">После нажатия кнопки ОК, сообщение «параметр для метода Method1 X равно 5» отображается.</span><span class="sxs-lookup"><span data-stu-id="bc13e-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="bc13e-143">Нажмите "ОК" и отображается сообщение «обработчик событий обнаружено событие».</span><span class="sxs-lookup"><span data-stu-id="bc13e-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc13e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="bc13e-144">See Also</span></span>  
 [<span data-ttu-id="bc13e-145">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="bc13e-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="bc13e-146">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="bc13e-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="bc13e-147">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="bc13e-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="bc13e-148">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="bc13e-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
