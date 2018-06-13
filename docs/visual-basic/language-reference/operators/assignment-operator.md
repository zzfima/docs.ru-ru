---
title: Оператор = (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603604"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4037b-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4037b-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="4037b-103">Присваивает значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="4037b-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4037b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4037b-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="4037b-105">Части</span><span class="sxs-lookup"><span data-stu-id="4037b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4037b-106">Любой доступный для записи переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="4037b-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="4037b-107">Любой литерал, константу или выражение.</span><span class="sxs-lookup"><span data-stu-id="4037b-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4037b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4037b-108">Remarks</span></span>  
 <span data-ttu-id="4037b-109">Элемент слева от знака равенства (`=`) может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="4037b-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4037b-110">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4037b-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="4037b-111">`=` Оператор присваивает значение справа переменной или свойству слева от него.</span><span class="sxs-lookup"><span data-stu-id="4037b-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4037b-112">`=` Оператор также используется в качестве оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="4037b-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="4037b-113">Дополнительные сведения см. в разделе [операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="4037b-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4037b-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="4037b-114">Overloading</span></span>  
 <span data-ttu-id="4037b-115">`=` Оператор может быть перегружен только как оператор сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="4037b-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="4037b-116">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4037b-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4037b-117">Пример</span><span class="sxs-lookup"><span data-stu-id="4037b-117">Example</span></span>  
 <span data-ttu-id="4037b-118">Ниже приведен пример оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="4037b-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="4037b-119">Присваивается значение справа переменной слева.</span><span class="sxs-lookup"><span data-stu-id="4037b-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4037b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4037b-120">See Also</span></span>  
 [<span data-ttu-id="4037b-121">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="4037b-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="4037b-122">Оператор \*=</span><span class="sxs-lookup"><span data-stu-id="4037b-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="4037b-123">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="4037b-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="4037b-124">-= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4037b-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="4037b-125">/ =-Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4037b-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="4037b-126">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="4037b-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="4037b-127">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="4037b-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="4037b-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="4037b-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="4037b-129">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="4037b-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="4037b-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="4037b-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="4037b-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="4037b-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
