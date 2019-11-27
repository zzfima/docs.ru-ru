---
title: '>>Оператор ='
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
ms.openlocfilehash: cad021c7730782d6233c60841483df7173308dc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351998"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="16f1a-102">Оператор > > = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16f1a-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="16f1a-103">Выполняет арифметическое смещение вправо для значения переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="16f1a-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16f1a-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="16f1a-105">Части</span><span class="sxs-lookup"><span data-stu-id="16f1a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="16f1a-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="16f1a-106">Required.</span></span> <span data-ttu-id="16f1a-107">Переменная или свойство целочисленного типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="16f1a-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="16f1a-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="16f1a-108">Required.</span></span> <span data-ttu-id="16f1a-109">Числовое выражение типа данных, которое расширяется до `Integer`.</span><span class="sxs-lookup"><span data-stu-id="16f1a-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16f1a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="16f1a-110">Remarks</span></span>  
 <span data-ttu-id="16f1a-111">Элемент в левой части оператора `>>=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="16f1a-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="16f1a-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="16f1a-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="16f1a-113">Оператор `>>=` сначала выполняет арифметический сдвиг значения переменной или свойства вправо.</span><span class="sxs-lookup"><span data-stu-id="16f1a-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="16f1a-114">Затем оператор присваивает результат этой операции с переменной или свойством.</span><span class="sxs-lookup"><span data-stu-id="16f1a-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="16f1a-115">Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец.</span><span class="sxs-lookup"><span data-stu-id="16f1a-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="16f1a-116">При арифметическом сдвиге вправо биты, сдвинутые за пределы крайней правой позиции, отбрасываются, а крайний левый бит передается в позиции, освобожденные слева.</span><span class="sxs-lookup"><span data-stu-id="16f1a-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="16f1a-117">Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые позиции будут установлены на единицу.</span><span class="sxs-lookup"><span data-stu-id="16f1a-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="16f1a-118">Если `variableorproperty` имеет положительное значение или если его тип данных не является типом без знака, освобождаемые позиции устанавливаются в ноль.</span><span class="sxs-lookup"><span data-stu-id="16f1a-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="16f1a-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="16f1a-119">Overloading</span></span>  
 <span data-ttu-id="16f1a-120">[Оператор > >](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="16f1a-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="16f1a-121">Перегрузка оператора `>>` влияет на поведение оператора `>>=`.</span><span class="sxs-lookup"><span data-stu-id="16f1a-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="16f1a-122">Если в коде используется `>>=` в классе или структуре, которая перегружает `>>`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="16f1a-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="16f1a-123">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="16f1a-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16f1a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="16f1a-124">Example</span></span>  
 <span data-ttu-id="16f1a-125">В следующем примере оператор `>>=` используется для сдвига битового шаблона `Integer` переменной вправо на указанное значение и присваивает результат переменной.</span><span class="sxs-lookup"><span data-stu-id="16f1a-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="16f1a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="16f1a-126">See also</span></span>

- [<span data-ttu-id="16f1a-127">Оператор >></span><span class="sxs-lookup"><span data-stu-id="16f1a-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="16f1a-128">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="16f1a-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="16f1a-129">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="16f1a-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="16f1a-130">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16f1a-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="16f1a-131">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="16f1a-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="16f1a-132">Операторы</span><span class="sxs-lookup"><span data-stu-id="16f1a-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
