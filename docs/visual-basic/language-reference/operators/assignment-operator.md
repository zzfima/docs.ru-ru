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
ms.openlocfilehash: ca4c519dd80c07f54dc1c3dfe70daf6948446363
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591843"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a416e-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a416e-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="a416e-103">Присваивает значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="a416e-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a416e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a416e-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="a416e-105">Части</span><span class="sxs-lookup"><span data-stu-id="a416e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a416e-106">Любая изменяемая переменная или любое свойство.</span><span class="sxs-lookup"><span data-stu-id="a416e-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="a416e-107">Любой литерал, константа или выражение.</span><span class="sxs-lookup"><span data-stu-id="a416e-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a416e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a416e-108">Remarks</span></span>  
 <span data-ttu-id="a416e-109">Элемент в левой части знака равенства (`=`) может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="a416e-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a416e-110">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a416e-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="a416e-111">Оператор `=` присваивает значение справа переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="a416e-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a416e-112">Оператор `=` также используется в качестве оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="a416e-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="a416e-113">Дополнительные сведения см. в разделе [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a416e-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a416e-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="a416e-114">Overloading</span></span>  
 <span data-ttu-id="a416e-115">Оператор `=` можно перегрузить только как оператор реляционного сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="a416e-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="a416e-116">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a416e-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a416e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="a416e-117">Example</span></span>  
 <span data-ttu-id="a416e-118">В следующем примере показан оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="a416e-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="a416e-119">Значение справа присваивается переменной слева.</span><span class="sxs-lookup"><span data-stu-id="a416e-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a416e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a416e-120">See also</span></span>

- [<span data-ttu-id="a416e-121">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="a416e-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="a416e-122">Оператор \*=</span><span class="sxs-lookup"><span data-stu-id="a416e-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="a416e-123">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="a416e-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="a416e-124">Оператор-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a416e-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="a416e-125">Оператор/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a416e-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="a416e-126">\\ = оператор</span><span class="sxs-lookup"><span data-stu-id="a416e-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="a416e-127">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="a416e-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="a416e-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="a416e-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="a416e-129">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="a416e-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="a416e-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a416e-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="a416e-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="a416e-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
