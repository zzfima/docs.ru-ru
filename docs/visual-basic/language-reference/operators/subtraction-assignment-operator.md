---
title: Оператор -=
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 44cb226d64e9f0b86c6566eb25fbafd6323a6d4c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347812"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="2991e-102">Оператор -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2991e-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="2991e-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="2991e-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2991e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2991e-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2991e-105">Части</span><span class="sxs-lookup"><span data-stu-id="2991e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2991e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2991e-106">Required.</span></span> <span data-ttu-id="2991e-107">Any numeric variable or property.</span><span class="sxs-lookup"><span data-stu-id="2991e-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2991e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2991e-108">Required.</span></span> <span data-ttu-id="2991e-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="2991e-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2991e-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2991e-110">Remarks</span></span>  
 <span data-ttu-id="2991e-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="2991e-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2991e-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="2991e-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2991e-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span><span class="sxs-lookup"><span data-stu-id="2991e-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="2991e-114">The operator then assigns the result of that operation to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="2991e-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2991e-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="2991e-115">Overloading</span></span>  
 <span data-ttu-id="2991e-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="2991e-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2991e-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span><span class="sxs-lookup"><span data-stu-id="2991e-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="2991e-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="2991e-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2991e-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2991e-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2991e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="2991e-120">Example</span></span>  
 <span data-ttu-id="2991e-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span><span class="sxs-lookup"><span data-stu-id="2991e-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="2991e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2991e-122">See also</span></span>

- [<span data-ttu-id="2991e-123">- Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2991e-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="2991e-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="2991e-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2991e-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="2991e-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2991e-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2991e-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2991e-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="2991e-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2991e-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="2991e-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
