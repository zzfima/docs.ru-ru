---
title: "Оператор += (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ac8f5679aa90c50c15c33a957cfc75d9ccecde6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ce237-102">Оператор += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce237-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="ce237-103">Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="ce237-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="ce237-104">Можно также использовать для объединения `String` выражение `String` переменной или свойства и присвоить его результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="ce237-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce237-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce237-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ce237-106">Части</span><span class="sxs-lookup"><span data-stu-id="ce237-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ce237-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ce237-107">Required.</span></span> <span data-ttu-id="ce237-108">Любые числовые или `String` переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="ce237-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ce237-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ce237-109">Required.</span></span> <span data-ttu-id="ce237-110">Любые числовые или `String` выражение.</span><span class="sxs-lookup"><span data-stu-id="ce237-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce237-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce237-111">Remarks</span></span>  
 <span data-ttu-id="ce237-112">Элемент, на левой стороне `+=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="ce237-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ce237-113">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ce237-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ce237-114">`+=` Оператор добавляет значение справа переменной или свойству слева от него и присваивает результат переменной или свойству слева от него.</span><span class="sxs-lookup"><span data-stu-id="ce237-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="ce237-115">`+=` Оператор может также использоваться для сцепления `String` выражение справа для `String` переменную или свойство слева и назначить результат в переменную или свойство слева от него.</span><span class="sxs-lookup"><span data-stu-id="ce237-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce237-116">При использовании `+=` оператор не можно определить, произойдет ли объединение строк или сложение операция.</span><span class="sxs-lookup"><span data-stu-id="ce237-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="ce237-117">Используйте `&=` для объединения оператор во избежание неоднозначности и выполнять код.</span><span class="sxs-lookup"><span data-stu-id="ce237-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="ce237-118">Этот оператор присваивания производит неявное не сужающие преобразования, если среда требует строгой семантики.</span><span class="sxs-lookup"><span data-stu-id="ce237-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="ce237-119">Дополнительные сведения о подобных преобразованиях см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="ce237-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="ce237-120">Дополнительные сведения о строгой и см. в разделе [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ce237-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="ce237-121">Если семантика разрешений разрешены, `+=` оператор неявно выполняет различные строковые и числовые преобразования, которые идентичны выполняемым `+` оператор.</span><span class="sxs-lookup"><span data-stu-id="ce237-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="ce237-122">Дополнительные сведения об этих преобразований см. в разделе [оператор +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ce237-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ce237-123">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="ce237-123">Overloading</span></span>  
 <span data-ttu-id="ce237-124">`+` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ce237-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ce237-125">Перегрузка `+` оператор влияет на поведение `+=` оператор.</span><span class="sxs-lookup"><span data-stu-id="ce237-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="ce237-126">Если ваш код использует `+=` для класса или структуры, перегружающей `+`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="ce237-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ce237-127">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ce237-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce237-128">Пример</span><span class="sxs-lookup"><span data-stu-id="ce237-128">Example</span></span>  
 <span data-ttu-id="ce237-129">В следующем примере используется `+=` оператор для объединения значения одной переменной с другой.</span><span class="sxs-lookup"><span data-stu-id="ce237-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="ce237-130">Первая часть использует `+=` с числовыми переменными для добавления одного значения в другой.</span><span class="sxs-lookup"><span data-stu-id="ce237-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="ce237-131">Вторая часть использует `+=` с `String` переменные для добавления одной строки к другой.</span><span class="sxs-lookup"><span data-stu-id="ce237-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="ce237-132">В обоих случаях результат присваивается первой переменной.</span><span class="sxs-lookup"><span data-stu-id="ce237-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="ce237-133">Значение `num1` сейчас 13, а значение `str1` становится «103».</span><span class="sxs-lookup"><span data-stu-id="ce237-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce237-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ce237-134">See Also</span></span>  
 [<span data-ttu-id="ce237-135">Оператор +</span><span class="sxs-lookup"><span data-stu-id="ce237-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [<span data-ttu-id="ce237-136">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="ce237-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="ce237-137">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="ce237-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="ce237-138">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="ce237-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="ce237-139">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce237-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ce237-140">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="ce237-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ce237-141">Операторы</span><span class="sxs-lookup"><span data-stu-id="ce237-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
