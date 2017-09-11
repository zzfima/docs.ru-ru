---
title: "= Оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 46dc9e6018cf2ae71f1fc6dc2b8f19c2f0aadb62
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5469a-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5469a-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="5469a-103">Присваивает значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="5469a-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5469a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5469a-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="5469a-105">Части</span><span class="sxs-lookup"><span data-stu-id="5469a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5469a-106">Любой доступный для записи переменная или любое свойство.</span><span class="sxs-lookup"><span data-stu-id="5469a-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="5469a-107">Любой литерал, константа или выражение.</span><span class="sxs-lookup"><span data-stu-id="5469a-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5469a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5469a-108">Remarks</span></span>  
 <span data-ttu-id="5469a-109">Элемент слева от знака равенства (`=`) может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="5469a-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5469a-110">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5469a-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="5469a-111">`=` Оператор присваивает значение справа переменной или свойству, расположенному слева.</span><span class="sxs-lookup"><span data-stu-id="5469a-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5469a-112">`=` Оператор также используется как оператор сравнения.</span><span class="sxs-lookup"><span data-stu-id="5469a-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="5469a-113">Дополнительные сведения см. в разделе [операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5469a-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5469a-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="5469a-114">Overloading</span></span>  
 <span data-ttu-id="5469a-115">`=` Оператор может быть перегружен только как оператор сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="5469a-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="5469a-116">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5469a-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5469a-117">Пример</span><span class="sxs-lookup"><span data-stu-id="5469a-117">Example</span></span>  
 <span data-ttu-id="5469a-118">В следующем примере оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="5469a-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="5469a-119">Присваивается значение справа переменной слева.</span><span class="sxs-lookup"><span data-stu-id="5469a-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 <span data-ttu-id="5469a-120">[!code-vb[VbVbalrOperators №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5469a-120">[!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5469a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="5469a-121">See Also</span></span>  
 <span data-ttu-id="5469a-122">[& =-Оператор](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-122">[&= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-123"> [* =-Оператор](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-123"> [*= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-124"> [+= Оператор](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-124"> [+= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-125"> [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-125"> [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-126"> [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-126"> [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-127"> [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-127"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-128"> [^ =-Оператор](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-128"> [^= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span></span>  
<span data-ttu-id="5469a-129"> [Инструкции](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="5469a-130"> [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-130"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="5469a-131"> [Только для чтения](../../../visual-basic/language-reference/modifiers/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="5469a-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span></span>  
<span data-ttu-id="5469a-132"> [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="5469a-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

