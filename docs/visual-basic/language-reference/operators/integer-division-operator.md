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
ms.openlocfilehash: 276071fef3632d1a617f177b6fe18026b290103a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917240"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b6f5a-102">Оператор \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f5a-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="b6f5a-103">Делит два числа и возвращает целочисленный результат.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6f5a-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="b6f5a-105">Части</span><span class="sxs-lookup"><span data-stu-id="b6f5a-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="b6f5a-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-106">Required.</span></span> <span data-ttu-id="b6f5a-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="b6f5a-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-108">Required.</span></span> <span data-ttu-id="b6f5a-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="b6f5a-110">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="b6f5a-110">Supported Types</span></span>  
 <span data-ttu-id="b6f5a-111">Все числовые типы, включая неподписанные и типы с плавающей запятой `Decimal`, и.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="b6f5a-112">Результат</span><span class="sxs-lookup"><span data-stu-id="b6f5a-112">Result</span></span>  
 <span data-ttu-id="b6f5a-113">Результатом является целочисленное частное `expression1` `expression2`деление на, которое отклоняет остаток и оставляет только целую часть.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="b6f5a-114">Это называется усечением.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="b6f5a-115">Тип данных result является числовым типом, подходящим для типов `expression1` данных и. `expression2`</span><span class="sxs-lookup"><span data-stu-id="b6f5a-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="b6f5a-116">См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5a-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="b6f5a-117">[Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, сохраняющее остаток в дробной части.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6f5a-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6f5a-118">Remarks</span></span>  
 <span data-ttu-id="b6f5a-119">Перед выполнением деления Visual Basic пытается преобразовать любое числовое выражение с плавающей запятой `Long`в.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="b6f5a-120">Если `Option Strict` имеет `On`значение, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="b6f5a-121">Если `Option Strict` параметр `Off`имеет значение <xref:System.OverflowException> , то возможно, если значения выходят за пределы диапазона [данных типа Long](../../../visual-basic/language-reference/data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5a-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="b6f5a-122">Преобразование в `Long` также регулируется округлением *банка*.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="b6f5a-123">Дополнительные сведения см. в разделе "Дробные части" [функций преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5a-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="b6f5a-124">Если `expression1` или`expression2` имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно считается нулевым.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="b6f5a-125">Попыток деления на ноль</span><span class="sxs-lookup"><span data-stu-id="b6f5a-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="b6f5a-126">Если `expression2` значение равно нулю `\` , оператор выдает <xref:System.DivideByZeroException> исключение.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="b6f5a-127">Это справедливо для всех числовых типов данных операндов.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6f5a-128">Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `\`</span><span class="sxs-lookup"><span data-stu-id="b6f5a-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b6f5a-129">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b6f5a-130">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5a-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6f5a-131">Пример</span><span class="sxs-lookup"><span data-stu-id="b6f5a-131">Example</span></span>  
 <span data-ttu-id="b6f5a-132">В следующем примере `\` оператор используется для выполнения целочисленного деления.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="b6f5a-133">Результатом является целое число, представляющее целочисленное частное двух операндов с отброшенным остатком.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="b6f5a-134">Выражения в предыдущем примере возвращают значения 2, 3, 33 и-22 соответственно.</span><span class="sxs-lookup"><span data-stu-id="b6f5a-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f5a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b6f5a-135">See also</span></span>

- [<span data-ttu-id="b6f5a-136">\\Оператор =</span><span class="sxs-lookup"><span data-stu-id="b6f5a-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="b6f5a-137">Оператор/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f5a-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="b6f5a-138">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="b6f5a-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="b6f5a-139">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="b6f5a-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="b6f5a-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6f5a-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b6f5a-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="b6f5a-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b6f5a-142">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6f5a-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
