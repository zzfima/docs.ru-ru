---
title: Оператор IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bf81384b0cecfd1ee3d438e4463949381279a181
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785196"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="c8cb0-102">Оператор IsTrue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8cb0-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="c8cb0-103">Определяет, является ли выражение `True`.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="c8cb0-104">Нельзя вызывать `IsTrue` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `OrElse` предложения.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="c8cb0-105">Если вы задаете класса или структуры, а затем использовать переменную этого типа в `OrElse` предложение, необходимо определить `IsTrue` для этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="c8cb0-106">Компилятор считает, что `IsTrue` и `IsFalse` операторы как *соответствующую пару*.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="c8cb0-107">Это означает, что если определить один из них, необходимо также определить другой.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="c8cb0-108">Использование IsTrue компилятором</span><span class="sxs-lookup"><span data-stu-id="c8cb0-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="c8cb0-109">После определения класса или структуры, можно использовать переменную этого типа в `For`, `If`, `Else If`, или `While` инструкции, либо в `When` предложение.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="c8cb0-110">После этого компилятор требует оператор, который преобразует тип в `Boolean` значение, чтобы проверить условие.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="c8cb0-111">Он выполняет поиск подходящего оператора в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="c8cb0-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="c8cb0-112">Оператор расширяющего преобразования от класса или структуры `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="c8cb0-113">Оператор расширяющего преобразования от класса или структуры `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="c8cb0-114">`IsTrue` Оператора для класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="c8cb0-115">Сужающее преобразование к типу `Boolean?` , не включает преобразование из `Boolean` для `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="c8cb0-116">Оператор сужающего преобразования от класса или структуры `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="c8cb0-117">Если не определены никакие преобразования в `Boolean` или `IsTrue` оператор, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8cb0-118">`IsTrue` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="c8cb0-119">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c8cb0-120">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb0-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8cb0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="c8cb0-121">Example</span></span>  
 <span data-ttu-id="c8cb0-122">В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.</span><span class="sxs-lookup"><span data-stu-id="c8cb0-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c8cb0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c8cb0-123">See Also</span></span>  
 [<span data-ttu-id="c8cb0-124">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="c8cb0-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="c8cb0-125">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="c8cb0-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="c8cb0-126">Оператор OrElse</span><span class="sxs-lookup"><span data-stu-id="c8cb0-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
