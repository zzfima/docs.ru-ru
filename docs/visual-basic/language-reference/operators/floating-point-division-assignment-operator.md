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
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592175"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4d91b-102">Оператор /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d91b-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="4d91b-103">Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="4d91b-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d91b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d91b-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4d91b-105">Части</span><span class="sxs-lookup"><span data-stu-id="4d91b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4d91b-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4d91b-106">Required.</span></span> <span data-ttu-id="4d91b-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="4d91b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="4d91b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4d91b-108">Required.</span></span> <span data-ttu-id="4d91b-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4d91b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d91b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d91b-110">Remarks</span></span>  
 <span data-ttu-id="4d91b-111">Элемент в левой части оператора `/=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="4d91b-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4d91b-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4d91b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4d91b-113">Оператор `/=` вначале делит значение переменной или свойства (в левой части оператора) на значение выражения (в правой части оператора), равное.</span><span class="sxs-lookup"><span data-stu-id="4d91b-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="4d91b-114">Затем оператор присваивает результат операции с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="4d91b-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="4d91b-115">Эта инструкция присваивает значение `Double` переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="4d91b-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="4d91b-116">Если `Option Strict` равно `On`, `variableorproperty` должно быть `Double`.</span><span class="sxs-lookup"><span data-stu-id="4d91b-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="4d91b-117">Если `Option Strict` равно `Off`, Visual Basic выполняет неявное преобразование и присваивает полученное значение `variableorproperty` с возможной ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d91b-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="4d91b-118">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Option](../../../visual-basic/language-reference/statements/option-strict-statement.md)parallelism.</span><span class="sxs-lookup"><span data-stu-id="4d91b-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4d91b-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="4d91b-119">Overloading</span></span>  
 <span data-ttu-id="4d91b-120">[Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4d91b-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4d91b-121">Перегрузка оператора `/` влияет на поведение оператора `/=`.</span><span class="sxs-lookup"><span data-stu-id="4d91b-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="4d91b-122">Если в коде используется `/=` для класса или структуры, которая перегружает `/`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="4d91b-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4d91b-123">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4d91b-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d91b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4d91b-124">Example</span></span>  
 <span data-ttu-id="4d91b-125">В следующем примере оператор `/=` используется для деления одной переменной `Integer` на вторую и присваивания значения частного для первой переменной.</span><span class="sxs-lookup"><span data-stu-id="4d91b-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="4d91b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4d91b-126">See also</span></span>

- [<span data-ttu-id="4d91b-127">Оператор/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d91b-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="4d91b-128">\\ = оператор</span><span class="sxs-lookup"><span data-stu-id="4d91b-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="4d91b-129">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="4d91b-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="4d91b-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="4d91b-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="4d91b-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d91b-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4d91b-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="4d91b-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4d91b-133">Операторы</span><span class="sxs-lookup"><span data-stu-id="4d91b-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
