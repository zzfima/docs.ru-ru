---
title: Операторы сравнения (Visual Basic)
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
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821040"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="07738-102">Операторы сравнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07738-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="07738-103">Ниже приведены операторы сравнения, определенные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="07738-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="07738-104">`<` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-104">`<` operator</span></span>  
  
 <span data-ttu-id="07738-105">`<=` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-105">`<=` operator</span></span>  
  
 <span data-ttu-id="07738-106">`>` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-106">`>` operator</span></span>  
  
 <span data-ttu-id="07738-107">`>=` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-107">`>=` operator</span></span>  
  
 <span data-ttu-id="07738-108">`=` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-108">`=` operator</span></span>  
  
 <span data-ttu-id="07738-109">`<>` Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="07738-110">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="07738-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="07738-111">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="07738-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="07738-112">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="07738-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="07738-113">Эти операторы сравнивают два выражения и определяет ли они равны, и если это не так, как они отличаются.</span><span class="sxs-lookup"><span data-stu-id="07738-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="07738-114">`Is`, `IsNot`, и `Like` подробно обсуждаются на отдельных страницах справки.</span><span class="sxs-lookup"><span data-stu-id="07738-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="07738-115">Операторы сравнения подробно описаны на этой странице.</span><span class="sxs-lookup"><span data-stu-id="07738-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07738-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07738-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="07738-117">Части</span><span class="sxs-lookup"><span data-stu-id="07738-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="07738-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-118">Required.</span></span> <span data-ttu-id="07738-119">Объект `Boolean` значение, представляющее результат сравнения.</span><span class="sxs-lookup"><span data-stu-id="07738-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="07738-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-120">Required.</span></span> <span data-ttu-id="07738-121">Любое выражение.</span><span class="sxs-lookup"><span data-stu-id="07738-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="07738-122">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-122">Required.</span></span> <span data-ttu-id="07738-123">Любой оператор сравнения отношений.</span><span class="sxs-lookup"><span data-stu-id="07738-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="07738-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="07738-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="07738-125">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-125">Required.</span></span> <span data-ttu-id="07738-126">Имя любого ссылочного объекта.</span><span class="sxs-lookup"><span data-stu-id="07738-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="07738-127">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-127">Required.</span></span> <span data-ttu-id="07738-128">Произвольное выражение `String` .</span><span class="sxs-lookup"><span data-stu-id="07738-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="07738-129">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="07738-129">Required.</span></span> <span data-ttu-id="07738-130">Любой `String` выражение или диапазона символов.</span><span class="sxs-lookup"><span data-stu-id="07738-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07738-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="07738-131">Remarks</span></span>  
 <span data-ttu-id="07738-132">Следующая таблица содержит список операторов сравнения и условий, определяющих ли `result` — `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="07738-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="07738-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="07738-133">Operator</span></span>|<span data-ttu-id="07738-134">`True`, если</span><span class="sxs-lookup"><span data-stu-id="07738-134">`True` if</span></span>|<span data-ttu-id="07738-135">`False`, если</span><span class="sxs-lookup"><span data-stu-id="07738-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="07738-136">`<` (Меньше)</span><span class="sxs-lookup"><span data-stu-id="07738-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="07738-137">`<=` (Меньше или равно)</span><span class="sxs-lookup"><span data-stu-id="07738-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="07738-138">`>` (Больше)</span><span class="sxs-lookup"><span data-stu-id="07738-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="07738-139">`>=` (Больше или равно)</span><span class="sxs-lookup"><span data-stu-id="07738-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="07738-140">`=` (Равно)</span><span class="sxs-lookup"><span data-stu-id="07738-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="07738-141">`<>` (Не равно)</span><span class="sxs-lookup"><span data-stu-id="07738-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="07738-142">[=-Оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) также используется как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="07738-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="07738-143">`Is` Оператор, `IsNot` оператор и `Like` оператор имеют особые функциональные возможности сравнения, которые отличаются от операторы, перечисленные в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="07738-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="07738-144">Сравнение чисел</span><span class="sxs-lookup"><span data-stu-id="07738-144">Comparing Numbers</span></span>  
 <span data-ttu-id="07738-145">При сравнении выражения типа `Single` к одному из типов `Double`, `Single` будет преобразовано в `Double`.</span><span class="sxs-lookup"><span data-stu-id="07738-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="07738-146">Это отличие поведению в Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="07738-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="07738-147">Аналогично, при сравнении выражения типа `Decimal` к выражению типа `Single` или `Double`, `Decimal` будет преобразовано в `Single` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="07738-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="07738-148">Для `Decimal` выражения, дробное значение меньше 1E-28 могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="07738-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="07738-149">Такая потеря дробного значения может привести к два значения сравниваются как равные, если они не.</span><span class="sxs-lookup"><span data-stu-id="07738-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="07738-150">По этой причине следует проявлять осторожность при использовании проверки на равенство (`=`) для сравнения двух переменных с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="07738-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="07738-151">Безопаснее проверить, является ли меньшим, чем небольшой приемлемый допуск абсолютное значение разницы между двумя числами.</span><span class="sxs-lookup"><span data-stu-id="07738-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="07738-152">С плавающей запятой неточности</span><span class="sxs-lookup"><span data-stu-id="07738-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="07738-153">При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="07738-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="07738-154">Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и [оператор Mod](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="07738-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="07738-155">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="07738-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="07738-156">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="07738-156">Comparing Strings</span></span>  
 <span data-ttu-id="07738-157">При сравнении строк строковые выражения вычисляются в алфавитном порядке сортировки, который зависит от `Option Compare` параметр.</span><span class="sxs-lookup"><span data-stu-id="07738-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="07738-158">`Option Compare Binary` базовые типы операции сравнения строк на основе порядка сортировки, производного от внутренних двоичных представлений символов.</span><span class="sxs-lookup"><span data-stu-id="07738-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="07738-159">Порядок сортировки определяется кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="07738-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="07738-160">В следующем примере показано двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="07738-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="07738-161">`Option Compare Text` базовые типы операции сравнения строк на порядок сортировки без учета регистра, специфичный определяется языкового стандарта приложения.</span><span class="sxs-lookup"><span data-stu-id="07738-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="07738-162">При задании `Option Compare Text` и сортировку символов в предыдущем примере, применяется следующий порядок сортировки текста:</span><span class="sxs-lookup"><span data-stu-id="07738-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="07738-163">Зависят от языкового стандарта</span><span class="sxs-lookup"><span data-stu-id="07738-163">Locale Dependence</span></span>  
 <span data-ttu-id="07738-164">При задании `Option Compare Text`, результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="07738-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="07738-165">Два символа могут считаться равными, в разных национальных настройках, а в другом.</span><span class="sxs-lookup"><span data-stu-id="07738-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="07738-166">Если вы используете сравнения строк для важных решений, например следует ли принять попытку входа в систему, можно чувствительность к языковым стандартам.</span><span class="sxs-lookup"><span data-stu-id="07738-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="07738-167">Рассмотрите возможность либо присвоив `Option Compare Binary` или вызывающей <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, который учитывает языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="07738-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="07738-168">Программирование с операторами сравнения</span><span class="sxs-lookup"><span data-stu-id="07738-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="07738-169">Использование операторов сравнения отношений с `Object` выражения не допускается в группе `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="07738-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="07738-170">При `Option Strict` — `Off`и либо `expression1` или `expression2` является `Object` выражения, типов во время выполнения определить, как выполняется сравнение.</span><span class="sxs-lookup"><span data-stu-id="07738-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="07738-171">Следующая таблица показывает сравнение выражений и результат сравнения в зависимости от типа среды выполнения из операндов.</span><span class="sxs-lookup"><span data-stu-id="07738-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="07738-172">Если операнды имеют</span><span class="sxs-lookup"><span data-stu-id="07738-172">If operands are</span></span>|<span data-ttu-id="07738-173">Сравнение выполняется</span><span class="sxs-lookup"><span data-stu-id="07738-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="07738-174">Оба `String`</span><span class="sxs-lookup"><span data-stu-id="07738-174">Both `String`</span></span>|<span data-ttu-id="07738-175">Сравнение сортировки, основанное на характеристиках сортировки строк.</span><span class="sxs-lookup"><span data-stu-id="07738-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="07738-176">Числовые</span><span class="sxs-lookup"><span data-stu-id="07738-176">Both numeric</span></span>|<span data-ttu-id="07738-177">Объекты преобразуются `Double`, числовое сравнение объектов.</span><span class="sxs-lookup"><span data-stu-id="07738-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="07738-178">Один числовой и один `String`</span><span class="sxs-lookup"><span data-stu-id="07738-178">One numeric and one `String`</span></span>|<span data-ttu-id="07738-179">`String` Преобразуется в `Double` и выполняется числовое сравнение.</span><span class="sxs-lookup"><span data-stu-id="07738-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="07738-180">Если `String` невозможно преобразовать в `Double`, <xref:System.InvalidCastException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="07738-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="07738-181">Одно или оба являются ссылочными типами, отличное от `String`</span><span class="sxs-lookup"><span data-stu-id="07738-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="07738-182">Возникает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="07738-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="07738-183">Числовое сравнение обрабатывает `Nothing` как 0.</span><span class="sxs-lookup"><span data-stu-id="07738-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="07738-184">Строковое сравнение рассматривает `Nothing` как `""` (пустая строка).</span><span class="sxs-lookup"><span data-stu-id="07738-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="07738-185">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="07738-185">Overloading</span></span>  
 <span data-ttu-id="07738-186">Операторы сравнения (`<`.</span><span class="sxs-lookup"><span data-stu-id="07738-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="07738-187">`<=``>`, `>=`, `=`, `<>`) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="07738-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="07738-188">Если код использует эти операторы для класса или структуры, убедитесь, что переопределенное.</span><span class="sxs-lookup"><span data-stu-id="07738-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="07738-189">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="07738-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="07738-190">Обратите внимание, что [=-оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) может быть перегружен только как оператор сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="07738-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07738-191">Пример</span><span class="sxs-lookup"><span data-stu-id="07738-191">Example</span></span>  
 <span data-ttu-id="07738-192">В следующем примере показаны различные способы использования операторов сравнения, используемые для сравнения выражений.</span><span class="sxs-lookup"><span data-stu-id="07738-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="07738-193">Операторы сравнения возвращают `Boolean` результат, представляет ли указанное выражение, результатом которого является `True`.</span><span class="sxs-lookup"><span data-stu-id="07738-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="07738-194">При применении `>` и `<` операторы в строки, будет выполнено сравнение с использованием обычной алфавитной сортировки строк.</span><span class="sxs-lookup"><span data-stu-id="07738-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="07738-195">Этот порядок может зависеть от настроек языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="07738-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="07738-196">Зависит ли порядок сортировки учитывает регистр, или не [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) параметр.</span><span class="sxs-lookup"><span data-stu-id="07738-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 <span data-ttu-id="07738-197">В приведенном выше примере первое сравнение возвращает `False` и вернуть оставшиеся сравнения `True`.</span><span class="sxs-lookup"><span data-stu-id="07738-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07738-198">См. также</span><span class="sxs-lookup"><span data-stu-id="07738-198">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="07738-199">Оператор =</span><span class="sxs-lookup"><span data-stu-id="07738-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="07738-200">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07738-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="07738-201">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="07738-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="07738-202">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="07738-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="07738-203">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07738-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
