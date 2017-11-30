---
title: "Оператор / (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f221e863725b9aeb0b3fa3219b3a881541e2be0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d9c7a-102">Оператор / (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="d9c7a-103">Делит два числа и возвращает результат с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9c7a-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="d9c7a-105">Части</span><span class="sxs-lookup"><span data-stu-id="d9c7a-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="d9c7a-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-106">Required.</span></span> <span data-ttu-id="d9c7a-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d9c7a-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-108">Required.</span></span> <span data-ttu-id="d9c7a-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="d9c7a-110">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="d9c7a-110">Supported Types</span></span>  
 <span data-ttu-id="d9c7a-111">Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="d9c7a-112">Результат</span><span class="sxs-lookup"><span data-stu-id="d9c7a-112">Result</span></span>  
 <span data-ttu-id="d9c7a-113">Результатом является полное частное от деления `expression1` деленная `expression2`, включая остаток.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="d9c7a-114">[\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное, без остатка.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9c7a-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9c7a-115">Remarks</span></span>  
 <span data-ttu-id="d9c7a-116">Тип данных результата зависит от типов операндов.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="d9c7a-117">Следующая таблица показывает, как определяется тип данных результата.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="d9c7a-118">Типы данных операндов</span><span class="sxs-lookup"><span data-stu-id="d9c7a-118">Operand data types</span></span>|<span data-ttu-id="d9c7a-119">Тип данных результата</span><span class="sxs-lookup"><span data-stu-id="d9c7a-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="d9c7a-120">Оба выражения имеют целочисленные типы данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [длинные](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="d9c7a-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="d9c7a-121">Одно выражение является [один](../../../visual-basic/language-reference/data-types/single-data-type.md) тип данных, а другой — не [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="d9c7a-122">Одно выражение является [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) тип данных, а другой — не [один](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="d9c7a-123">Одно из выражений имеет [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) тип данных</span><span class="sxs-lookup"><span data-stu-id="d9c7a-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="d9c7a-124">Перед выполнением деления все целочисленные числовые выражения преобразуются в тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="d9c7a-125">Если вы назначаете результат целочисленный тип данных, Visual Basic пытается преобразовать результат из `Double` к этому типу.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="d9c7a-126">Это может вызвать исключение, если результат не умещается в этом типе.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="d9c7a-127">В частности в разделе «Попытка деления на ноль» на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="d9c7a-128">Если `expression1` или `expression2` равен [ничего](../../../visual-basic/language-reference/nothing.md), интерпретируется как ноль.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="d9c7a-129">Попытка деления на ноль</span><span class="sxs-lookup"><span data-stu-id="d9c7a-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="d9c7a-130">Если `expression2` равняется нулю, `/` оператор различается для разных типов данных операнда.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="d9c7a-131">В следующей таблице показаны возможные результаты.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="d9c7a-132">Типы данных операндов</span><span class="sxs-lookup"><span data-stu-id="d9c7a-132">Operand data types</span></span>|<span data-ttu-id="d9c7a-133">Поведение при `expression2` равно нулю</span><span class="sxs-lookup"><span data-stu-id="d9c7a-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="d9c7a-134">С плавающей запятой (`Single` или `Double`)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="d9c7a-135">Возвращает бесконечность (<xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>), или <xref:System.Double.NaN> (не число) Если `expression1` также равно нулю</span><span class="sxs-lookup"><span data-stu-id="d9c7a-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="d9c7a-136">Создает исключение<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="d9c7a-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="d9c7a-137">Целочисленное (знаковое или без знака)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="d9c7a-138">Выполняется преобразование в целочисленный тип создает исключение <xref:System.OverflowException> , так как не может принимать целые типы <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, или<xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="d9c7a-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d9c7a-139">`/` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d9c7a-140">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d9c7a-141">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d9c7a-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9c7a-142">Пример</span><span class="sxs-lookup"><span data-stu-id="d9c7a-142">Example</span></span>  
 <span data-ttu-id="d9c7a-143">В этом примере используется `/` оператора для выполнения операции деления с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="d9c7a-144">Результатом является частное двух операндов.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 <span data-ttu-id="d9c7a-145">Выражения в предыдущем примере возвращают значения 2,5 и 3,333333.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="d9c7a-146">Обратите внимание, что результат всегда с плавающей запятой (`Double`), даже если оба операнда являются целочисленными константами.</span><span class="sxs-lookup"><span data-stu-id="d9c7a-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c7a-147">См. также</span><span class="sxs-lookup"><span data-stu-id="d9c7a-147">See Also</span></span>  
 [<span data-ttu-id="d9c7a-148">/ =-Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="d9c7a-149">\ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c7a-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="d9c7a-150">Типы данных результатов оператора</span><span class="sxs-lookup"><span data-stu-id="d9c7a-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [<span data-ttu-id="d9c7a-151">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="d9c7a-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="d9c7a-152">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9c7a-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="d9c7a-153">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d9c7a-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="d9c7a-154">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9c7a-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
