---
title: Оператор /= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 642307bc531e7d9ce21a932b112795b35e7b3182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604098"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3fd64-102">Оператор /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fd64-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="3fd64-103">Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3fd64-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fd64-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3fd64-105">Части</span><span class="sxs-lookup"><span data-stu-id="3fd64-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3fd64-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3fd64-106">Required.</span></span> <span data-ttu-id="3fd64-107">Числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="3fd64-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3fd64-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3fd64-108">Required.</span></span> <span data-ttu-id="3fd64-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="3fd64-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fd64-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fd64-110">Remarks</span></span>  
 <span data-ttu-id="3fd64-111">Элемент, на левой стороне `/=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="3fd64-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3fd64-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3fd64-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3fd64-113">`/=` Оператор сначала делит значение переменной или свойства (в левой части оператора) значение выражения (в правой части оператора).</span><span class="sxs-lookup"><span data-stu-id="3fd64-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="3fd64-114">Затем оператор присваивает результат этой операции с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3fd64-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="3fd64-115">Эта инструкция присваивает `Double` значение переменной или свойству в левой части экрана.</span><span class="sxs-lookup"><span data-stu-id="3fd64-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="3fd64-116">Если `Option Strict` — `On`, `variableorproperty` должен быть `Double`.</span><span class="sxs-lookup"><span data-stu-id="3fd64-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="3fd64-117">Если `Option Strict` — `Off`, Visual Basic выполняет неявное преобразование, а затем присваивает результирующее значение `variableorproperty`, возможные ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3fd64-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="3fd64-118">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3fd64-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3fd64-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="3fd64-119">Overloading</span></span>  
 <span data-ttu-id="3fd64-120">[-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружены*, это означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3fd64-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3fd64-121">Перегрузка `/` оператор влияет на поведение `/=` оператор.</span><span class="sxs-lookup"><span data-stu-id="3fd64-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="3fd64-122">Если ваш код использует `/=` для класса или структуры, перегружающей `/`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="3fd64-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3fd64-123">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3fd64-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd64-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3fd64-124">Example</span></span>  
 <span data-ttu-id="3fd64-125">В следующем примере используется `/=` оператор деления для деления одного `Integer` переменных в секунду и назначить частное первой переменной.</span><span class="sxs-lookup"><span data-stu-id="3fd64-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3fd64-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd64-126">See Also</span></span>  
 [<span data-ttu-id="3fd64-127">/ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fd64-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="3fd64-128">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="3fd64-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="3fd64-129">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="3fd64-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="3fd64-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="3fd64-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="3fd64-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fd64-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="3fd64-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="3fd64-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="3fd64-133">Операторы</span><span class="sxs-lookup"><span data-stu-id="3fd64-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
