---
title: Оператор *= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 3aa1d563b9657d4e80425b8c2d29e069ca2ef06a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601887"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0bb52-102">Оператор \*= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bb52-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="0bb52-103">Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="0bb52-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bb52-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0bb52-105">Части</span><span class="sxs-lookup"><span data-stu-id="0bb52-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="0bb52-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0bb52-106">Required.</span></span> <span data-ttu-id="0bb52-107">Любой числовой переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="0bb52-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="0bb52-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0bb52-108">Required.</span></span> <span data-ttu-id="0bb52-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="0bb52-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bb52-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bb52-110">Remarks</span></span>  
 <span data-ttu-id="0bb52-111">Элемент, на левой стороне `*=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="0bb52-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="0bb52-112">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="0bb52-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="0bb52-113">`*=` Оператор сначала Умножает значение выражения (в области справа от оператора) на значение переменной или свойства (в левой части оператора).</span><span class="sxs-lookup"><span data-stu-id="0bb52-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="0bb52-114">Оператор затем присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="0bb52-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0bb52-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="0bb52-115">Overloading</span></span>  
 <span data-ttu-id="0bb52-116">[\* Оператор](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0bb52-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0bb52-117">Перегрузка `*` оператор влияет на поведение `*=` оператор.</span><span class="sxs-lookup"><span data-stu-id="0bb52-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="0bb52-118">Если код использует `*=` для класса или структуры, перегружающей `*`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="0bb52-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0bb52-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0bb52-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bb52-120">Пример</span><span class="sxs-lookup"><span data-stu-id="0bb52-120">Example</span></span>  
 <span data-ttu-id="0bb52-121">В следующем примере используется `*=` чтобы перемножить один `Integer` переменных в секунду и назначает полученное значение первой переменной.</span><span class="sxs-lookup"><span data-stu-id="0bb52-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0bb52-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0bb52-122">See also</span></span>
- [<span data-ttu-id="0bb52-123">Оператор \*</span><span class="sxs-lookup"><span data-stu-id="0bb52-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="0bb52-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="0bb52-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="0bb52-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="0bb52-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="0bb52-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0bb52-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0bb52-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="0bb52-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0bb52-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="0bb52-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
