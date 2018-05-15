---
title: '- Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 4df8eb3844ed20fd24ca375f77cea46b9c6cee37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="e67a2-102">Оператор - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e67a2-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="e67a2-103">Возвращает разность двух числовых выражений или отрицательное значение числового выражения.</span><span class="sxs-lookup"><span data-stu-id="e67a2-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67a2-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="e67a2-105">Части</span><span class="sxs-lookup"><span data-stu-id="e67a2-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="e67a2-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e67a2-106">Required.</span></span> <span data-ttu-id="e67a2-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="e67a2-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e67a2-108">Требуется, если `–` оператор вычисляет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="e67a2-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="e67a2-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="e67a2-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="e67a2-110">Результат</span><span class="sxs-lookup"><span data-stu-id="e67a2-110">Result</span></span>  
 <span data-ttu-id="e67a2-111">Результат отличается от `expression1` и `expression2`, или инвертированное значение `expression1`.</span><span class="sxs-lookup"><span data-stu-id="e67a2-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="e67a2-112">Тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="e67a2-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="e67a2-113">В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="e67a2-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e67a2-114">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="e67a2-114">Supported Types</span></span>  
 <span data-ttu-id="e67a2-115">Все числовые типы.</span><span class="sxs-lookup"><span data-stu-id="e67a2-115">All numeric types.</span></span> <span data-ttu-id="e67a2-116">Сюда входят типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e67a2-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e67a2-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="e67a2-117">Remarks</span></span>  
 <span data-ttu-id="e67a2-118">При первом использовании показано в приведенном примере `–` оператор *двоичных* оператор арифметического вычитания для нахождения разности двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="e67a2-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="e67a2-119">При втором использовании показано в приведенном примере `–` оператор *унарный* оператор отрицания отрицательного значения выражения.</span><span class="sxs-lookup"><span data-stu-id="e67a2-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="e67a2-120">В этом смысле отрицание представляет собой замену знака `expression1` , чтобы результат будет положительным Если `expression1` является отрицательным значением.</span><span class="sxs-lookup"><span data-stu-id="e67a2-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="e67a2-121">Если какое-нибудь выражение, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), `–` оператор воспринимает его как ноль.</span><span class="sxs-lookup"><span data-stu-id="e67a2-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e67a2-122">`–` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="e67a2-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e67a2-123">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его.</span><span class="sxs-lookup"><span data-stu-id="e67a2-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="e67a2-124">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e67a2-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e67a2-125">Пример</span><span class="sxs-lookup"><span data-stu-id="e67a2-125">Example</span></span>  
 <span data-ttu-id="e67a2-126">В следующем примере используется `–` оператор вычисляет и возвращает разность двух чисел, а затем меняет знак числа.</span><span class="sxs-lookup"><span data-stu-id="e67a2-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="e67a2-127">После выполнения этих инструкций `binaryResult` содержит значение 124,45 и `unaryResult` содержит значение – 334,90.</span><span class="sxs-lookup"><span data-stu-id="e67a2-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67a2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e67a2-128">See Also</span></span>  
 <span data-ttu-id="e67a2-129">[-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="e67a2-129">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span></span>  
 [<span data-ttu-id="e67a2-130">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e67a2-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="e67a2-131">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="e67a2-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="e67a2-132">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e67a2-132">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
