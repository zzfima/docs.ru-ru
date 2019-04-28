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
ms.openlocfilehash: d9d3fa021654d3be1b9d304beb83caa737660264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778473"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d86b4-102">Оператор /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d86b4-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="d86b4-103">Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="d86b4-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d86b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d86b4-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d86b4-105">Части</span><span class="sxs-lookup"><span data-stu-id="d86b4-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="d86b4-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d86b4-106">Required.</span></span> <span data-ttu-id="d86b4-107">Любой числовой переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="d86b4-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="d86b4-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d86b4-108">Required.</span></span> <span data-ttu-id="d86b4-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d86b4-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d86b4-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d86b4-110">Remarks</span></span>  
 <span data-ttu-id="d86b4-111">Элемент, на левой стороне `/=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="d86b4-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d86b4-112">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d86b4-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="d86b4-113">`/=` Оператор сначала делит значение переменной или свойства (в левой части оператора) значение выражения (в области справа от оператора).</span><span class="sxs-lookup"><span data-stu-id="d86b4-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="d86b4-114">Затем оператор присваивает результат этой операции с плавающей запятой к переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="d86b4-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="d86b4-115">Эта инструкция присваивает `Double` значение переменной или свойства в левой части.</span><span class="sxs-lookup"><span data-stu-id="d86b4-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="d86b4-116">Если `Option Strict` — `On`, `variableorproperty` должно быть `Double`.</span><span class="sxs-lookup"><span data-stu-id="d86b4-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="d86b4-117">Если `Option Strict` — `Off`, Visual Basic выполняет неявное преобразование, а затем присваивает результирующее значение `variableorproperty`, возможные ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d86b4-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="d86b4-118">Дополнительные сведения см. в разделе [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d86b4-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d86b4-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="d86b4-119">Overloading</span></span>  
 <span data-ttu-id="d86b4-120">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d86b4-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d86b4-121">Перегрузка `/` оператор влияет на поведение `/=` оператор.</span><span class="sxs-lookup"><span data-stu-id="d86b4-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="d86b4-122">Если код использует `/=` для класса или структуры, перегружающей `/`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="d86b4-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d86b4-123">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d86b4-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d86b4-124">Пример</span><span class="sxs-lookup"><span data-stu-id="d86b4-124">Example</span></span>  
 <span data-ttu-id="d86b4-125">В следующем примере используется `/=` оператор деления для деления одного `Integer` переменных в секунду и назначить частное первой переменной.</span><span class="sxs-lookup"><span data-stu-id="d86b4-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="d86b4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d86b4-126">See also</span></span>

- [<span data-ttu-id="d86b4-127">/ Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d86b4-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="d86b4-128">\\= Оператор</span><span class="sxs-lookup"><span data-stu-id="d86b4-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="d86b4-129">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="d86b4-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="d86b4-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="d86b4-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="d86b4-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d86b4-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d86b4-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d86b4-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d86b4-133">Операторы</span><span class="sxs-lookup"><span data-stu-id="d86b4-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
