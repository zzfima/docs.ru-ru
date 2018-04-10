---
title: '&gt;&gt;= Оператор (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="677ab-102">&gt;&gt;= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="677ab-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="677ab-103">Выполняет арифметический сдвиг вправо значения переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="677ab-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="677ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="677ab-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="677ab-105">Части</span><span class="sxs-lookup"><span data-stu-id="677ab-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="677ab-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="677ab-106">Required.</span></span> <span data-ttu-id="677ab-107">Переменная или свойство целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="677ab-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="677ab-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="677ab-108">Required.</span></span> <span data-ttu-id="677ab-109">Числовое выражение типа данных, который расширяется до `Integer`.</span><span class="sxs-lookup"><span data-stu-id="677ab-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="677ab-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="677ab-110">Remarks</span></span>  
 <span data-ttu-id="677ab-111">Элемент, на левой стороне `>>=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="677ab-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="677ab-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="677ab-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="677ab-113">`>>=` Оператор сначала выполняет арифметический сдвиг вправо значения переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="677ab-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="677ab-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="677ab-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="677ab-115">Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="677ab-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="677ab-116">В арифметический сдвиг вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а крайний левый бит передается в освободившиеся слева позиции битов.</span><span class="sxs-lookup"><span data-stu-id="677ab-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="677ab-117">Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые устанавливаются в единицу.</span><span class="sxs-lookup"><span data-stu-id="677ab-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="677ab-118">Если `variableorproperty` положительно, или если его тип данных является тип без знака, освобождаемые принимают нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="677ab-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="677ab-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="677ab-119">Overloading</span></span>  
 <span data-ttu-id="677ab-120">[>> Оператор](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="677ab-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="677ab-121">Перегрузка `>>` оператор влияет на поведение `>>=` оператор.</span><span class="sxs-lookup"><span data-stu-id="677ab-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="677ab-122">Если ваш код использует `>>=` для класса или структуры, перегружающей `>>`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="677ab-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="677ab-123">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="677ab-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="677ab-124">Пример</span><span class="sxs-lookup"><span data-stu-id="677ab-124">Example</span></span>  
 <span data-ttu-id="677ab-125">В следующем примере используется `>>=` оператор, на которое производится Сдвиг битового представления `Integer` переменной вправо на указанную величину и присвоить его результат переменной.</span><span class="sxs-lookup"><span data-stu-id="677ab-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="677ab-126">См. также</span><span class="sxs-lookup"><span data-stu-id="677ab-126">See Also</span></span>  
 [<span data-ttu-id="677ab-127">Оператор >></span><span class="sxs-lookup"><span data-stu-id="677ab-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="677ab-128">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="677ab-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="677ab-129">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="677ab-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="677ab-130">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="677ab-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="677ab-131">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="677ab-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="677ab-132">Операторы</span><span class="sxs-lookup"><span data-stu-id="677ab-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
