---
title: "Процедуры в Visual Basic"
ms.custom: 
ms.date: 2017-04-28
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, structured code
- Visual Basic code, procedures
- procedures, types of
- structured code, procedures
- procedures
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fd1a369ecfc1fa23cba694941fa47ab872ca1368
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="procedures-in-visual-basic"></a><span data-ttu-id="a09b6-102">Процедуры в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a09b6-102">Procedures in Visual Basic</span></span>
<span data-ttu-id="a09b6-103">*Процедура* — это блок операторов [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], заключенных между оператором объявления (`Function`, `Sub`, `Operator`, `Get`, `Set`) и соответствующим объявлением `End`.</span><span class="sxs-lookup"><span data-stu-id="a09b6-103">A *procedure* is a block of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements enclosed by a declaration statement (`Function`, `Sub`, `Operator`, `Get`, `Set`) and a matching `End` declaration.</span></span> <span data-ttu-id="a09b6-104">Каждый исполняемый оператор в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должен быть включен в какую-либо процедуру.</span><span class="sxs-lookup"><span data-stu-id="a09b6-104">All executable statements in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must be within some procedure.</span></span>  
  
## <a name="calling-a-procedure"></a><span data-ttu-id="a09b6-105">Вызов процедуры</span><span class="sxs-lookup"><span data-stu-id="a09b6-105">Calling a Procedure</span></span>  
 <span data-ttu-id="a09b6-106">Процедура вызывается из другого места в коде.</span><span class="sxs-lookup"><span data-stu-id="a09b6-106">You invoke a procedure from some other place in the code.</span></span> <span data-ttu-id="a09b6-107">Это называется *вызовом процедуры*.</span><span class="sxs-lookup"><span data-stu-id="a09b6-107">This is known as a *procedure call*.</span></span> <span data-ttu-id="a09b6-108">После завершения процедуры она возвращает управление в код, из которого она была вызвана (*вызывающий код*).</span><span class="sxs-lookup"><span data-stu-id="a09b6-108">When the procedure is finished running, it returns control to the code that invoked it, which is known as the *calling code*.</span></span> <span data-ttu-id="a09b6-109">Вызывающий код — это оператор или выражение в составе оператора, в которых указывается имя процедуры и передается управление процедуре.</span><span class="sxs-lookup"><span data-stu-id="a09b6-109">The calling code is a statement, or an expression within a statement, that specifies the procedure by name and transfers control to it.</span></span>  
  
## <a name="returning-from-a-procedure"></a><span data-ttu-id="a09b6-110">Возврат из процедуры</span><span class="sxs-lookup"><span data-stu-id="a09b6-110">Returning from a Procedure</span></span>  
 <span data-ttu-id="a09b6-111">После завершения процедуры она возвращает управление вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="a09b6-111">A procedure returns control to the calling code when it has finished running.</span></span> <span data-ttu-id="a09b6-112">Чтобы сделать это, можно использовать [оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md), соответствующий [оператор Exit](../../../../visual-basic/language-reference/statements/exit-statement.md) для процедуры или [ключевое слово >\< оператора ](../../../../visual-basic/language-reference/statements/end-keyword-statement.md)End.</span><span class="sxs-lookup"><span data-stu-id="a09b6-112">To do this, it can use a [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), the appropriate [Exit Statement](../../../../visual-basic/language-reference/statements/exit-statement.md) statement for the procedure, or the procedure's [End \<keyword> Statement](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) statement.</span></span> <span data-ttu-id="a09b6-113">Затем управление передается в вызывающий код, следующий за точкой вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="a09b6-113">Control then passes to the calling code following the point of the procedure call.</span></span>  
  
-   <span data-ttu-id="a09b6-114">При использовании оператора `Return` управление немедленно возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a09b6-114">With a `Return` statement, control returns immediately to the calling code.</span></span> <span data-ttu-id="a09b6-115">Операторы, следующие за оператором `Return`, не выполняются.</span><span class="sxs-lookup"><span data-stu-id="a09b6-115">Statements following the `Return` statement do not run.</span></span> <span data-ttu-id="a09b6-116">В одной и той же процедуре можно использовать несколько операторов `Return`.</span><span class="sxs-lookup"><span data-stu-id="a09b6-116">You can have more than one `Return` statement in the same procedure.</span></span>  
  
-   <span data-ttu-id="a09b6-117">При использовании операторов `Exit Sub` или `Exit Function` управление немедленно возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a09b6-117">With an `Exit Sub` or `Exit Function` statement, control returns immediately to the calling code.</span></span> <span data-ttu-id="a09b6-118">Операторы, следующие за оператором `Exit`, не выполняются.</span><span class="sxs-lookup"><span data-stu-id="a09b6-118">Statements following the `Exit` statement do not run.</span></span> <span data-ttu-id="a09b6-119">В одной и той же процедуре можно использовать несколько операторов `Exit` и одновременно использовать операторы `Return` и `Exit`.</span><span class="sxs-lookup"><span data-stu-id="a09b6-119">You can have more than one `Exit` statement in the same procedure, and you can mix `Return` and `Exit` statements in the same procedure.</span></span>  
  
-   <span data-ttu-id="a09b6-120">Если процедура не содержит операторов `Return` или `Exit`, она завершается оператором `End Sub`, `End Function`, `End Get` или `End Set`, который следует за последним оператором в составе процедуры.</span><span class="sxs-lookup"><span data-stu-id="a09b6-120">If a procedure has no `Return` or `Exit` statements, it concludes with an `End Sub` or `End Function`, `End Get`, or `End Set` statement following the last statement of the procedure body.</span></span> <span data-ttu-id="a09b6-121">При использовании оператора `End` управление немедленно возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a09b6-121">The `End` statement returns control immediately to the calling code.</span></span> <span data-ttu-id="a09b6-122">В процедуре можно использовать только один оператор `End`.</span><span class="sxs-lookup"><span data-stu-id="a09b6-122">You can have only one `End` statement in a procedure.</span></span>  
  
## <a name="parameters-and-arguments"></a><span data-ttu-id="a09b6-123">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="a09b6-123">Parameters and Arguments</span></span>  
 <span data-ttu-id="a09b6-124">В большинстве случаев процедура должна работать с разными данными при каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="a09b6-124">In most cases, a procedure needs to operate on different data each time you call it.</span></span> <span data-ttu-id="a09b6-125">Эти данные можно передать в процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="a09b6-125">You can pass this information to the procedure as part of the procedure call.</span></span> <span data-ttu-id="a09b6-126">В процедуре можно определить *параметры* (ноль или более), каждый из которых представляет одно из передаваемых значений.</span><span class="sxs-lookup"><span data-stu-id="a09b6-126">The procedure defines zero or more *parameters*, each of which represents a value it expects you to pass to it.</span></span> <span data-ttu-id="a09b6-127">Каждому параметру в определении процедуры соответствует *аргумент* при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="a09b6-127">Corresponding to each parameter in the procedure definition is an *argument* in the procedure call.</span></span> <span data-ttu-id="a09b6-128">Аргумент представляет значение, которое передается в соответствующий параметр для заданного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="a09b6-128">An argument represents the value you pass to the corresponding parameter in a given procedure call.</span></span>  
  
## <a name="types-of-procedures"></a><span data-ttu-id="a09b6-129">Типы процедур</span><span class="sxs-lookup"><span data-stu-id="a09b6-129">Types of Procedures</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="a09b6-130"> использует несколько типов процедур.</span><span class="sxs-lookup"><span data-stu-id="a09b6-130"> uses several types of procedures:</span></span>  
  
-   <span data-ttu-id="a09b6-131">[Подпрограммы](./sub-procedures.md) выполняют действия, но не возвращают значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a09b6-131">[Sub Procedures](./sub-procedures.md) perform actions but do not return a value to the calling code.</span></span>  
  
-   <span data-ttu-id="a09b6-132">Процедуры обработки событий — это процедуры `Sub`, которые выполняются в ответ на событие, вызванное действием пользователя или наступлением определенных условий в программе.</span><span class="sxs-lookup"><span data-stu-id="a09b6-132">Event-handling procedures are `Sub` procedures that execute in response to an event raised by user action or by an occurrence in a program.</span></span>  
  
-   <span data-ttu-id="a09b6-133">[Функции](./function-procedures.md) возвращают значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a09b6-133">[Function Procedures](./function-procedures.md) return a value to the calling code.</span></span> <span data-ttu-id="a09b6-134">Они могут выполнять другие действия перед возвратом.</span><span class="sxs-lookup"><span data-stu-id="a09b6-134">They can perform other actions before returning.</span></span>

    <span data-ttu-id="a09b6-135">Некоторые функции, написанные на C#, возвращают *значение по ссылке*.</span><span class="sxs-lookup"><span data-stu-id="a09b6-135">Some functions written in C# return a *reference return value*.</span></span> <span data-ttu-id="a09b6-136">Вызывающие функции могут изменять возвращаемое значение, и это изменение отражается в состоянии вызываемого объекта.</span><span class="sxs-lookup"><span data-stu-id="a09b6-136">Function callers can modify the return value, and this modification is reflected in the state of the called object.</span></span> <span data-ttu-id="a09b6-137">Начиная с Visual Basic 2017, в коде можно использовать значения, возвращаемые по ссылке, но нельзя возвращать значения по ссылке.</span><span class="sxs-lookup"><span data-stu-id="a09b6-137">Starting with Visual Basic 2017, Visual Basic code can consume reference return values, although it cannot return a value by reference.</span></span> <span data-ttu-id="a09b6-138">Дополнительные сведения см. в разделе [Значения, возвращаемые по ссылке](ref-return-values.md).</span><span class="sxs-lookup"><span data-stu-id="a09b6-138">For more information, see [Reference return values](ref-return-values.md).</span></span>
  
-   <span data-ttu-id="a09b6-139">[Процедуры свойств](./property-procedures.md) возвращают и задают значения свойств для объектов или модулей.</span><span class="sxs-lookup"><span data-stu-id="a09b6-139">[Property Procedures](./property-procedures.md) return and assign values of properties on objects or modules.</span></span>  
  
-   <span data-ttu-id="a09b6-140">[Процедуры операторов](./operator-procedures.md) определяют поведение стандартного оператора, если один или оба операнда представляют собой недавно определенный класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="a09b6-140">[Operator Procedures](./operator-procedures.md) define the behavior of a standard operator when one or both of the operands is a newly-defined class or structure.</span></span>  
  
-   <span data-ttu-id="a09b6-141">В [универсальных процедурах в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) определяются *параметры типа* в дополнение к обычным параметрам процедуры. Это позволяет передавать параметры определенного типа из вызывающего кода при каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="a09b6-141">[Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) define one or more *type parameters* in addition to their normal parameters, so the calling code can pass specific data types each time it makes a call.</span></span>  
  
## <a name="procedures-and-structured-code"></a><span data-ttu-id="a09b6-142">Процедуры и структурированный код</span><span class="sxs-lookup"><span data-stu-id="a09b6-142">Procedures and Structured Code</span></span>  
 <span data-ttu-id="a09b6-143">Каждая строка исполняемого кода в приложении должна находиться внутри некоторой процедуры, такой как `Main`, `calculate` или `Button1_Click`.</span><span class="sxs-lookup"><span data-stu-id="a09b6-143">Every line of executable code in your application must be inside some procedure, such as `Main`, `calculate`, or `Button1_Click`.</span></span> <span data-ttu-id="a09b6-144">Если разделить большие процедуры на более мелкие, код будет более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="a09b6-144">If you subdivide large procedures into smaller ones, your application is more readable.</span></span>  
  
 <span data-ttu-id="a09b6-145">Процедуры можно использовать для реализации повторяющихся или общих задач, таких как часто используемые вычисления, операции с текстом и элементами управления и операции с базами данных.</span><span class="sxs-lookup"><span data-stu-id="a09b6-145">Procedures are useful for performing repeated or shared tasks, such as frequently used calculations, text and control manipulation, and database operations.</span></span> <span data-ttu-id="a09b6-146">Процедуры можно вызывать из различных мест в коде; таким образом, их можно использовать в качестве стандартных блоков для создания приложения.</span><span class="sxs-lookup"><span data-stu-id="a09b6-146">You can call a procedure from many different places in your code, so you can use procedures as building blocks for your application.</span></span>  
  
 <span data-ttu-id="a09b6-147">Структурирование кода с помощью процедур предоставляет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="a09b6-147">Structuring your code with procedures gives you the following benefits:</span></span>  
  
-   <span data-ttu-id="a09b6-148">Процедуры позволяют разбить программу на отдельные логические блоки.</span><span class="sxs-lookup"><span data-stu-id="a09b6-148">Procedures allow you to break your programs into discrete logical units.</span></span> <span data-ttu-id="a09b6-149">Отлаживать такие отдельные блоки легче, чем всю программу целиком.</span><span class="sxs-lookup"><span data-stu-id="a09b6-149">You can debug separate units more easily than you can debug an entire program without procedures.</span></span>  
  
-   <span data-ttu-id="a09b6-150">После разработки процедур для использования в одной программе их можно использовать в других программах без изменений или с небольшими изменениями.</span><span class="sxs-lookup"><span data-stu-id="a09b6-150">After you develop procedures for use in one program, you can use them in other programs, often with little or no modification.</span></span> <span data-ttu-id="a09b6-151">Это помогает избежать дублирования кода.</span><span class="sxs-lookup"><span data-stu-id="a09b6-151">This helps you avoid code duplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09b6-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a09b6-152">See Also</span></span>  
 <span data-ttu-id="a09b6-153">[Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-153">[How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
 <span data-ttu-id="a09b6-154">[Подпрограммы](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-154">[Sub Procedures](./sub-procedures.md) </span></span>  
 <span data-ttu-id="a09b6-155">[Функции](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-155">[Function Procedures](./function-procedures.md) </span></span>  
 <span data-ttu-id="a09b6-156">[Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-156">[Property Procedures](./property-procedures.md) </span></span>  
 <span data-ttu-id="a09b6-157">[Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-157">[Operator Procedures](./operator-procedures.md) </span></span>  
 <span data-ttu-id="a09b6-158">[Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-158">[Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
 <span data-ttu-id="a09b6-159">[Рекурсивные процедуры](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-159">[Recursive Procedures](./recursive-procedures.md) </span></span>  
 <span data-ttu-id="a09b6-160">[Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-160">[Procedure Overloading](./procedure-overloading.md) </span></span>  
 <span data-ttu-id="a09b6-161">[Универсальные процедуры в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a09b6-161">[Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) </span></span>  
 [<span data-ttu-id="a09b6-162">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="a09b6-162">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

