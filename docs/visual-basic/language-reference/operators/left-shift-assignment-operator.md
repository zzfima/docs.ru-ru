---
title: << =-оператор (Visual Basic)
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
ms.openlocfilehash: da2b5ca0b7538d77c3c8d8bc7d45712d656ce63a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768320"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b2680-102">\<\<= Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2680-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="b2680-103">Выполняет арифметическое смещение влево на значение переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b2680-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2680-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2680-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="b2680-105">Части</span><span class="sxs-lookup"><span data-stu-id="b2680-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b2680-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2680-106">Required.</span></span> <span data-ttu-id="b2680-107">Переменная или свойство целочисленного типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="b2680-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="b2680-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2680-108">Required.</span></span> <span data-ttu-id="b2680-109">Числовое выражение типа данных, который расширяется до `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b2680-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2680-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2680-110">Remarks</span></span>  
 <span data-ttu-id="b2680-111">Элемент, на левой стороне `<<=` оператор может быть простой скалярной переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="b2680-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b2680-112">Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b2680-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b2680-113">`<<=` Оператор сначала выполняет арифметическое смещение влево на значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b2680-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="b2680-114">Затем оператор присваивает результат этой операции, переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b2680-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="b2680-115">Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце.</span><span class="sxs-lookup"><span data-stu-id="b2680-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="b2680-116">В арифметического сдвига влево биты, перемещен за пределы диапазона для типа данных результата отбрасываются и освободившиеся справа позиции битов заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="b2680-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b2680-117">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="b2680-117">Overloading</span></span>  
 <span data-ttu-id="b2680-118">[<< Оператор](../../../visual-basic/language-reference/operators/left-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b2680-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b2680-119">Перегрузка `<<` оператор влияет на поведение `<<=` оператор.</span><span class="sxs-lookup"><span data-stu-id="b2680-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="b2680-120">Если код использует `<<=` для класса или структуры, перегружающей `<<`, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="b2680-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b2680-121">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b2680-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2680-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b2680-122">Example</span></span>  
 <span data-ttu-id="b2680-123">В следующем примере используется `<<=` оператор, чтобы сдвинуть битовый шаблон из `Integer` переменной влево на заданную величину и назначить результат переменной.</span><span class="sxs-lookup"><span data-stu-id="b2680-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="b2680-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b2680-124">See also</span></span>

- [<span data-ttu-id="b2680-125">Оператор <<</span><span class="sxs-lookup"><span data-stu-id="b2680-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="b2680-126">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="b2680-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="b2680-127">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="b2680-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="b2680-128">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2680-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b2680-129">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="b2680-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b2680-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="b2680-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
