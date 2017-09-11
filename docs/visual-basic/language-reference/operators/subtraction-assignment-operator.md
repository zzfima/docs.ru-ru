---
title: "-= Оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: 694033ec89e32b5fdba4092bd60292af536f58dd
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="3c685-102">Оператор -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c685-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="3c685-103">Вычитает значение выражения из значения переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3c685-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c685-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c685-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3c685-105">Части</span><span class="sxs-lookup"><span data-stu-id="3c685-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3c685-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3c685-106">Required.</span></span> <span data-ttu-id="3c685-107">Любой числовой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3c685-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3c685-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3c685-108">Required.</span></span> <span data-ttu-id="3c685-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="3c685-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c685-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c685-110">Remarks</span></span>  
 <span data-ttu-id="3c685-111">Элемент слева от `-=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="3c685-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3c685-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3c685-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3c685-113">`-=` Оператор сначала вычитает значение выражения (справа от оператора) из значения переменной или свойства (в левой части оператора).</span><span class="sxs-lookup"><span data-stu-id="3c685-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="3c685-114">Затем оператор присваивает результат этой операции к переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3c685-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3c685-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="3c685-115">Overloading</span></span>  
 <span data-ttu-id="3c685-116">[-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) может быть *перегруженные*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c685-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3c685-117">Перегрузка `-` оператор влияет на поведение `-=` оператор.</span><span class="sxs-lookup"><span data-stu-id="3c685-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="3c685-118">Если ваш код использует `-=` для класса или структуры, перегружающей `-`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="3c685-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3c685-119">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3c685-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c685-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3c685-120">Example</span></span>  
 <span data-ttu-id="3c685-121">В следующем примере используется `-=` оператор вычитание одного `Integer` переменной из другого и назначить результат первой переменной.</span><span class="sxs-lookup"><span data-stu-id="3c685-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 <span data-ttu-id="3c685-122">[!code-vb[VbVbalrOperators&11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3c685-122">[!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c685-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3c685-123">See Also</span></span>  
 <span data-ttu-id="3c685-124">[-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span><span class="sxs-lookup"><span data-stu-id="3c685-124">[- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span></span>  
<span data-ttu-id="3c685-125"> [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="3c685-125"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="3c685-126"> [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="3c685-126"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="3c685-127"> [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="3c685-127"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="3c685-128"> [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="3c685-128"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="3c685-129"> [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="3c685-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

