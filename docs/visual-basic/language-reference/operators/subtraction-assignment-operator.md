---
title: Оператор -= (Visual Basic)
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
ms.openlocfilehash: 598fd9db4262d0a33bf0408ebe9455760d5e4506
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603877"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="4173b-102">Оператор -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4173b-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="4173b-103">Вычитает значение выражения из значения переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="4173b-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4173b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4173b-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4173b-105">Части</span><span class="sxs-lookup"><span data-stu-id="4173b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4173b-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4173b-106">Required.</span></span> <span data-ttu-id="4173b-107">Числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="4173b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="4173b-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4173b-108">Required.</span></span> <span data-ttu-id="4173b-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4173b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4173b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4173b-110">Remarks</span></span>  
 <span data-ttu-id="4173b-111">Элемент, на левой стороне `-=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="4173b-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4173b-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4173b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4173b-113">`-=` Оператор сначала вычитает значение выражения (справа от оператора) из значения переменной или свойства (в левой части оператора).</span><span class="sxs-lookup"><span data-stu-id="4173b-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="4173b-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="4173b-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4173b-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="4173b-115">Overloading</span></span>  
 <span data-ttu-id="4173b-116">[-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4173b-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4173b-117">Перегрузка `-` оператор влияет на поведение `-=` оператор.</span><span class="sxs-lookup"><span data-stu-id="4173b-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="4173b-118">Если ваш код использует `-=` для класса или структуры, перегружающей `-`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="4173b-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4173b-119">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4173b-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4173b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="4173b-120">Example</span></span>  
 <span data-ttu-id="4173b-121">В следующем примере используется `-=` оператор для вычитания одного `Integer` переменной из другого и назначить результат первой переменной.</span><span class="sxs-lookup"><span data-stu-id="4173b-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4173b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4173b-122">See Also</span></span>  
 [<span data-ttu-id="4173b-123">-Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4173b-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)  
 [<span data-ttu-id="4173b-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="4173b-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="4173b-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="4173b-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="4173b-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4173b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4173b-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="4173b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4173b-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="4173b-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
