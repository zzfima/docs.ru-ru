---
title: "Операторы сравнения в Visual Basic | Документы Microsoft"
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
- comparison operators, comparing strings
- comparison operators, comparing objects
- strings [Visual Basic], comparing
- comparison operators
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers, comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values, comparing
- comparison operators, comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
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
ms.openlocfilehash: a958481fa04cb1a9abde69c5215dccd6dbbe4a14
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="d07b0-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d07b0-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="d07b0-103">Операторы сравнения сравнивают два выражения и возвращают `Boolean` значение, которое представляет связь между значениями.</span><span class="sxs-lookup"><span data-stu-id="d07b0-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="d07b0-104">Операторы используются для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов.</span><span class="sxs-lookup"><span data-stu-id="d07b0-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="d07b0-105">Ниже представлено описание всех трех типов операторов.</span><span class="sxs-lookup"><span data-stu-id="d07b0-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="d07b0-106">Сравнение числовых значений</span><span class="sxs-lookup"><span data-stu-id="d07b0-106">Comparing Numeric Values</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d07b0-107">сравнивает числовые значения с помощью шести числовых операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="d07b0-107"> compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="d07b0-108">Каждый оператор принимает в качестве операндов два выражения, которые возвращают числовые значения.</span><span class="sxs-lookup"><span data-stu-id="d07b0-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="d07b0-109">В следующей таблице перечислены операторы и приведены примеры каждого.</span><span class="sxs-lookup"><span data-stu-id="d07b0-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="d07b0-110">Оператор</span><span class="sxs-lookup"><span data-stu-id="d07b0-110">Operator</span></span>|<span data-ttu-id="d07b0-111">Проверяемое условие</span><span class="sxs-lookup"><span data-stu-id="d07b0-111">Condition tested</span></span>|<span data-ttu-id="d07b0-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="d07b0-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="d07b0-113">`=`(Равенство)</span><span class="sxs-lookup"><span data-stu-id="d07b0-113">`=` (Equality)</span></span>|<span data-ttu-id="d07b0-114">Значение первого выражения равно значению второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="d07b0-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="d07b0-118">`<>`(Неравенство)</span><span class="sxs-lookup"><span data-stu-id="d07b0-118">`<>` (Inequality)</span></span>|<span data-ttu-id="d07b0-119">Значение первого выражения равно значению второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="d07b0-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="d07b0-123">`<`(Меньше чем)</span><span class="sxs-lookup"><span data-stu-id="d07b0-123">`<` (Less than)</span></span>|<span data-ttu-id="d07b0-124">Значение первого выражения меньше значения второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="d07b0-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="d07b0-128">`>`(Больше)</span><span class="sxs-lookup"><span data-stu-id="d07b0-128">`>` (Greater than)</span></span>|<span data-ttu-id="d07b0-129">Значение первого выражения больше значения второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="d07b0-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="d07b0-133">`<=`(Меньше или равно)</span><span class="sxs-lookup"><span data-stu-id="d07b0-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="d07b0-134">Значение первого выражения меньше или равно значению второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="d07b0-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="d07b0-138">`>=`(Больше или равно)</span><span class="sxs-lookup"><span data-stu-id="d07b0-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="d07b0-139">Значение первого выражения больше или равно значению второго?</span><span class="sxs-lookup"><span data-stu-id="d07b0-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="d07b0-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="d07b0-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="d07b0-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="d07b0-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="d07b0-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="d07b0-143">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="d07b0-143">Comparing Strings</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d07b0-144">сравнение строк с помощью [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md) и числовых операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="d07b0-144"> compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="d07b0-145">`Like` Оператор позволяет указать шаблон.</span><span class="sxs-lookup"><span data-stu-id="d07b0-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="d07b0-146">Строка затем сравнивается с шаблоном, и если он соответствует, результатом будет `True`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="d07b0-147">В противном случае результатом является `False`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="d07b0-148">Числовые операторы позволяют сравнивать `String` значения на основе их порядка сортировки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="d07b0-149">В предыдущем примере результатом является `True` , поскольку первый символ в первой строке сортируется до первого символа во второй строке.</span><span class="sxs-lookup"><span data-stu-id="d07b0-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="d07b0-150">Если первые символы равны, сравнение будет по-прежнему следующий символ в обеих строках и т.д.</span><span class="sxs-lookup"><span data-stu-id="d07b0-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="d07b0-151">Можно также проверить равенство строк с помощью оператора равенства, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="d07b0-152">Если одна строка является префиксом другой, например «aa» и «aaa», более длинная строка считается больше, чем более короткие строки.</span><span class="sxs-lookup"><span data-stu-id="d07b0-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="d07b0-153">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="d07b0-154">Порядок сортировки основан на двоичном сравнении или текстовом сравнении в зависимости от параметра `Option Compare`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="d07b0-155">Дополнительные сведения см. [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d07b0-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="d07b0-156">Сравнение объектов</span><span class="sxs-lookup"><span data-stu-id="d07b0-156">Comparing Objects</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d07b0-157">сравниваются две ссылочные переменные объекта с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d07b0-157"> compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="d07b0-158">Чтобы определить, если две ссылочные переменные ссылаются на один и тот же экземпляр объекта, можно использовать любой из этих операторов.</span><span class="sxs-lookup"><span data-stu-id="d07b0-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="d07b0-159">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-159">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="d07b0-160">[!code-vb[VbVbalrOperators&#65;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d07b0-160">[!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="d07b0-161">В предыдущем примере `x Is y` равен `True`, поскольку обе переменные ссылаются на один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d07b0-161">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="d07b0-162">Противоположный результат в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-162">Contrast this result with the following example.</span></span>  
  
 <span data-ttu-id="d07b0-163">[!code-vb[VbVbalrOperators&#66;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d07b0-163">[!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="d07b0-164">В предыдущем примере `x Is y` равен `False`, поскольку, хотя переменные и ссылаются на объекты одного типа, ссылки на разные экземпляры этого типа.</span><span class="sxs-lookup"><span data-stu-id="d07b0-164">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="d07b0-165">При необходимости тестирования для двух объектов, не указывает на тот же экземпляр `IsNot` оператор позволяет избежать грамматически грубо сочетание `Not` и `Is`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-165">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="d07b0-166">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-166">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="d07b0-167">[!code-vb[VbVbalrOperators&#67;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="d07b0-167">[!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span></span>  
  
 <span data-ttu-id="d07b0-168">В предыдущем примере `If a IsNot b` эквивалентно `If Not a Is b`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-168">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="d07b0-169">Сравнение типов объектов</span><span class="sxs-lookup"><span data-stu-id="d07b0-169">Comparing Object Type</span></span>  
 <span data-ttu-id="d07b0-170">Можно проверить, является ли объект определенного типа с `TypeOf`... `Is` выражение.</span><span class="sxs-lookup"><span data-stu-id="d07b0-170">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="d07b0-171">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d07b0-171">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="d07b0-172">Когда `typename` указывает тип интерфейса, то `TypeOf`... `Is` возвращает значение `True` , если объект реализует тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d07b0-172">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="d07b0-173">Когда `typename` является типом класса, выражение возвращает `True` , если объект является экземпляром указанного класса или класса, производного от указанного класса.</span><span class="sxs-lookup"><span data-stu-id="d07b0-173">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="d07b0-174">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d07b0-174">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="d07b0-175">[!code-vb[VbVbalrOperators&#68;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="d07b0-175">[!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span></span>  
  
 <span data-ttu-id="d07b0-176">В предыдущем примере `TypeOf x Is Control` выражение `True` так как тип `x` — `Button`, который наследуется от `Control`.</span><span class="sxs-lookup"><span data-stu-id="d07b0-176">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="d07b0-177">Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d07b0-177">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07b0-178">См. также</span><span class="sxs-lookup"><span data-stu-id="d07b0-178">See Also</span></span>  
 <span data-ttu-id="d07b0-179">[Сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="d07b0-179">[Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="d07b0-180"> [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d07b0-180"> [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="d07b0-181"> [Операторы](../../../../visual-basic/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="d07b0-181"> [Operators](../../../../visual-basic/language-reference/operators/index.md) </span></span>  
<span data-ttu-id="d07b0-182"> [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d07b0-182"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="d07b0-183"> [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d07b0-183"> [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span></span>  
<span data-ttu-id="d07b0-184"> [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="d07b0-184"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
