---
title: "Создание и реализация интерфейсов (Visual Basic) | Документы Microsoft"
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: ef1ec16005bf0a7967d396054ae23c1023143c2a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="ae0a2-102">Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae0a2-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="ae0a2-103">Интерфейсы описывают характеристики свойств, методов и событий, но оставить детали реализации до структур или классов.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="ae0a2-104">В этом пошаговом руководстве показано, как объявления и реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae0a2-105">В этом пошаговом руководстве не предоставляет сведения о том, как создать пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="ae0a2-106">Определение интерфейса</span><span class="sxs-lookup"><span data-stu-id="ae0a2-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="ae0a2-107">Откройте новую [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проекта приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-107">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="ae0a2-108">Добавьте новый модуль в проект, нажав кнопку **добавить модуль** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="ae0a2-109">Назовите новый модуль `Module1.vb` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="ae0a2-110">Отображается код нового модуля.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="ae0a2-111">Определите интерфейс с именем `TestInterface` в `Module1` , введя `Interface TestInterface` между `Module` и `End Module` инструкций и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="ae0a2-112">**Редактор кода** отступы `Interface` ключевое слово и добавляет `End Interface` инструкции для формирования блока кода.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="ae0a2-113">Определение свойств, методов и событий интерфейса, размещая следующий код между `Interface` и `End Interface` инструкции:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     <span data-ttu-id="ae0a2-114">[!code-vb[VbVbalrOOP&#98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-114">[!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="ae0a2-115">Реализация</span><span class="sxs-lookup"><span data-stu-id="ae0a2-115">Implementation</span></span>  
 <span data-ttu-id="ae0a2-116">Вы можете заметить, что синтаксис, используемый для объявления членов интерфейса отличается от синтаксиса, используемого для объявления членов класса.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="ae0a2-117">Это отличие отражает тот факт, что интерфейсы не содержат кода реализации.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="ae0a2-118">Реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="ae0a2-118">To implement the interface</span></span>  
  
1.  <span data-ttu-id="ae0a2-119">Добавьте класс с именем `ImplementationClass` , добавив следующую инструкцию, чтобы `Module1`после того, как `End Interface` инструкции до `End Module` инструкции и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     <span data-ttu-id="ae0a2-120">[!code-vb[VbVbalrOOP&#99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-120">[!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-121">Если вы работаете в интегрированной среде разработки, **редактор кода** подставит соответствующий `End Class` инструкция, при нажатии клавиши ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-121">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="ae0a2-122">Добавьте следующие `Implements` инструкции `ImplementationClass`, который определяет реализуемый класс реализует:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-122">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     <span data-ttu-id="ae0a2-123">[!code-vb[VbVbalrOOP&#100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-123">[!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-124">Указанный отдельно от других элементов в верхней части класса или структуры, `Implements` оператор указывает, что класс или структура реализуют интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-124">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="ae0a2-125">Если вы работаете в интегрированной среде разработки, **редактор кода** реализует члены класса, необходимые `TestInterface` при нажатии клавиши ВВОД, и следующий шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-125">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="ae0a2-126">Если вы работаете не в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-126">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="ae0a2-127">Добавьте следующий код в `ImplementationClass` реализовать `Event1`, `Method1`, и `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-127">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     <span data-ttu-id="ae0a2-128">[!code-vb[VbVbalrOOP&#101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-128">[!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-129">`Implements` Инструкция имена интерфейсов и членов реализуемых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-129">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="ae0a2-130">Завершите определение `Prop1` путем добавления закрытое поле для класса, который хранится значение свойства:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-130">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     <span data-ttu-id="ae0a2-131">[!code-vb[VbVbalrOOP&#102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-131">[!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-132">Возвращает значение `pval` из свойства метод доступа get.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-132">Return the value of the `pval` from the property get accessor.</span></span>  
  
     <span data-ttu-id="ae0a2-133">[!code-vb[VbVbalrOOP&#103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-133">[!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-134">Задайте значение `pval` метода доступа set свойства.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-134">Set the value of `pval` in the property set accessor.</span></span>  
  
     <span data-ttu-id="ae0a2-135">[!code-vb[VbVbalrOOP&#104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-135">[!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span></span>  
  
5.  <span data-ttu-id="ae0a2-136">Завершите определение `Method1` , добавив следующий код.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-136">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     <span data-ttu-id="ae0a2-137">[!code-vb[VbVbalrOOP&#105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-137">[!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span></span>  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="ae0a2-138">Чтобы проверить реализацию интерфейса</span><span class="sxs-lookup"><span data-stu-id="ae0a2-138">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="ae0a2-139">Щелкните правой кнопкой мыши форму запуска проекта в **обозревателе решений**и нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-139">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="ae0a2-140">Редактор покажет класс формы запуска.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-140">The editor displays the class for your startup form.</span></span> <span data-ttu-id="ae0a2-141">По умолчанию форма запуска называется `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-141">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="ae0a2-142">Добавьте следующие `testInstance` на `Form1` класса:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-142">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     <span data-ttu-id="ae0a2-143">[!code-vb[VbVbalrOOP&#120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-143">[!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-144">Объявив `testInstance` как `WithEvents`, `Form1` класс может обрабатывать его события.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-144">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="ae0a2-145">Добавьте следующий обработчик событий к `Form1` класс для обработки событий, вызванных `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-145">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     <span data-ttu-id="ae0a2-146">[!code-vb[VbVbalrOOP&#106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-146">[!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span></span>  
  
4.  <span data-ttu-id="ae0a2-147">Добавить подпрограмму с именем `Test` для `Form1` класса, чтобы протестировать класс реализации:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-147">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     <span data-ttu-id="ae0a2-148">[!code-vb[VbVbalrOOP&#107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-148">[!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span></span>  
  
     <span data-ttu-id="ae0a2-149">`Test` Процедура создает экземпляр класса, который реализует `MyInterface`, присваивает этот экземпляр `testInstance` поля, задает свойство и запускает метод через интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-149">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="ae0a2-150">Добавьте код для вызова `Test` процедуру `Form1 Load` процедуры при запуске формы:</span><span class="sxs-lookup"><span data-stu-id="ae0a2-150">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     <span data-ttu-id="ae0a2-151">[!code-vb[VbVbalrOOP&#108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae0a2-151">[!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span></span>  
  
6.  <span data-ttu-id="ae0a2-152">Запустите `Test` процедура, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-152">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="ae0a2-153">Отображается сообщение «Prop1 было установлено значение 9».</span><span class="sxs-lookup"><span data-stu-id="ae0a2-153">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="ae0a2-154">После нажатия кнопки ОК, сообщение «X параметра для метода Method1 равно 5» отображается.</span><span class="sxs-lookup"><span data-stu-id="ae0a2-154">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="ae0a2-155">Нажмите кнопку ОК, и появится сообщение «обработчик события обнаружено событие».</span><span class="sxs-lookup"><span data-stu-id="ae0a2-155">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0a2-156">См. также</span><span class="sxs-lookup"><span data-stu-id="ae0a2-156">See Also</span></span>  
 <span data-ttu-id="ae0a2-157">[Оператор Implements](../../../../visual-basic/language-reference/statements/implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae0a2-157">[Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md) </span></span>  
<span data-ttu-id="ae0a2-158"> [Интерфейсы](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae0a2-158"> [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span></span>  
<span data-ttu-id="ae0a2-159"> [Оператор Interface](../../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae0a2-159"> [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="ae0a2-160"> [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md)</span><span class="sxs-lookup"><span data-stu-id="ae0a2-160"> [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)</span></span>

