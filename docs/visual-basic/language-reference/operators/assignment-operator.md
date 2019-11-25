---
title: Оператор =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350204"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3d1bf-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d1bf-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="3d1bf-103">Assigns a value to a variable or property.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d1bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d1bf-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="3d1bf-105">Части</span><span class="sxs-lookup"><span data-stu-id="3d1bf-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3d1bf-106">Any writable variable or any property.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="3d1bf-107">Any literal, constant, or expression.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d1bf-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="3d1bf-108">Remarks</span></span>  
 <span data-ttu-id="3d1bf-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3d1bf-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3d1bf-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="3d1bf-111">The `=` operator assigns the value on its right to the variable or property on its left.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d1bf-112">The `=` operator is also used as a comparison operator.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="3d1bf-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3d1bf-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3d1bf-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="3d1bf-114">Overloading</span></span>  
 <span data-ttu-id="3d1bf-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="3d1bf-116">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3d1bf-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d1bf-117">Пример</span><span class="sxs-lookup"><span data-stu-id="3d1bf-117">Example</span></span>  
 <span data-ttu-id="3d1bf-118">The following example demonstrates the assignment operator.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="3d1bf-119">The value on the right is assigned to the variable on the left.</span><span class="sxs-lookup"><span data-stu-id="3d1bf-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3d1bf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3d1bf-120">See also</span></span>

- [<span data-ttu-id="3d1bf-121">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="3d1bf-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="3d1bf-122">Оператор \*=</span><span class="sxs-lookup"><span data-stu-id="3d1bf-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="3d1bf-123">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="3d1bf-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="3d1bf-124">-= Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d1bf-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="3d1bf-125">/= Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d1bf-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="3d1bf-126">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="3d1bf-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="3d1bf-127">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="3d1bf-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="3d1bf-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="3d1bf-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="3d1bf-129">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="3d1bf-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="3d1bf-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3d1bf-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="3d1bf-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="3d1bf-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
