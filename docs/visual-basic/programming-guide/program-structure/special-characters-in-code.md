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
ms.openlocfilehash: 95bef937912e35cd828bf0090b4cf48ccb3290cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962464"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="1d873-102">Специальные символы в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d873-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="1d873-103">Иногда в коде необходимо использовать специальные символы, то есть символы, не являющиеся алфавитными или числовыми.</span><span class="sxs-lookup"><span data-stu-id="1d873-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="1d873-104">Знаки пунктуации и специальные символы в Visual Basic кодировке имеют различные варианты использования, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой.</span><span class="sxs-lookup"><span data-stu-id="1d873-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="1d873-105">Эти знаки не определяют операции, подлежащие выполнению.</span><span class="sxs-lookup"><span data-stu-id="1d873-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="1d873-106">Скобки</span><span class="sxs-lookup"><span data-stu-id="1d873-106">Parentheses</span></span>  
 <span data-ttu-id="1d873-107">Используйте круглые скобки при определении процедуры, например `Sub` или. `Function`</span><span class="sxs-lookup"><span data-stu-id="1d873-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="1d873-108">Все списки аргументов процедур необходимо заключать в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="1d873-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="1d873-109">Также круглые скобки используются для помещения переменных или аргументов в логические группы, особенно для переопределения порядка приоритета операторов по умолчанию в сложном выражении.</span><span class="sxs-lookup"><span data-stu-id="1d873-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="1d873-110">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1d873-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="1d873-111">После выполнения предыдущего кода значение `d` равно 8,225, а `e` значение равно 3.</span><span class="sxs-lookup"><span data-stu-id="1d873-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="1d873-112">Вычисление для `d` `/` использует приоритет по умолчанию `d = b + (c / a)`over `+` и эквивалентен.</span><span class="sxs-lookup"><span data-stu-id="1d873-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="1d873-113">Круглые скобки в вычислении для `e` переопределения приоритета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d873-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="1d873-114">Разделители</span><span class="sxs-lookup"><span data-stu-id="1d873-114">Separators</span></span>  
 <span data-ttu-id="1d873-115">Разделители выполняют свои имена: они разделяют разделы кода.</span><span class="sxs-lookup"><span data-stu-id="1d873-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="1d873-116">В Visual Basic символ разделителя является двоеточием (`:`).</span><span class="sxs-lookup"><span data-stu-id="1d873-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="1d873-117">Используйте разделители, если требуется включить несколько операторов в одну строку, а не отдельные строки.</span><span class="sxs-lookup"><span data-stu-id="1d873-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="1d873-118">Это экономит пространство и повышает удобочитаемость кода.</span><span class="sxs-lookup"><span data-stu-id="1d873-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="1d873-119">В следующем примере показаны три инструкции, разделенные двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="1d873-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="1d873-120">Дополнительные сведения см. в разделе [Практическое руководство. Разбейте и объедините операторы](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)в коде.</span><span class="sxs-lookup"><span data-stu-id="1d873-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="1d873-121">Символ двоеточия`:`() также используется для обозначения метки оператора.</span><span class="sxs-lookup"><span data-stu-id="1d873-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="1d873-122">Дополнительные сведения см. в разделе [Практическое руководство. Операторы](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)меток.</span><span class="sxs-lookup"><span data-stu-id="1d873-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="1d873-123">Сцепление</span><span class="sxs-lookup"><span data-stu-id="1d873-123">Concatenation</span></span>  
 <span data-ttu-id="1d873-124">Используйте оператор для объединения или связывания строк. `&`</span><span class="sxs-lookup"><span data-stu-id="1d873-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="1d873-125">Не путайте его с `+` оператором, который добавляет вместе числовые значения.</span><span class="sxs-lookup"><span data-stu-id="1d873-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="1d873-126">При использовании `+` оператора для сцепления с числовыми значениями можно получить неверные результаты.</span><span class="sxs-lookup"><span data-stu-id="1d873-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="1d873-127">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="1d873-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="1d873-128">После выполнения предыдущего кода значение `resultA` равно 21,01, а `resultB` значение равно "10,0111".</span><span class="sxs-lookup"><span data-stu-id="1d873-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="1d873-129">Операторы доступа к членам</span><span class="sxs-lookup"><span data-stu-id="1d873-129">Member Access Operators</span></span>  
 <span data-ttu-id="1d873-130">Для доступа к члену типа используется оператор dot (`.`) или восклицательный знак (`!`) между именем типа и именем члена.</span><span class="sxs-lookup"><span data-stu-id="1d873-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="1d873-131">Точка (.) Оператор</span><span class="sxs-lookup"><span data-stu-id="1d873-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="1d873-132">`.` Используйте оператор для класса, структуры, интерфейса или перечисления в качестве оператора доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="1d873-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="1d873-133">Элемент может быть полем, свойством, событием или методом.</span><span class="sxs-lookup"><span data-stu-id="1d873-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="1d873-134">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1d873-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="1d873-135">Восклицательный знак (!) Оператор</span><span class="sxs-lookup"><span data-stu-id="1d873-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="1d873-136">`!` Оператор используется только для класса или интерфейса в качестве оператора доступа в словаре.</span><span class="sxs-lookup"><span data-stu-id="1d873-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="1d873-137">Класс или интерфейс должен иметь свойство по умолчанию, принимающее один `String` аргумент.</span><span class="sxs-lookup"><span data-stu-id="1d873-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="1d873-138">Идентификатор, непосредственно следующий за `!` оператором, становится значением аргумента, передаваемым в свойство по умолчанию в виде строки.</span><span class="sxs-lookup"><span data-stu-id="1d873-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="1d873-139">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="1d873-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="1d873-140">В трех строках `MsgBox` вывода отображается значение `32856`.</span><span class="sxs-lookup"><span data-stu-id="1d873-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="1d873-141">В первой строке используется традиционный доступ к свойству `index`, а во втором используется тот факт, который `index` является свойством по умолчанию `hasDefault`класса, а третий использует словарный доступ к классу.</span><span class="sxs-lookup"><span data-stu-id="1d873-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="1d873-142">Обратите внимание, что второй операнд `!` оператора должен быть допустимым Visual Basic идентификатором, не заключенным в двойные кавычки (`" "`).</span><span class="sxs-lookup"><span data-stu-id="1d873-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="1d873-143">Иными словами, нельзя использовать строковый литерал или строковую переменную.</span><span class="sxs-lookup"><span data-stu-id="1d873-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="1d873-144">Следующее изменение в последней строке `MsgBox` вызова приводит к ошибке, поскольку `"X"` является заключенным строковым литералом.</span><span class="sxs-lookup"><span data-stu-id="1d873-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="1d873-145">Ссылки на коллекции по умолчанию должны быть явными.</span><span class="sxs-lookup"><span data-stu-id="1d873-145">References to default collections must be explicit.</span></span> <span data-ttu-id="1d873-146">В частности, нельзя использовать `!` оператор для переменной с поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="1d873-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="1d873-147">Символ также используется в `Single` качестве символа типа. `!`</span><span class="sxs-lookup"><span data-stu-id="1d873-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d873-148">См. также</span><span class="sxs-lookup"><span data-stu-id="1d873-148">See also</span></span>

- [<span data-ttu-id="1d873-149">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="1d873-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="1d873-150">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="1d873-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
