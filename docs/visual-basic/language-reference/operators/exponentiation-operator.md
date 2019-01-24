---
title: Оператор ^ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 2fb52a57a9d96f93c31ab1419e81e7f05967f831
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659726"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="01bad-102">Оператор ^ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01bad-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="01bad-103">Возводит число в степень другого числа.</span><span class="sxs-lookup"><span data-stu-id="01bad-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01bad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01bad-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="01bad-105">Части</span><span class="sxs-lookup"><span data-stu-id="01bad-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="01bad-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="01bad-106">Required.</span></span> <span data-ttu-id="01bad-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="01bad-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="01bad-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="01bad-108">Required.</span></span> <span data-ttu-id="01bad-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="01bad-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="01bad-110">Результат</span><span class="sxs-lookup"><span data-stu-id="01bad-110">Result</span></span>  
 <span data-ttu-id="01bad-111">В результате `number` степени `exponent`, всегда как `Double` значение.</span><span class="sxs-lookup"><span data-stu-id="01bad-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="01bad-112">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="01bad-112">Supported Types</span></span>  
 <span data-ttu-id="01bad-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="01bad-113">`Double`.</span></span> <span data-ttu-id="01bad-114">Операнды любого другого типа преобразуются в `Double`.</span><span class="sxs-lookup"><span data-stu-id="01bad-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01bad-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="01bad-115">Remarks</span></span>  
 <span data-ttu-id="01bad-116">Visual Basic всегда выполняет возведение в степень в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="01bad-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="01bad-117">Значение `exponent` может быть дробным, отрицательным или оба.</span><span class="sxs-lookup"><span data-stu-id="01bad-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="01bad-118">При выполнении нескольких возведения в степень в одном выражении, `^` оператор выполняется, в котором он слева направо.</span><span class="sxs-lookup"><span data-stu-id="01bad-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bad-119">`^` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="01bad-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="01bad-120">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="01bad-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="01bad-121">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="01bad-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01bad-122">Пример</span><span class="sxs-lookup"><span data-stu-id="01bad-122">Example</span></span>  
 <span data-ttu-id="01bad-123">В следующем примере используется `^` оператор для возведения числа в степень показатель степени.</span><span class="sxs-lookup"><span data-stu-id="01bad-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="01bad-124">Результатом является первый операнд, возведенный в степень второго.</span><span class="sxs-lookup"><span data-stu-id="01bad-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="01bad-125">В предыдущем примере получаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="01bad-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="01bad-126">`exp1` имеет значение 4 (2 в квадрате).</span><span class="sxs-lookup"><span data-stu-id="01bad-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="01bad-127">`exp2` имеет значение 19683 (3 в кубе, затем полученное значение в кубе).</span><span class="sxs-lookup"><span data-stu-id="01bad-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="01bad-128">`exp3` устанавливается в 125 (5 в кубе).</span><span class="sxs-lookup"><span data-stu-id="01bad-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="01bad-129">`exp4` имеет значение 625 (-5 в четвертой степени).</span><span class="sxs-lookup"><span data-stu-id="01bad-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="01bad-130">`exp5` имеет значение 2 (кубический корень из 8).</span><span class="sxs-lookup"><span data-stu-id="01bad-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="01bad-131">`exp6` имеет значение 0,5 (1.0, деленное на кубический корень из 8).</span><span class="sxs-lookup"><span data-stu-id="01bad-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="01bad-132">Обратите внимание на важность круглых скобок в выражениях в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="01bad-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="01bad-133">Из-за *порядок применения операторов*, Visual Basic обычно выполняет `^` оператор перед любыми другими, даже унарный `–` оператор.</span><span class="sxs-lookup"><span data-stu-id="01bad-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="01bad-134">Если `exp4` и `exp6` были рассчитаны без скобок, они имели бы следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="01bad-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="01bad-135">`exp4 = -5 ^ 4` будет рассчитываться следующим образом: (от 5 до четвертой степени), что может привести к-625.</span><span class="sxs-lookup"><span data-stu-id="01bad-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="01bad-136">`exp6 = 8 ^ -1.0 / 3.0` будет вычисляться как (8-1 или 0,125) делится 3.0, что привело бы равно 0,041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="01bad-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bad-137">См. также</span><span class="sxs-lookup"><span data-stu-id="01bad-137">See also</span></span>
- [<span data-ttu-id="01bad-138">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="01bad-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="01bad-139">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="01bad-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="01bad-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01bad-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="01bad-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="01bad-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="01bad-142">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01bad-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
