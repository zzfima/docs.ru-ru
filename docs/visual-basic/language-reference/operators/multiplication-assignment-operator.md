---
title: "Оператор *= (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0a2c638f3faaf20fadb745ef437941ee29d4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ee44c-102">Оператор *= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee44c-102">*= Operator (Visual Basic)</span></span>
<span data-ttu-id="ee44c-103">Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="ee44c-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee44c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee44c-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ee44c-105">Части</span><span class="sxs-lookup"><span data-stu-id="ee44c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ee44c-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ee44c-106">Required.</span></span> <span data-ttu-id="ee44c-107">Числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="ee44c-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ee44c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ee44c-108">Required.</span></span> <span data-ttu-id="ee44c-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="ee44c-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee44c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee44c-110">Remarks</span></span>  
 <span data-ttu-id="ee44c-111">Элемент, на левой стороне `*=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="ee44c-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ee44c-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ee44c-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ee44c-113">`*=` Оператор сначала Умножает значение выражения (справа от оператора) значение переменной или свойства (в левой части оператора).</span><span class="sxs-lookup"><span data-stu-id="ee44c-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="ee44c-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="ee44c-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ee44c-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="ee44c-115">Overloading</span></span>  
 <span data-ttu-id="ee44c-116">[* Оператор](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ee44c-116">The [* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ee44c-117">Перегрузка `*` оператор влияет на поведение `*=` оператор.</span><span class="sxs-lookup"><span data-stu-id="ee44c-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="ee44c-118">Если ваш код использует `*=` для класса или структуры, перегружающей `*`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="ee44c-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ee44c-119">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ee44c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee44c-120">Пример</span><span class="sxs-lookup"><span data-stu-id="ee44c-120">Example</span></span>  
 <span data-ttu-id="ee44c-121">В следующем примере используется `*=` оператор для умножения одного `Integer` переменных в секунду и назначить результат первой переменной.</span><span class="sxs-lookup"><span data-stu-id="ee44c-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ee44c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ee44c-122">See Also</span></span>  
 [<span data-ttu-id="ee44c-123">Оператор *</span><span class="sxs-lookup"><span data-stu-id="ee44c-123">* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [<span data-ttu-id="ee44c-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="ee44c-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="ee44c-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="ee44c-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="ee44c-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee44c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ee44c-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="ee44c-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ee44c-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="ee44c-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
