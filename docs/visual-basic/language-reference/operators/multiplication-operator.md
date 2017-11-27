---
title: "* Оператор (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 450d728e44ef5639d75369e05b47cb3009b4d769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4c5c3-102">Оператор * (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c5c3-102">* Operator (Visual Basic)</span></span>
<span data-ttu-id="4c5c3-103">Выполняет умножение двух чисел.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c5c3-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="4c5c3-105">Части</span><span class="sxs-lookup"><span data-stu-id="4c5c3-105">Parts</span></span>  
  
|<span data-ttu-id="4c5c3-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4c5c3-106">Term</span></span>|<span data-ttu-id="4c5c3-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4c5c3-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="4c5c3-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-108">Required.</span></span> <span data-ttu-id="4c5c3-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="4c5c3-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-110">Required.</span></span> <span data-ttu-id="4c5c3-111">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="4c5c3-112">Результат</span><span class="sxs-lookup"><span data-stu-id="4c5c3-112">Result</span></span>  
 <span data-ttu-id="4c5c3-113">Результат — это совокупность `number1` и `number2`.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="4c5c3-114">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="4c5c3-114">Supported Types</span></span>  
 <span data-ttu-id="4c5c3-115">Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c5c3-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c5c3-116">Remarks</span></span>  
 <span data-ttu-id="4c5c3-117">Тип данных результата зависит от типов операндов.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="4c5c3-118">Следующая таблица показывает, как определяется тип данных результата.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="4c5c3-119">Типы данных операндов</span><span class="sxs-lookup"><span data-stu-id="4c5c3-119">Operand data types</span></span>|<span data-ttu-id="4c5c3-120">Тип данных результата</span><span class="sxs-lookup"><span data-stu-id="4c5c3-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="4c5c3-121">Оба выражения имеют целочисленные типы данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [длинные](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="4c5c3-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="4c5c3-122">Числовой тип данных для типов данных `number1` и `number2`.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="4c5c3-123">В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4c5c3-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="4c5c3-124">Оба выражения имеют [десятичное число](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="4c5c3-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="4c5c3-125">Оба выражения имеют [один](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="4c5c3-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="4c5c3-126">Любое из выражений имеет тип данных с плавающей запятой (`Single` или [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md)), но не оба `Single` (Примечание `Decimal` не является типом данных с плавающей запятой)</span><span class="sxs-lookup"><span data-stu-id="4c5c3-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="4c5c3-127">Если результатом выражения [ничего](../../../visual-basic/language-reference/nothing.md), интерпретируется как ноль.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4c5c3-128">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="4c5c3-128">Overloading</span></span>  
 <span data-ttu-id="4c5c3-129">`*` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4c5c3-130">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4c5c3-131">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4c5c3-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c5c3-132">Пример</span><span class="sxs-lookup"><span data-stu-id="4c5c3-132">Example</span></span>  
 <span data-ttu-id="4c5c3-133">В этом примере используется `*` оператор для умножения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="4c5c3-134">Результатом является произведение двух операндов.</span><span class="sxs-lookup"><span data-stu-id="4c5c3-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4c5c3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="4c5c3-135">See Also</span></span>  
 [<span data-ttu-id="4c5c3-136">Оператор *=</span><span class="sxs-lookup"><span data-stu-id="4c5c3-136">*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="4c5c3-137">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="4c5c3-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="4c5c3-138">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c5c3-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4c5c3-139">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="4c5c3-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4c5c3-140">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c5c3-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
