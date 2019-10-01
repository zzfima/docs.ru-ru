---
title: '\=Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: d7b4a6946cc38984272a6b63e14e8c1db2825a5e
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700680"
---
# <a name="-operator"></a><span data-ttu-id="062e7-102">\\ = оператор</span><span class="sxs-lookup"><span data-stu-id="062e7-102">\\= Operator</span></span>
<span data-ttu-id="062e7-103">Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="062e7-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="062e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="062e7-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="062e7-105">Части</span><span class="sxs-lookup"><span data-stu-id="062e7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="062e7-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="062e7-106">Required.</span></span> <span data-ttu-id="062e7-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="062e7-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="062e7-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="062e7-108">Required.</span></span> <span data-ttu-id="062e7-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="062e7-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="062e7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="062e7-110">Remarks</span></span>  
 <span data-ttu-id="062e7-111">Элемент в левой части оператора `\=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="062e7-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="062e7-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="062e7-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="062e7-113">Оператор `\=` делит значение переменной или свойства слева на значение справа, а целочисленный результат присваивается переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="062e7-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="062e7-114">Дополнительные сведения о целочисленном делении см. в разделе [оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="062e7-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="062e7-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="062e7-115">Overloading</span></span>  
 <span data-ttu-id="062e7-116">Оператор `\` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="062e7-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="062e7-117">Перегрузка оператора `\` влияет на поведение оператора `\=`.</span><span class="sxs-lookup"><span data-stu-id="062e7-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="062e7-118">Если в коде используется `\=` для класса или структуры, которая перегружает `\`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="062e7-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="062e7-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="062e7-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="062e7-120">Пример</span><span class="sxs-lookup"><span data-stu-id="062e7-120">Example</span></span>  
 <span data-ttu-id="062e7-121">В следующем примере оператор `\=` используется для деления одной переменной `Integer` на вторую и присваивания целочисленного результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="062e7-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="062e7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="062e7-122">See also</span></span>

- [<span data-ttu-id="062e7-123">Оператор \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="062e7-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="062e7-124">Оператор/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="062e7-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="062e7-125">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="062e7-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="062e7-126">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="062e7-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="062e7-127">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="062e7-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="062e7-128">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="062e7-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="062e7-129">Операторы</span><span class="sxs-lookup"><span data-stu-id="062e7-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
