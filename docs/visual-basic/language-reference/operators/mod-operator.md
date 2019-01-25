---
title: Оператор Mod (Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: d74e1f7aaaa22d68c49f4e40ca557511a48e0554
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525031"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="10bab-102">Оператор Mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10bab-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="10bab-103">Делит два числа и возвращает только остаток.</span><span class="sxs-lookup"><span data-stu-id="10bab-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10bab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10bab-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="10bab-105">Части</span><span class="sxs-lookup"><span data-stu-id="10bab-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="10bab-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="10bab-106">Required.</span></span> <span data-ttu-id="10bab-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="10bab-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="10bab-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="10bab-108">Required.</span></span> <span data-ttu-id="10bab-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="10bab-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="10bab-110">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="10bab-110">Supported types</span></span>  
 <span data-ttu-id="10bab-111">Все числовые типы.</span><span class="sxs-lookup"><span data-stu-id="10bab-111">All numeric types.</span></span> <span data-ttu-id="10bab-112">Сюда входят типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10bab-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="10bab-113">Результат</span><span class="sxs-lookup"><span data-stu-id="10bab-113">Result</span></span>

<span data-ttu-id="10bab-114">Результатом является остаток `number1` делится `number2`.</span><span class="sxs-lookup"><span data-stu-id="10bab-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="10bab-115">Например, выражение `14 Mod 4` равно 2.</span><span class="sxs-lookup"><span data-stu-id="10bab-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="10bab-116">Есть разница между *остаток* и *модуля* в математике дает различные результаты для отрицательных чисел.</span><span class="sxs-lookup"><span data-stu-id="10bab-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="10bab-117">`Mod` Оператор в Visual Basic .NET Framework `op_Modulus` оператор и базовым [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) инструкции IL, все операции остатка.</span><span class="sxs-lookup"><span data-stu-id="10bab-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="10bab-118">Результат `Mod` операция сохраняет со знаком делимого, `number1`, и поэтому он может быть положительным или отрицательным.</span><span class="sxs-lookup"><span data-stu-id="10bab-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="10bab-119">Результат всегда находится в диапазоне (-`number2`, `number2`), монопольная.</span><span class="sxs-lookup"><span data-stu-id="10bab-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="10bab-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="10bab-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="10bab-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="10bab-121">Remarks</span></span>  
 <span data-ttu-id="10bab-122">Если параметр `number1` или `number2` — это значение с плавающей запятой с плавающей запятой остаток от деления возвращается.</span><span class="sxs-lookup"><span data-stu-id="10bab-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="10bab-123">Тип данных результата — это наименьший тип данных, который может содержать все возможные значения, возникающие в результате деления с типами данных `number1` и `number2`.</span><span class="sxs-lookup"><span data-stu-id="10bab-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="10bab-124">Если `number1` или `number2` принимает значение [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.</span><span class="sxs-lookup"><span data-stu-id="10bab-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="10bab-125">Связанные операторы включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="10bab-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="10bab-126">[\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное от деления.</span><span class="sxs-lookup"><span data-stu-id="10bab-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="10bab-127">Например, выражение `14 \ 4` равен 3.</span><span class="sxs-lookup"><span data-stu-id="10bab-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="10bab-128">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, включая остаток, как число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="10bab-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="10bab-129">Например, выражение `14 / 4` принимает значение 3.5.</span><span class="sxs-lookup"><span data-stu-id="10bab-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="10bab-130">Попытка деления на ноль</span><span class="sxs-lookup"><span data-stu-id="10bab-130">Attempted division by zero</span></span>  
 <span data-ttu-id="10bab-131">Если `number2` оказался равным нулю, поведение `Mod` оператора зависит от типа данных операндов.</span><span class="sxs-lookup"><span data-stu-id="10bab-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="10bab-132">Создает целочисленного деления <xref:System.DivideByZeroException> исключение.</span><span class="sxs-lookup"><span data-stu-id="10bab-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="10bab-133">Возвращает деления с плавающей запятой <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="10bab-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="10bab-134">Аналогичной формулы</span><span class="sxs-lookup"><span data-stu-id="10bab-134">Equivalent formula</span></span>  
 <span data-ttu-id="10bab-135">Выражение `a Mod b` является эквивалентом для любой из следующих формул:</span><span class="sxs-lookup"><span data-stu-id="10bab-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="10bab-136">С плавающей запятой неточности</span><span class="sxs-lookup"><span data-stu-id="10bab-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="10bab-137">При работе с числами с плавающей запятой, помните, что они не всегда имеют точное десятичное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="10bab-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="10bab-138">Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и `Mod` оператор.</span><span class="sxs-lookup"><span data-stu-id="10bab-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="10bab-139">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="10bab-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="10bab-140">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="10bab-140">Overloading</span></span>  
 <span data-ttu-id="10bab-141">`Mod` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение.</span><span class="sxs-lookup"><span data-stu-id="10bab-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="10bab-142">Если код применяет `Mod` к экземпляру класса или структуры, которая включает в себя такие перегрузки, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="10bab-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="10bab-143">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="10bab-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10bab-144">Пример</span><span class="sxs-lookup"><span data-stu-id="10bab-144">Example</span></span>  
 <span data-ttu-id="10bab-145">В следующем примере используется `Mod` оператор деления двух чисел и возвращает только остаток.</span><span class="sxs-lookup"><span data-stu-id="10bab-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="10bab-146">Если оба числа число с плавающей запятой, результатом является числом с плавающей запятой, представляющее остаток.</span><span class="sxs-lookup"><span data-stu-id="10bab-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="10bab-147">Пример</span><span class="sxs-lookup"><span data-stu-id="10bab-147">Example</span></span>  
 <span data-ttu-id="10bab-148">В следующем примере показано возможная неточность операндов с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="10bab-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="10bab-149">В первой инструкции, операнды имеют `Double`, и 0,2 является периодической бесконечной двоичной дробью, сохраненное значение 0,20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="10bab-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="10bab-150">Во втором операторе символа типа литерала `D` приводит оба операнда для `Decimal`, и 0,2 имеет точное представление.</span><span class="sxs-lookup"><span data-stu-id="10bab-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="10bab-151">См. также</span><span class="sxs-lookup"><span data-stu-id="10bab-151">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="10bab-152">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="10bab-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="10bab-153">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="10bab-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="10bab-154">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="10bab-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="10bab-155">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="10bab-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="10bab-156">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="10bab-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="10bab-157">\ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10bab-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
