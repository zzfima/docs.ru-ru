---
title: '\= Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768357"
---
# <a name="-operator"></a><span data-ttu-id="5b65d-102">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="5b65d-102">\\= Operator</span></span>
<span data-ttu-id="5b65d-103">Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="5b65d-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b65d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b65d-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5b65d-105">Части</span><span class="sxs-lookup"><span data-stu-id="5b65d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5b65d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5b65d-106">Required.</span></span> <span data-ttu-id="5b65d-107">Любой числовой переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="5b65d-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5b65d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5b65d-108">Required.</span></span> <span data-ttu-id="5b65d-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="5b65d-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b65d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b65d-110">Remarks</span></span>  
 <span data-ttu-id="5b65d-111">Элемент, на левой стороне `\=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="5b65d-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5b65d-112">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5b65d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5b65d-113">`\=` Оператор делит значение переменной или свойства слева от него значение справа и присваивает целочисленный результат переменной или свойству слева от него</span><span class="sxs-lookup"><span data-stu-id="5b65d-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="5b65d-114">Для получения дополнительных сведений при целочисленном делении см. в разделе [\ оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5b65d-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5b65d-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="5b65d-115">Overloading</span></span>  
 <span data-ttu-id="5b65d-116">`\` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="5b65d-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5b65d-117">Перегрузка `\` оператор влияет на поведение `\=` оператор.</span><span class="sxs-lookup"><span data-stu-id="5b65d-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="5b65d-118">Если код использует `\=` для класса или структуры, перегружающей `\`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="5b65d-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5b65d-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5b65d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b65d-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5b65d-120">Example</span></span>  
 <span data-ttu-id="5b65d-121">В следующем примере используется `\=` оператор деления для деления одного `Integer` переменных в секунду и назначить результат целое число в первой переменной.</span><span class="sxs-lookup"><span data-stu-id="5b65d-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="5b65d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5b65d-122">See also</span></span>

- [<span data-ttu-id="5b65d-123">\ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b65d-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="5b65d-124">/ =-Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b65d-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="5b65d-125">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="5b65d-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="5b65d-126">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="5b65d-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="5b65d-127">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b65d-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5b65d-128">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="5b65d-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5b65d-129">Операторы</span><span class="sxs-lookup"><span data-stu-id="5b65d-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
