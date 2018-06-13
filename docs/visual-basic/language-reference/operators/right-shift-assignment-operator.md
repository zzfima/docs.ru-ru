---
title: '&gt;&gt;= Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: d0c0ea819741f80e30e55a960b1187699898a3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604111"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="af0f9-102">&gt;&gt;= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af0f9-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="af0f9-103">Выполняет арифметический сдвиг вправо значения переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="af0f9-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af0f9-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="af0f9-105">Части</span><span class="sxs-lookup"><span data-stu-id="af0f9-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="af0f9-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="af0f9-106">Required.</span></span> <span data-ttu-id="af0f9-107">Переменная или свойство целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="af0f9-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="af0f9-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="af0f9-108">Required.</span></span> <span data-ttu-id="af0f9-109">Числовое выражение типа данных, который расширяется до `Integer`.</span><span class="sxs-lookup"><span data-stu-id="af0f9-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af0f9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="af0f9-110">Remarks</span></span>  
 <span data-ttu-id="af0f9-111">Элемент, на левой стороне `>>=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="af0f9-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="af0f9-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="af0f9-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="af0f9-113">`>>=` Оператор сначала выполняет арифметический сдвиг вправо значения переменной или свойства.</span><span class="sxs-lookup"><span data-stu-id="af0f9-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="af0f9-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="af0f9-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="af0f9-115">Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="af0f9-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="af0f9-116">В арифметический сдвиг вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а крайний левый бит передается в освободившиеся слева позиции битов.</span><span class="sxs-lookup"><span data-stu-id="af0f9-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="af0f9-117">Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые устанавливаются в единицу.</span><span class="sxs-lookup"><span data-stu-id="af0f9-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="af0f9-118">Если `variableorproperty` положительно, или если его тип данных является тип без знака, освобождаемые принимают нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="af0f9-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="af0f9-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="af0f9-119">Overloading</span></span>  
 <span data-ttu-id="af0f9-120">[>> Оператор](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="af0f9-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="af0f9-121">Перегрузка `>>` оператор влияет на поведение `>>=` оператор.</span><span class="sxs-lookup"><span data-stu-id="af0f9-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="af0f9-122">Если ваш код использует `>>=` для класса или структуры, перегружающей `>>`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="af0f9-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="af0f9-123">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="af0f9-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0f9-124">Пример</span><span class="sxs-lookup"><span data-stu-id="af0f9-124">Example</span></span>  
 <span data-ttu-id="af0f9-125">В следующем примере используется `>>=` оператор, на которое производится Сдвиг битового представления `Integer` переменной вправо на указанную величину и присвоить его результат переменной.</span><span class="sxs-lookup"><span data-stu-id="af0f9-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="af0f9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="af0f9-126">See Also</span></span>  
 [<span data-ttu-id="af0f9-127">Оператор >></span><span class="sxs-lookup"><span data-stu-id="af0f9-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="af0f9-128">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="af0f9-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="af0f9-129">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="af0f9-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="af0f9-130">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af0f9-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="af0f9-131">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="af0f9-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="af0f9-132">Операторы</span><span class="sxs-lookup"><span data-stu-id="af0f9-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
