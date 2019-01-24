---
title: Оператор \ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: ac306038aefba4ca0e0f13fa2945d01c27c0804d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654689"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f7cfd-102">Оператор \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7cfd-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="f7cfd-103">Делит два числа и возвращает целочисленный результат.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cfd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7cfd-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f7cfd-105">Части</span><span class="sxs-lookup"><span data-stu-id="f7cfd-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="f7cfd-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-106">Required.</span></span> <span data-ttu-id="f7cfd-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f7cfd-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-108">Required.</span></span> <span data-ttu-id="f7cfd-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f7cfd-110">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="f7cfd-110">Supported Types</span></span>  
 <span data-ttu-id="f7cfd-111">Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="f7cfd-112">Результат</span><span class="sxs-lookup"><span data-stu-id="f7cfd-112">Result</span></span>  
 <span data-ttu-id="f7cfd-113">Результатом является целочисленное частное `expression1` деления на `expression2`, котором остаток отбрасывается и возвращается только целая часть результата.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="f7cfd-114">Этот процесс называется *усечение*.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="f7cfd-115">Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f7cfd-116">См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="f7cfd-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="f7cfd-117">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, в котором сохраняется остаток в дробной части.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7cfd-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7cfd-118">Remarks</span></span>  
 <span data-ttu-id="f7cfd-119">Перед выполнением деления, Visual Basic пытается преобразовать любое с плавающей запятой числовое выражение, чтобы `Long`.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="f7cfd-120">Если `Option Strict` является `On`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="f7cfd-121">Если `Option Strict` — `Off`, <xref:System.OverflowException> возможно в том случае, если значение находится вне диапазона [тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f7cfd-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="f7cfd-122">Преобразование в `Long` также является *банковское округление*.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="f7cfd-123">Дополнительные сведения см. в разделе «Дробных частей» в [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="f7cfd-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="f7cfd-124">Если `expression1` или `expression2` принимает значение [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="f7cfd-125">Попытка деления на ноль</span><span class="sxs-lookup"><span data-stu-id="f7cfd-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="f7cfd-126">Если `expression2` результатом которого является ноль, `\` вызывает оператор <xref:System.DivideByZeroException> исключение.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="f7cfd-127">Это справедливо для всех числовых типов данных операндов.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7cfd-128">`\` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f7cfd-129">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f7cfd-130">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f7cfd-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7cfd-131">Пример</span><span class="sxs-lookup"><span data-stu-id="f7cfd-131">Example</span></span>  
 <span data-ttu-id="f7cfd-132">В следующем примере используется `\` оператора для выполнения операции деления целое число.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="f7cfd-133">Результатом является целое число, представляющее целочисленное частное двух операндов, а остальное удаляются.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 <span data-ttu-id="f7cfd-134">Выражения в предыдущем примере возвращают значения 2, 3, 33 и -22 соответственно.</span><span class="sxs-lookup"><span data-stu-id="f7cfd-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7cfd-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f7cfd-135">See also</span></span>
- [<span data-ttu-id="f7cfd-136">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="f7cfd-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="f7cfd-137">/ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7cfd-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="f7cfd-138">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="f7cfd-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f7cfd-139">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="f7cfd-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f7cfd-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7cfd-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f7cfd-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f7cfd-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f7cfd-142">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7cfd-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
