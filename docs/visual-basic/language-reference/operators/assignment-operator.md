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
ms.openlocfilehash: ad74e3ebc947af4f36022be838b69df6ce24997a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608282"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="fc154-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc154-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="fc154-103">Присваивает значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="fc154-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc154-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc154-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="fc154-105">Части</span><span class="sxs-lookup"><span data-stu-id="fc154-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="fc154-106">Любой доступный для записи переменной или любого свойства.</span><span class="sxs-lookup"><span data-stu-id="fc154-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="fc154-107">Любой литерал, константу или выражение.</span><span class="sxs-lookup"><span data-stu-id="fc154-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc154-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc154-108">Remarks</span></span>  
 <span data-ttu-id="fc154-109">Элемент слева от знака равенства (`=`) может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="fc154-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="fc154-110">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="fc154-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="fc154-111">`=` Оператор присваивает значение справа переменной или свойства слева от него.</span><span class="sxs-lookup"><span data-stu-id="fc154-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc154-112">`=` Оператор также используется как оператор сравнения.</span><span class="sxs-lookup"><span data-stu-id="fc154-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="fc154-113">Дополнительные сведения см. в разделе [операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="fc154-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fc154-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="fc154-114">Overloading</span></span>  
 <span data-ttu-id="fc154-115">`=` Оператор может быть перегружен, только как оператор сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="fc154-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="fc154-116">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fc154-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc154-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fc154-117">Example</span></span>  
 <span data-ttu-id="fc154-118">Ниже приведен пример оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="fc154-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="fc154-119">Значение справа назначается переменной слева.</span><span class="sxs-lookup"><span data-stu-id="fc154-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="fc154-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fc154-120">See also</span></span>

- [<span data-ttu-id="fc154-121">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="fc154-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="fc154-122">Оператор \*=</span><span class="sxs-lookup"><span data-stu-id="fc154-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="fc154-123">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="fc154-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="fc154-124">-= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc154-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="fc154-125">/ =-Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc154-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="fc154-126">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="fc154-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="fc154-127">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="fc154-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="fc154-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="fc154-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="fc154-129">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="fc154-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="fc154-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="fc154-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="fc154-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="fc154-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
