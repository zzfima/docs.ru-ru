---
title: Оператор += (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: cfe987929099fc73ba3af9fe92b5871275c5396e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617555"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="cfc21-102">Оператор += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfc21-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="cfc21-103">Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="cfc21-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="cfc21-104">Можно также использовать для объединения `String` выражение `String` переменная или свойство и назначает полученное значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="cfc21-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc21-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfc21-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="cfc21-106">Части</span><span class="sxs-lookup"><span data-stu-id="cfc21-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="cfc21-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cfc21-107">Required.</span></span> <span data-ttu-id="cfc21-108">Любой числовой или `String` переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="cfc21-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="cfc21-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cfc21-109">Required.</span></span> <span data-ttu-id="cfc21-110">Любой числовой или `String` выражение.</span><span class="sxs-lookup"><span data-stu-id="cfc21-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfc21-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfc21-111">Remarks</span></span>  
 <span data-ttu-id="cfc21-112">Элемент, на левой стороне `+=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="cfc21-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="cfc21-113">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="cfc21-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="cfc21-114">`+=` Оператор добавляет значение справа переменной или свойству слева от него и присваивает результат переменной или свойству слева от него.</span><span class="sxs-lookup"><span data-stu-id="cfc21-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="cfc21-115">`+=` Оператор может также использоваться для сцепления `String` выражение, право на `String` переменной или свойства на слева и назначает полученное значение переменной или свойства слева от него.</span><span class="sxs-lookup"><span data-stu-id="cfc21-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfc21-116">При использовании `+=` оператора, может не появиться возможность определить, произойдет ли объединение строк или сложение операция.</span><span class="sxs-lookup"><span data-stu-id="cfc21-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="cfc21-117">Используйте `&=` для объединения оператор устранения неоднозначности и выполнять код.</span><span class="sxs-lookup"><span data-stu-id="cfc21-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="cfc21-118">Этот оператор присваивания производит неявное не сужающие преобразования, если среда требует строгую семантику.</span><span class="sxs-lookup"><span data-stu-id="cfc21-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="cfc21-119">Дополнительные сведения об этих преобразованиях см. в разделе [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="cfc21-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="cfc21-120">Дополнительные сведения о строгой и см. в разделе [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cfc21-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="cfc21-121">Если разрешено семантика разрешений, `+=` оператор неявно выполняет различные строковые и числовые преобразования, которые идентичны функциям `+` оператор.</span><span class="sxs-lookup"><span data-stu-id="cfc21-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="cfc21-122">Дополнительные сведения об этих преобразований, см. в разделе [оператором "+"](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="cfc21-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="cfc21-123">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="cfc21-123">Overloading</span></span>  
 <span data-ttu-id="cfc21-124">`+` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="cfc21-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cfc21-125">Перегрузка `+` оператор влияет на поведение `+=` оператор.</span><span class="sxs-lookup"><span data-stu-id="cfc21-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="cfc21-126">Если код использует `+=` для класса или структуры, перегружающей `+`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="cfc21-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cfc21-127">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="cfc21-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfc21-128">Пример</span><span class="sxs-lookup"><span data-stu-id="cfc21-128">Example</span></span>  
 <span data-ttu-id="cfc21-129">В следующем примере используется `+=` оператор для объединения значений переменной типа с другим.</span><span class="sxs-lookup"><span data-stu-id="cfc21-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="cfc21-130">Первая часть использует `+=` для числовых переменных, чтобы добавить одного значения к другому.</span><span class="sxs-lookup"><span data-stu-id="cfc21-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="cfc21-131">Вторая часть использует `+=` с `String` переменные для добавления одной строки с другим.</span><span class="sxs-lookup"><span data-stu-id="cfc21-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="cfc21-132">В обоих случаях результат назначается первой переменной.</span><span class="sxs-lookup"><span data-stu-id="cfc21-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="cfc21-133">Значение `num1` 13, а значение `str1` становится «103».</span><span class="sxs-lookup"><span data-stu-id="cfc21-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc21-134">См. также</span><span class="sxs-lookup"><span data-stu-id="cfc21-134">See also</span></span>
- [<span data-ttu-id="cfc21-135">Оператор +</span><span class="sxs-lookup"><span data-stu-id="cfc21-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="cfc21-136">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="cfc21-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="cfc21-137">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="cfc21-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="cfc21-138">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="cfc21-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="cfc21-139">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfc21-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cfc21-140">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="cfc21-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="cfc21-141">Операторы</span><span class="sxs-lookup"><span data-stu-id="cfc21-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
