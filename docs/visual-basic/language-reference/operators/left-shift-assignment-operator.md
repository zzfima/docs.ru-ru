---
title: '&lt;&lt;= Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: 559624f7097f90d374ee83e3c0a9ac97d9f93444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600731"
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="3aa22-102">&lt;&lt;= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aa22-102">&lt;&lt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="3aa22-103">Выполняет арифметическое смещение влево на значение переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3aa22-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3aa22-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="3aa22-105">Части</span><span class="sxs-lookup"><span data-stu-id="3aa22-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3aa22-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3aa22-106">Required.</span></span> <span data-ttu-id="3aa22-107">Переменная или свойство целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="3aa22-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="3aa22-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3aa22-108">Required.</span></span> <span data-ttu-id="3aa22-109">Числовое выражение типа данных, который расширяется до `Integer`.</span><span class="sxs-lookup"><span data-stu-id="3aa22-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3aa22-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3aa22-110">Remarks</span></span>  
 <span data-ttu-id="3aa22-111">Элемент, на левой стороне `<<=` оператор может быть простой скалярной переменной, свойством или элемент массива.</span><span class="sxs-lookup"><span data-stu-id="3aa22-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3aa22-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3aa22-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3aa22-113">`<<=` Оператор сначала выполняет арифметическое смещение влево на значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3aa22-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="3aa22-114">Затем оператор присваивает результат этой операции, переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="3aa22-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="3aa22-115">Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="3aa22-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="3aa22-116">В арифметический сдвиг влево биты, сдвигаемые дальше диапазона типа данных результата отбрасываются, а освободившиеся справа позиции битов заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="3aa22-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3aa22-117">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="3aa22-117">Overloading</span></span>  
 <span data-ttu-id="3aa22-118">[<< Оператор](../../../visual-basic/language-reference/operators/left-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3aa22-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3aa22-119">Перегрузка `<<` оператор влияет на поведение `<<=` оператор.</span><span class="sxs-lookup"><span data-stu-id="3aa22-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="3aa22-120">Если ваш код использует `<<=` для класса или структуры, перегружающей `<<`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="3aa22-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3aa22-121">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3aa22-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3aa22-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3aa22-122">Example</span></span>  
 <span data-ttu-id="3aa22-123">В следующем примере используется `<<=` оператор, на которое производится Сдвиг битового представления `Integer` переменной влево на указанную величину и назначить результат переменной.</span><span class="sxs-lookup"><span data-stu-id="3aa22-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3aa22-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3aa22-124">See Also</span></span>  
 [<span data-ttu-id="3aa22-125">Оператор <<</span><span class="sxs-lookup"><span data-stu-id="3aa22-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [<span data-ttu-id="3aa22-126">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="3aa22-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="3aa22-127">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="3aa22-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="3aa22-128">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aa22-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="3aa22-129">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="3aa22-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="3aa22-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="3aa22-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
