---
title: Специальные символы в коде (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 932b38d97b36292e66bfad91a9a3799459d3b73c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="f485d-102">Специальные символы в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f485d-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="f485d-103">Иногда необходимо использовать специальные символы в коде, то есть символы, которые не являются буквой или цифрой.</span><span class="sxs-lookup"><span data-stu-id="f485d-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="f485d-104">Знаки пунктуации и специальные символы в кодировке Visual Basic имеют различные применения, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой.</span><span class="sxs-lookup"><span data-stu-id="f485d-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="f485d-105">Эти знаки не определяют операции, подлежащие выполнению.</span><span class="sxs-lookup"><span data-stu-id="f485d-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="f485d-106">Круглые скобки</span><span class="sxs-lookup"><span data-stu-id="f485d-106">Parentheses</span></span>  
 <span data-ttu-id="f485d-107">Используйте круглые скобки при определении процедуры, такие как `Sub` или `Function`.</span><span class="sxs-lookup"><span data-stu-id="f485d-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="f485d-108">Все списки аргументов в процедуру необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="f485d-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="f485d-109">Вы также использовать круглые скобки для помещения переменными или аргументами в логические группы, особенно, чтобы переопределить порядок приоритета операторов в сложное выражение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f485d-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="f485d-110">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f485d-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 <span data-ttu-id="f485d-111">После выполнения предыдущего кода значение `d` равняется 8,225, а значение `e` равно 3.</span><span class="sxs-lookup"><span data-stu-id="f485d-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="f485d-112">Расчет `d` используется приоритет по умолчанию `/` над `+` и эквивалентно `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="f485d-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="f485d-113">Круглые скобки в вычислении `e` наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="f485d-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="f485d-114">Разделители</span><span class="sxs-lookup"><span data-stu-id="f485d-114">Separators</span></span>  
 <span data-ttu-id="f485d-115">В качестве разделителей сделать их названия: они разделяют сегменты кода.</span><span class="sxs-lookup"><span data-stu-id="f485d-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="f485d-116">В Visual Basic, знак разделителя используется двоеточие (`:`).</span><span class="sxs-lookup"><span data-stu-id="f485d-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="f485d-117">Разделители используются в том случае, если вы хотите использовать несколько операторов в отдельных строках в одну строку.</span><span class="sxs-lookup"><span data-stu-id="f485d-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="f485d-118">Это экономит место и повышает удобочитаемость кода.</span><span class="sxs-lookup"><span data-stu-id="f485d-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="f485d-119">В следующем примере показано три инструкции, разделенные точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="f485d-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 <span data-ttu-id="f485d-120">Дополнительные сведения см. в разделе [как: Break и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f485d-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="f485d-121">Двоеточие (`:`) символ также используется для установления метки оператора.</span><span class="sxs-lookup"><span data-stu-id="f485d-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="f485d-122">Дополнительные сведения см. в разделе [как: метка инструкции](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="f485d-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="f485d-123">Сцепление</span><span class="sxs-lookup"><span data-stu-id="f485d-123">Concatenation</span></span>  
 <span data-ttu-id="f485d-124">Используйте `&` оператор для *объединение*, или связывания строки.</span><span class="sxs-lookup"><span data-stu-id="f485d-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="f485d-125">Не следует путать с `+` оператор, который складывает числовых значений.</span><span class="sxs-lookup"><span data-stu-id="f485d-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="f485d-126">Если вы используете `+` оператор для сцепления при работе с числовыми значениями, можно получить неверные результаты.</span><span class="sxs-lookup"><span data-stu-id="f485d-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="f485d-127">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="f485d-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 <span data-ttu-id="f485d-128">После выполнения предыдущего кода значение `resultA` 21.01 и значение `resultB` — «10.0111».</span><span class="sxs-lookup"><span data-stu-id="f485d-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="f485d-129">Операторы доступа к членам</span><span class="sxs-lookup"><span data-stu-id="f485d-129">Member Access Operators</span></span>  
 <span data-ttu-id="f485d-130">Для доступа к члену типа, используется точка (`.`) или восклицательный знак (`!`) оператор между именем типа и имени элемента.</span><span class="sxs-lookup"><span data-stu-id="f485d-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="f485d-131">Точка (.) Оператор</span><span class="sxs-lookup"><span data-stu-id="f485d-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="f485d-132">Используйте `.` оператора для класса, структуры, интерфейса или перечисления как оператор доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="f485d-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="f485d-133">Элемент может быть поле, свойство, событие или метод.</span><span class="sxs-lookup"><span data-stu-id="f485d-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="f485d-134">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f485d-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="f485d-135">Восклицательный знак (!) Оператор</span><span class="sxs-lookup"><span data-stu-id="f485d-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="f485d-136">Используйте `!` оператор только для класса или интерфейса, как оператор доступа к словарям.</span><span class="sxs-lookup"><span data-stu-id="f485d-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="f485d-137">Класс или интерфейс должен иметь свойство по умолчанию, который принимает один `String` аргумент.</span><span class="sxs-lookup"><span data-stu-id="f485d-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="f485d-138">Идентификатор, следующий сразу `!` оператор становится значение аргумента, переданного свойства по умолчанию как строку.</span><span class="sxs-lookup"><span data-stu-id="f485d-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="f485d-139">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="f485d-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 <span data-ttu-id="f485d-140">Три выходных строк `MsgBox` все отобразить значение `32856`.</span><span class="sxs-lookup"><span data-stu-id="f485d-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="f485d-141">В первой строке используется традиционный доступ к свойству `index`, вторая использует тот факт, `index` является свойством по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.</span><span class="sxs-lookup"><span data-stu-id="f485d-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="f485d-142">Обратите внимание, что второй операнд `!` оператор должен быть допустимым идентификатором Visual Basic не заключен в двойные кавычки (`" "`).</span><span class="sxs-lookup"><span data-stu-id="f485d-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="f485d-143">Другими словами нельзя использовать строковый литерал или строковую переменную.</span><span class="sxs-lookup"><span data-stu-id="f485d-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="f485d-144">Следующее изменение в последней строке `MsgBox` вызов приводит к ошибке, поскольку `"X"` является закрытой строка литерала.</span><span class="sxs-lookup"><span data-stu-id="f485d-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="f485d-145">Ссылки на коллекции по умолчанию должны быть явными.</span><span class="sxs-lookup"><span data-stu-id="f485d-145">References to default collections must be explicit.</span></span> <span data-ttu-id="f485d-146">В частности, нельзя использовать `!` оператор переменной позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="f485d-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="f485d-147">`!` Символ также используется в качестве `Single` тип символа.</span><span class="sxs-lookup"><span data-stu-id="f485d-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f485d-148">См. также</span><span class="sxs-lookup"><span data-stu-id="f485d-148">See Also</span></span>  
 [<span data-ttu-id="f485d-149">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="f485d-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="f485d-150">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="f485d-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
