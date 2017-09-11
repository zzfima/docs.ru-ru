---
title: "/ =-Оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
dev_langs:
- VB
helpviewer_keywords:
- assignment statements, compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
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
ms.openlocfilehash: e877e98104b5c9fd679485b50a88943fac80a696
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="de582-102">Оператор /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de582-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="de582-103">Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой к переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="de582-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de582-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de582-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="de582-105">Части</span><span class="sxs-lookup"><span data-stu-id="de582-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="de582-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de582-106">Required.</span></span> <span data-ttu-id="de582-107">Любой числовой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="de582-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="de582-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de582-108">Required.</span></span> <span data-ttu-id="de582-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="de582-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de582-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="de582-110">Remarks</span></span>  
 <span data-ttu-id="de582-111">Элемент слева от `/=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="de582-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="de582-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="de582-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="de582-113">`/=` Оператор сначала делит значение переменной или свойства (в левой части оператора) значение выражения (в правой части оператора).</span><span class="sxs-lookup"><span data-stu-id="de582-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="de582-114">Затем оператор присваивает результат этой операции с плавающей запятой к переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="de582-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="de582-115">Эта инструкция присваивает `Double` значение переменной или свойству в левой части окна.</span><span class="sxs-lookup"><span data-stu-id="de582-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="de582-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span><span class="sxs-lookup"><span data-stu-id="de582-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="de582-117">Если `Option Strict` — `Off`, Visual Basic выполняет неявное преобразование и присваивает полученное значение для `variableorproperty`, возможные ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="de582-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="de582-118">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="de582-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="de582-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="de582-119">Overloading</span></span>  
 <span data-ttu-id="de582-120">[-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегруженные*, это означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="de582-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="de582-121">Перегрузка `/` оператор влияет на поведение `/=` оператор.</span><span class="sxs-lookup"><span data-stu-id="de582-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="de582-122">Если ваш код использует `/=` для класса или структуры, перегружающей `/`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="de582-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="de582-123">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="de582-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de582-124">Пример</span><span class="sxs-lookup"><span data-stu-id="de582-124">Example</span></span>  
 <span data-ttu-id="de582-125">В следующем примере используется `/=` оператор деления для деления одного `Integer` переменных в секунду и назначить частное первой переменной.</span><span class="sxs-lookup"><span data-stu-id="de582-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 <span data-ttu-id="de582-126">[!code-vb[VbVbalrOperators&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="de582-126">[!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de582-127">См. также</span><span class="sxs-lookup"><span data-stu-id="de582-127">See Also</span></span>  
 <span data-ttu-id="de582-128">[/ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="de582-128">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span></span>  
<span data-ttu-id="de582-129"> [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="de582-129"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="de582-130"> [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="de582-130"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="de582-131"> [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="de582-131"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="de582-132"> [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="de582-132"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="de582-133"> [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="de582-133"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="de582-134"> [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="de582-134"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

