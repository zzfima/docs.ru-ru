---
title: '- Operator (Visual Basic)'
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
ms.openlocfilehash: 8526f632b7e54c03bd16c3af70375179cd7cf277
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724477"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="75b16-102">Оператор - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75b16-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="75b16-103">Возвращает разность двух числовых выражений или отрицательное значение числового выражения.</span><span class="sxs-lookup"><span data-stu-id="75b16-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75b16-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="75b16-105">Части</span><span class="sxs-lookup"><span data-stu-id="75b16-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="75b16-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="75b16-106">Required.</span></span> <span data-ttu-id="75b16-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="75b16-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="75b16-108">Требуется, если `–` оператор вычисляет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="75b16-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="75b16-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="75b16-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="75b16-110">Результат</span><span class="sxs-lookup"><span data-stu-id="75b16-110">Result</span></span>  
 <span data-ttu-id="75b16-111">Результат отличается от `expression1` и `expression2`, или отрицательное значение `expression1`.</span><span class="sxs-lookup"><span data-stu-id="75b16-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="75b16-112">Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="75b16-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="75b16-113">См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="75b16-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="75b16-114">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="75b16-114">Supported Types</span></span>  
 <span data-ttu-id="75b16-115">Все числовые типы.</span><span class="sxs-lookup"><span data-stu-id="75b16-115">All numeric types.</span></span> <span data-ttu-id="75b16-116">Сюда входят типы без знака и с плавающей запятой и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="75b16-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75b16-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="75b16-117">Remarks</span></span>  
 <span data-ttu-id="75b16-118">При первом использовании показано в приведенном примере `–` оператор *двоичных* оператор арифметического вычитания для разницы между двумя числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="75b16-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="75b16-119">При использовании второго в синтаксис, показанный ранее `–` оператор *унарный* оператор отрицания отрицательного значения выражения.</span><span class="sxs-lookup"><span data-stu-id="75b16-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="75b16-120">В этом смысле отрицание представляет собой замену знака `expression1` , чтобы результат будет положительным Если `expression1` является отрицательным.</span><span class="sxs-lookup"><span data-stu-id="75b16-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="75b16-121">Если любое из выражений, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), `–` оператор воспринимает его как ноль.</span><span class="sxs-lookup"><span data-stu-id="75b16-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75b16-122">`–` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="75b16-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="75b16-123">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его.</span><span class="sxs-lookup"><span data-stu-id="75b16-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="75b16-124">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="75b16-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75b16-125">Пример</span><span class="sxs-lookup"><span data-stu-id="75b16-125">Example</span></span>  
 <span data-ttu-id="75b16-126">В следующем примере используется `–` оператор вычисляет и возвращает разность двух чисел, а затем меняет знак числа.</span><span class="sxs-lookup"><span data-stu-id="75b16-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="75b16-127">После выполнения этих инструкций `binaryResult` содержит значение 124,45 и `unaryResult` содержит значение – 334,90.</span><span class="sxs-lookup"><span data-stu-id="75b16-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b16-128">См. также</span><span class="sxs-lookup"><span data-stu-id="75b16-128">See also</span></span>
- [<span data-ttu-id="75b16-129">-= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75b16-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="75b16-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="75b16-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="75b16-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75b16-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="75b16-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="75b16-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="75b16-133">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75b16-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
