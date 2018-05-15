---
title: Оператор ^= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 571ef26eb188d9044ec8f6c8e6e4b490780f17a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="02a45-102">Оператор ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a45-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="02a45-103">Возводит значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="02a45-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02a45-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="02a45-105">Части</span><span class="sxs-lookup"><span data-stu-id="02a45-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="02a45-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="02a45-106">Required.</span></span> <span data-ttu-id="02a45-107">Числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="02a45-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="02a45-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="02a45-108">Required.</span></span> <span data-ttu-id="02a45-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="02a45-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a45-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="02a45-110">Remarks</span></span>  
 <span data-ttu-id="02a45-111">Элемент, на левой стороне `^=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="02a45-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="02a45-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="02a45-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="02a45-113">`^=` Оператор сначала вызывает значение переменной или свойства (в левой части оператора) в степень значение выражения (справа от оператора).</span><span class="sxs-lookup"><span data-stu-id="02a45-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="02a45-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="02a45-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="02a45-115">Visual Basic всегда выполняет возведение в степень, в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="02a45-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="02a45-116">Операнды любого другого типа преобразуются в `Double`, и результат всегда является `Double`.</span><span class="sxs-lookup"><span data-stu-id="02a45-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="02a45-117">Значение `expression` может быть дробным, отрицательным или оба.</span><span class="sxs-lookup"><span data-stu-id="02a45-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="02a45-118">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="02a45-118">Overloading</span></span>  
 <span data-ttu-id="02a45-119">[^ Оператор](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="02a45-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="02a45-120">Перегрузка `^` оператор влияет на поведение `^=` оператор.</span><span class="sxs-lookup"><span data-stu-id="02a45-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="02a45-121">Если ваш код использует `^=` для класса или структуры, перегружающей `^`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="02a45-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="02a45-122">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="02a45-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02a45-123">Пример</span><span class="sxs-lookup"><span data-stu-id="02a45-123">Example</span></span>  
 <span data-ttu-id="02a45-124">В следующем примере используется `^=` оператор для вызова одного `Integer` переменной в степень второй переменной и назначить результат первой переменной.</span><span class="sxs-lookup"><span data-stu-id="02a45-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="02a45-125">См. также</span><span class="sxs-lookup"><span data-stu-id="02a45-125">See Also</span></span>  
 [<span data-ttu-id="02a45-126">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="02a45-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="02a45-127">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="02a45-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="02a45-128">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="02a45-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="02a45-129">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02a45-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="02a45-130">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="02a45-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="02a45-131">Операторы</span><span class="sxs-lookup"><span data-stu-id="02a45-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
