---
title: "Специальные символы в коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
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
ms.openlocfilehash: cd7fbce5c382c3acd88a12277a3d7899b823d049
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="626c4-102">Специальные символы в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="626c4-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="626c4-103">Иногда необходимо использовать специальные символы в коде, то есть символы, которые не являются буквой или цифрой.</span><span class="sxs-lookup"><span data-stu-id="626c4-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="626c4-104">Знаки пунктуации и специальные символы в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] набор символов имеет различное применение, от организации текста программы, до определения задач, выполняемых компилятором или скомпилированной программой.</span><span class="sxs-lookup"><span data-stu-id="626c4-104">The punctuation and special characters in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="626c4-105">Эти знаки не определяют операции, подлежащие выполнению.</span><span class="sxs-lookup"><span data-stu-id="626c4-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="626c4-106">Круглые скобки</span><span class="sxs-lookup"><span data-stu-id="626c4-106">Parentheses</span></span>  
 <span data-ttu-id="626c4-107">Используйте круглые скобки при определении процедуры, такие как `Sub` или `Function`.</span><span class="sxs-lookup"><span data-stu-id="626c4-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="626c4-108">Все списки аргументов процедуры необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="626c4-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="626c4-109">Вы также использовать круглые скобки для распределения переменных или аргументов на логические группы, особенно для того, чтобы переопределить порядок приоритета операторов в сложном выражении.</span><span class="sxs-lookup"><span data-stu-id="626c4-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="626c4-110">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="626c4-110">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="626c4-111">[!code-vb[VbVbcnConventions&11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c4-111">[!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="626c4-112">После выполнения предыдущего кода значение `d` равняется 8,225, а значение `e` равно 3.</span><span class="sxs-lookup"><span data-stu-id="626c4-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="626c4-113">Расчет `d` использует приоритет по умолчанию `/` над `+` и эквивалентен `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="626c4-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="626c4-114">Круглые скобки в вычислении `e` наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="626c4-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="626c4-115">Разделители</span><span class="sxs-lookup"><span data-stu-id="626c4-115">Separators</span></span>  
 <span data-ttu-id="626c4-116">Разделители выполняют предполагает их название: они разделяют сегменты кода.</span><span class="sxs-lookup"><span data-stu-id="626c4-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="626c4-117">В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], разделителя используется двоеточие (`:`).</span><span class="sxs-lookup"><span data-stu-id="626c4-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="626c4-118">Разделители используются в том случае, если требуется использовать несколько операторов в одной строке, а не в отдельных строках.</span><span class="sxs-lookup"><span data-stu-id="626c4-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="626c4-119">Это экономит место и повышает удобочитаемость кода.</span><span class="sxs-lookup"><span data-stu-id="626c4-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="626c4-120">В следующем примере показано три оператора, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="626c4-120">The following example shows three statements separated by colons.</span></span>  
  
 <span data-ttu-id="626c4-121">[!code-vb[VbVbcnConventions&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c4-121">[!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span></span>  
  
 <span data-ttu-id="626c4-122">Дополнительные сведения см. в разделе [как: Break и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="626c4-122">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="626c4-123">Двоеточие (`:`) символ также используется для установления метки оператора.</span><span class="sxs-lookup"><span data-stu-id="626c4-123">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="626c4-124">Дополнительные сведения см. в разделе [как: операторы метку](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="626c4-124">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="626c4-125">Сцепление</span><span class="sxs-lookup"><span data-stu-id="626c4-125">Concatenation</span></span>  
 <span data-ttu-id="626c4-126">Используйте `&` оператор для *объединение*, или сцепления, строк вместе.</span><span class="sxs-lookup"><span data-stu-id="626c4-126">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="626c4-127">Не следует путать его с `+` оператор, который складывает числовых значений.</span><span class="sxs-lookup"><span data-stu-id="626c4-127">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="626c4-128">Если вы используете `+` оператор для сцепления при работе с числовыми значениями, можно получить неверные результаты.</span><span class="sxs-lookup"><span data-stu-id="626c4-128">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="626c4-129">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="626c4-129">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="626c4-130">[!code-vb[VbVbcnConventions&#13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c4-130">[!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span></span>  
  
 <span data-ttu-id="626c4-131">После выполнения предыдущего кода значение `resultA` имеет значение 21.01, а `resultB` — «10.0111».</span><span class="sxs-lookup"><span data-stu-id="626c4-131">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="626c4-132">Операторы доступа к членам</span><span class="sxs-lookup"><span data-stu-id="626c4-132">Member Access Operators</span></span>  
 <span data-ttu-id="626c4-133">Для доступа к члену типа, используйте точку (`.`) или восклицательный знак (`!`) оператор между именем типа и имя элемента.</span><span class="sxs-lookup"><span data-stu-id="626c4-133">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="626c4-134">Точка (.) Оператор</span><span class="sxs-lookup"><span data-stu-id="626c4-134">Dot (.) Operator</span></span>  
 <span data-ttu-id="626c4-135">Используйте `.` оператором оператор доступа к члену класса, структуры, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="626c4-135">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="626c4-136">Элемент может быть поле, свойство, событие или метод.</span><span class="sxs-lookup"><span data-stu-id="626c4-136">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="626c4-137">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="626c4-137">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="626c4-138">[!code-vb[VbVbcnConventions&#14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c4-138">[!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span></span>  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="626c4-139">Восклицательный знак (!) Оператор</span><span class="sxs-lookup"><span data-stu-id="626c4-139">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="626c4-140">Используйте `!` оператор только для класса или интерфейса, как оператор доступа к словарям.</span><span class="sxs-lookup"><span data-stu-id="626c4-140">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="626c4-141">Класс или интерфейс должен иметь свойство по умолчанию, который принимает один `String` аргумент.</span><span class="sxs-lookup"><span data-stu-id="626c4-141">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="626c4-142">Идентификатор, следующий сразу `!` оператор становится значение аргумента, переданного свойства по умолчанию как строку.</span><span class="sxs-lookup"><span data-stu-id="626c4-142">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="626c4-143">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="626c4-143">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="626c4-144">[!code-vb[VbVbcnConventions&#15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="626c4-144">[!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span></span>  
  
 <span data-ttu-id="626c4-145">Три выходных строк `MsgBox` все отображать значение `32856`.</span><span class="sxs-lookup"><span data-stu-id="626c4-145">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="626c4-146">В первой строке используется традиционный доступ к свойству `index`, вторая использует тот факт, `index` — свойство по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.</span><span class="sxs-lookup"><span data-stu-id="626c4-146">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="626c4-147">Обратите внимание, что второй операнд `!` оператор должен быть допустимым идентификатором Visual Basic, не заключенный в двойные кавычки (`" "`).</span><span class="sxs-lookup"><span data-stu-id="626c4-147">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="626c4-148">Другими словами нельзя использовать строковый литерал или строковую переменную.</span><span class="sxs-lookup"><span data-stu-id="626c4-148">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="626c4-149">Следующее изменение в последней строке `MsgBox` вызов приводит к ошибке, поскольку `"X"` является закрытой строка литерала.</span><span class="sxs-lookup"><span data-stu-id="626c4-149">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="626c4-150">Ссылки на коллекции по умолчанию должны быть явными.</span><span class="sxs-lookup"><span data-stu-id="626c4-150">References to default collections must be explicit.</span></span> <span data-ttu-id="626c4-151">В частности, нельзя использовать `!` оператор переменной позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="626c4-151">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="626c4-152">`!` Символ также используется в качестве `Single` знак типа.</span><span class="sxs-lookup"><span data-stu-id="626c4-152">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626c4-153">См. также</span><span class="sxs-lookup"><span data-stu-id="626c4-153">See Also</span></span>  
 <span data-ttu-id="626c4-154">[Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="626c4-154">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="626c4-155"> [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="626c4-155"> [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
