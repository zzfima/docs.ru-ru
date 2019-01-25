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
ms.openlocfilehash: 73705df376284edd9d8f20baaf4306c41b1d3943
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699731"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="80858-102">Оператор ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80858-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="80858-103">Возводит значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="80858-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80858-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80858-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="80858-105">Части</span><span class="sxs-lookup"><span data-stu-id="80858-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="80858-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="80858-106">Required.</span></span> <span data-ttu-id="80858-107">Любой числовой переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="80858-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="80858-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="80858-108">Required.</span></span> <span data-ttu-id="80858-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="80858-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80858-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="80858-110">Remarks</span></span>  
 <span data-ttu-id="80858-111">Элемент, на левой стороне `^=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="80858-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="80858-112">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="80858-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="80858-113">`^=` Оператор прежде всего создает значение переменной или свойства (в левой части оператора) в степень значения выражения (в области справа от оператора).</span><span class="sxs-lookup"><span data-stu-id="80858-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="80858-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="80858-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="80858-115">Visual Basic всегда выполняет возведение в степень в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="80858-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="80858-116">Операнды любого другого типа преобразуются в `Double`, и результат всегда имеет `Double`.</span><span class="sxs-lookup"><span data-stu-id="80858-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="80858-117">Значение `expression` может быть дробным, отрицательным или оба.</span><span class="sxs-lookup"><span data-stu-id="80858-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="80858-118">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="80858-118">Overloading</span></span>  
 <span data-ttu-id="80858-119">[^ Оператор](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="80858-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="80858-120">Перегрузка `^` оператор влияет на поведение `^=` оператор.</span><span class="sxs-lookup"><span data-stu-id="80858-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="80858-121">Если код использует `^=` для класса или структуры, перегружающей `^`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="80858-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="80858-122">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="80858-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80858-123">Пример</span><span class="sxs-lookup"><span data-stu-id="80858-123">Example</span></span>  
 <span data-ttu-id="80858-124">В следующем примере используется `^=` оператор для вызова значении, равном единице `Integer` переменной в степень второй переменной и назначает полученное значение первой переменной.</span><span class="sxs-lookup"><span data-stu-id="80858-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="80858-125">См. также</span><span class="sxs-lookup"><span data-stu-id="80858-125">See also</span></span>
- [<span data-ttu-id="80858-126">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="80858-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="80858-127">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="80858-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="80858-128">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="80858-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="80858-129">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80858-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="80858-130">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="80858-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="80858-131">Операторы</span><span class="sxs-lookup"><span data-stu-id="80858-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
