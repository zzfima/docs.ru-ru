---
title: Операторы сравнения
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: ea7604626ede66da818e4bc22fe4922bc752dc2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336084"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="268d9-102">Операторы сравнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="268d9-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="268d9-103">Ниже приведены операторы сравнения, определенные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="268d9-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="268d9-104">Оператор `<`</span><span class="sxs-lookup"><span data-stu-id="268d9-104">`<` operator</span></span>

 <span data-ttu-id="268d9-105">Оператор `<=`</span><span class="sxs-lookup"><span data-stu-id="268d9-105">`<=` operator</span></span>

 <span data-ttu-id="268d9-106">Оператор `>`</span><span class="sxs-lookup"><span data-stu-id="268d9-106">`>` operator</span></span>

 <span data-ttu-id="268d9-107">Оператор `>=`</span><span class="sxs-lookup"><span data-stu-id="268d9-107">`>=` operator</span></span>

 <span data-ttu-id="268d9-108">Оператор `=`</span><span class="sxs-lookup"><span data-stu-id="268d9-108">`=` operator</span></span>

 <span data-ttu-id="268d9-109">Оператор `<>`</span><span class="sxs-lookup"><span data-stu-id="268d9-109">`<>` operator</span></span>

 [<span data-ttu-id="268d9-110">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="268d9-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)

 [<span data-ttu-id="268d9-111">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="268d9-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [<span data-ttu-id="268d9-112">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="268d9-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)

 <span data-ttu-id="268d9-113">Эти операторы сравнивают два выражения, чтобы определить, равны ли они, и если нет, то их отличия.</span><span class="sxs-lookup"><span data-stu-id="268d9-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="268d9-114">`Is`, `IsNot`и `Like` подробно обсуждаются на отдельных страницах справки.</span><span class="sxs-lookup"><span data-stu-id="268d9-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="268d9-115">Реляционные операторы сравнения подробно обсуждаются на этой странице.</span><span class="sxs-lookup"><span data-stu-id="268d9-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="268d9-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="268d9-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="268d9-117">Части</span><span class="sxs-lookup"><span data-stu-id="268d9-117">Parts</span></span>
 `result`  
 <span data-ttu-id="268d9-118">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-118">Required.</span></span> <span data-ttu-id="268d9-119">Значение `Boolean`, представляющее результат сравнения.</span><span class="sxs-lookup"><span data-stu-id="268d9-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="268d9-120">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="268d9-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="268d9-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-121">Required.</span></span> <span data-ttu-id="268d9-122">Любое выражение.</span><span class="sxs-lookup"><span data-stu-id="268d9-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="268d9-123">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-123">Required.</span></span> <span data-ttu-id="268d9-124">Любой оператор реляционного сравнения.</span><span class="sxs-lookup"><span data-stu-id="268d9-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="268d9-125">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="268d9-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="268d9-126">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-126">Required.</span></span> <span data-ttu-id="268d9-127">Имена ссылочных объектов.</span><span class="sxs-lookup"><span data-stu-id="268d9-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="268d9-128">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-128">Required.</span></span> <span data-ttu-id="268d9-129">Произвольное выражение `String` .</span><span class="sxs-lookup"><span data-stu-id="268d9-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="268d9-130">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="268d9-130">Required.</span></span> <span data-ttu-id="268d9-131">Любое `String`ое выражение или диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="268d9-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="268d9-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="268d9-132">Remarks</span></span>
 <span data-ttu-id="268d9-133">В следующей таблице содержится список реляционных операторов сравнения и условий, которые определяют, является ли `result` `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="268d9-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="268d9-134">оператора</span><span class="sxs-lookup"><span data-stu-id="268d9-134">Operator</span></span>|<span data-ttu-id="268d9-135">`True`, если</span><span class="sxs-lookup"><span data-stu-id="268d9-135">`True` if</span></span>|<span data-ttu-id="268d9-136">`False`, если</span><span class="sxs-lookup"><span data-stu-id="268d9-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="268d9-137">`<` (меньше)</span><span class="sxs-lookup"><span data-stu-id="268d9-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="268d9-138">`<=` (меньше или равно)</span><span class="sxs-lookup"><span data-stu-id="268d9-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="268d9-139">`>` (больше)</span><span class="sxs-lookup"><span data-stu-id="268d9-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="268d9-140">`>=` (больше или равно)</span><span class="sxs-lookup"><span data-stu-id="268d9-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="268d9-141">`=` (равно)</span><span class="sxs-lookup"><span data-stu-id="268d9-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="268d9-142">`<>` (не равно)</span><span class="sxs-lookup"><span data-stu-id="268d9-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="268d9-143">[Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md) также используется в качестве оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="268d9-143">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="268d9-144">Оператор `Is`, оператор `IsNot` и оператор `Like` имеют определенные функции сравнения, отличные от операторов в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="268d9-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="268d9-145">Сравнение чисел</span><span class="sxs-lookup"><span data-stu-id="268d9-145">Comparing Numbers</span></span>
 <span data-ttu-id="268d9-146">При сравнении выражения типа `Single` с одним из типов `Double`выражение `Single` преобразуется в `Double`.</span><span class="sxs-lookup"><span data-stu-id="268d9-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="268d9-147">Это поведение противоположено поведению, обнаруженному в Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="268d9-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="268d9-148">Аналогично, при сравнении выражения типа `Decimal` с выражением типа `Single` или `Double`выражение `Decimal` преобразуется в `Single` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="268d9-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="268d9-149">Для `Decimal`ных выражений любое значение дробной части меньше 1E-28 может быть потеряно.</span><span class="sxs-lookup"><span data-stu-id="268d9-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="268d9-150">Такая утрата дробных значений может привести к тому, что два значения будут сравниваться как равные, если это не так.</span><span class="sxs-lookup"><span data-stu-id="268d9-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="268d9-151">По этой причине следует соблюдать осторожность при использовании равенства (`=`) для сравнения двух переменных с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="268d9-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="268d9-152">Безопаснее проверить, является ли абсолютное значение разницы между двумя числами меньше, чем небольшая допустимая погрешность.</span><span class="sxs-lookup"><span data-stu-id="268d9-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="268d9-153">Точность чисел с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="268d9-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="268d9-154">При работе с числами с плавающей запятой следует помнить, что они не всегда имеют точное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="268d9-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="268d9-155">Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и [оператор Mod](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="268d9-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="268d9-156">Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="268d9-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="268d9-157">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="268d9-157">Comparing Strings</span></span>
 <span data-ttu-id="268d9-158">При сравнении строк строковые выражения оцениваются на основе их порядка сортировки в алфавитном порядке, который зависит от параметра `Option Compare`.</span><span class="sxs-lookup"><span data-stu-id="268d9-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="268d9-159">`Option Compare Binary` базовые сравнения строк по порядковому номеру сортировки, производным от внутренних двоичных представлений символов.</span><span class="sxs-lookup"><span data-stu-id="268d9-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="268d9-160">Порядок сортировки определяется кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="268d9-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="268d9-161">В следующем примере показан типичный порядок двоичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="268d9-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="268d9-162">`Option Compare Text` базовые сравнения строк при сравнении без учета регистра, текстовый порядок сортировки определяется языковым стандартом приложения.</span><span class="sxs-lookup"><span data-stu-id="268d9-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="268d9-163">При установке `Option Compare Text` и сортировке символов в предыдущем примере применяется следующий порядок сортировки текста:</span><span class="sxs-lookup"><span data-stu-id="268d9-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="268d9-164">Зависимость от локали</span><span class="sxs-lookup"><span data-stu-id="268d9-164">Locale Dependence</span></span>
 <span data-ttu-id="268d9-165">При установке `Option Compare Text`результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="268d9-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="268d9-166">Два символа могут сравниваться как одинаковые в одном языковом стандарте, но не в другом.</span><span class="sxs-lookup"><span data-stu-id="268d9-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="268d9-167">Если вы используете сравнение строк для принятия важных решений, например, принимаете ли вы попытку входа в систему, вы должны быть извещены о конфиденциальности языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="268d9-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="268d9-168">Попробуйте либо задать `Option Compare Binary`, либо вызвать <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, в котором учитывается языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="268d9-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="268d9-169">Программирование без типов с помощью реляционных операторов сравнения</span><span class="sxs-lookup"><span data-stu-id="268d9-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="268d9-170">Использование реляционных операторов сравнения с выражениями `Object` не допускается в `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="268d9-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="268d9-171">Если `Option Strict` `Off`и либо `expression1`, либо `expression2` является выражением `Object`, то типы времени выполнения определяют, как они сравниваются.</span><span class="sxs-lookup"><span data-stu-id="268d9-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="268d9-172">В следующей таблице показано, как сравниваются выражения и результат сравнения, в зависимости от типа операндов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="268d9-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="268d9-173">Если операнды</span><span class="sxs-lookup"><span data-stu-id="268d9-173">If operands are</span></span>|<span data-ttu-id="268d9-174">Сравнение:</span><span class="sxs-lookup"><span data-stu-id="268d9-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="268d9-175">Оба `String`</span><span class="sxs-lookup"><span data-stu-id="268d9-175">Both `String`</span></span>|<span data-ttu-id="268d9-176">Сравнение сортировки на основе характеристик сортировки строк.</span><span class="sxs-lookup"><span data-stu-id="268d9-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="268d9-177">Оба числовых</span><span class="sxs-lookup"><span data-stu-id="268d9-177">Both numeric</span></span>|<span data-ttu-id="268d9-178">Объекты, преобразованные в `Double`, числовое сравнение.</span><span class="sxs-lookup"><span data-stu-id="268d9-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="268d9-179">Один числовой и один `String`</span><span class="sxs-lookup"><span data-stu-id="268d9-179">One numeric and one `String`</span></span>|<span data-ttu-id="268d9-180">`String` преобразуется в `Double` и выполняется числовое сравнение.</span><span class="sxs-lookup"><span data-stu-id="268d9-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="268d9-181">Если `String` невозможно преобразовать в `Double`, создается исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="268d9-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="268d9-182">Один или оба являются ссылочными типами, отличными от `String`</span><span class="sxs-lookup"><span data-stu-id="268d9-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="268d9-183">Возникает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="268d9-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="268d9-184">Числовые сравнения обрабатывают `Nothing` как 0.</span><span class="sxs-lookup"><span data-stu-id="268d9-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="268d9-185">Сравнения строк обрабатывают `Nothing` как `""` (пустая строка).</span><span class="sxs-lookup"><span data-stu-id="268d9-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="268d9-186">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="268d9-186">Overloading</span></span>
 <span data-ttu-id="268d9-187">Реляционные операторы сравнения (`<`.</span><span class="sxs-lookup"><span data-stu-id="268d9-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="268d9-188">`<=`, `>`, `>=`, `=`, `<>`) могут быть *перегружены*. Это означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="268d9-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="268d9-189">Если в коде используются какие-либо из этих операторов в таком классе или структуре, убедитесь, что вы понимаете переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="268d9-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="268d9-190">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="268d9-190">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="268d9-191">Обратите внимание, что [оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md) можно перегружать только как оператор реляционного сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="268d9-191">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="268d9-192">Пример</span><span class="sxs-lookup"><span data-stu-id="268d9-192">Example</span></span>
 <span data-ttu-id="268d9-193">В следующем примере показаны различные варианты использования реляционных операторов сравнения, которые используются для сравнения выражений.</span><span class="sxs-lookup"><span data-stu-id="268d9-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="268d9-194">Реляционные операторы сравнения возвращают `Boolean` результат, который представляет, принимает ли указанное выражение значение `True`.</span><span class="sxs-lookup"><span data-stu-id="268d9-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="268d9-195">При применении операторов `>` и `<` к строкам сравнение выполняется с использованием обычного алфавитного порядка сортировки строк.</span><span class="sxs-lookup"><span data-stu-id="268d9-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="268d9-196">Этот порядок может зависеть от настроек языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="268d9-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="268d9-197">Учитывается ли сортировка с учетом регистра или не зависит от параметра [параметра Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="268d9-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="268d9-198">В предыдущем примере первое сравнение возвращает `False`, а оставшиеся сравнения возвращают `True`.</span><span class="sxs-lookup"><span data-stu-id="268d9-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="268d9-199">См. также</span><span class="sxs-lookup"><span data-stu-id="268d9-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="268d9-200">Оператор =</span><span class="sxs-lookup"><span data-stu-id="268d9-200">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="268d9-201">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="268d9-201">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="268d9-202">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="268d9-202">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="268d9-203">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="268d9-203">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="268d9-204">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="268d9-204">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
