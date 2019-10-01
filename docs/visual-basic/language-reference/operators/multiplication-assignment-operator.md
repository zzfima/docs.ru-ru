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
ms.openlocfilehash: 47d3239af6ff24501e6babc23c0db4103c477796
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701069"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="98f80-102">Оператор \*= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98f80-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="98f80-103">Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="98f80-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98f80-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="98f80-105">Части</span><span class="sxs-lookup"><span data-stu-id="98f80-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="98f80-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="98f80-106">Required.</span></span> <span data-ttu-id="98f80-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="98f80-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="98f80-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="98f80-108">Required.</span></span> <span data-ttu-id="98f80-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="98f80-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98f80-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="98f80-110">Remarks</span></span>  
 <span data-ttu-id="98f80-111">Элемент в левой части оператора `*=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="98f80-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="98f80-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="98f80-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="98f80-113">Оператор `*=` вначале умножает значение выражения (в правой части оператора) на значение переменной или свойства (в левой части оператора) (слева).</span><span class="sxs-lookup"><span data-stu-id="98f80-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="98f80-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="98f80-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="98f80-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="98f80-115">Overloading</span></span>  
 <span data-ttu-id="98f80-116">[Оператор \*](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="98f80-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="98f80-117">Перегрузка оператора `*` влияет на поведение оператора `*=`.</span><span class="sxs-lookup"><span data-stu-id="98f80-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="98f80-118">Если в коде используется `*=` для класса или структуры, которая перегружает `*`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="98f80-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="98f80-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="98f80-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98f80-120">Пример</span><span class="sxs-lookup"><span data-stu-id="98f80-120">Example</span></span>  
 <span data-ttu-id="98f80-121">В следующем примере оператор `*=` используется для умножения одной переменной `Integer` на вторую и присваивания результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="98f80-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="98f80-122">См. также</span><span class="sxs-lookup"><span data-stu-id="98f80-122">See also</span></span>

- [<span data-ttu-id="98f80-123">Оператор \*</span><span class="sxs-lookup"><span data-stu-id="98f80-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="98f80-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="98f80-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="98f80-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="98f80-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="98f80-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98f80-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="98f80-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="98f80-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="98f80-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="98f80-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
