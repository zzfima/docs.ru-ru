---
title: Оператор +=
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 31a6da163061b905b8ffddcfc4b44978f5cdd55e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350305"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0c3a8-102">Оператор += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c3a8-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="0c3a8-103">Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="0c3a8-104">Можно также использовать для сцепления `String` выражения с `String` переменной или свойством и назначения результата переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c3a8-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0c3a8-106">Части</span><span class="sxs-lookup"><span data-stu-id="0c3a8-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="0c3a8-107">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-107">Required.</span></span> <span data-ttu-id="0c3a8-108">Любая числовая или `String` переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="0c3a8-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-109">Required.</span></span> <span data-ttu-id="0c3a8-110">Любое числовое или `String` выражение.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c3a8-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="0c3a8-111">Remarks</span></span>  
 <span data-ttu-id="0c3a8-112">Элемент в левой части оператора `+=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="0c3a8-113">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="0c3a8-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="0c3a8-114">Оператор `+=` добавляет значение справа к переменной или свойству слева и присваивает результат переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="0c3a8-115">Оператор `+=` также можно использовать для сцепления выражения `String` справа с переменной `String` или свойством слева и назначения результата переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c3a8-116">При использовании оператора `+=`, возможно, не удастся определить, будет ли выполняться сложение или объединение строк.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="0c3a8-117">Используйте оператор `&=` для объединения, чтобы избежать неоднозначности и предоставить код для самостоятельного документирования.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="0c3a8-118">Этот оператор присваивания неявно выполняет расширяющие, но не сужающие преобразования, если среда компиляции применяет строгую семантику.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="0c3a8-119">Дополнительные сведения об этих преобразованиях см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="0c3a8-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="0c3a8-120">Дополнительные сведения о семантике строгих и неразрешений см. в разделе [оператор Option строгий](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0c3a8-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="0c3a8-121">Если семантика разрешений разрешена, оператор `+=` неявно выполняет различные строковые и числовые преобразования, идентичные значениям, выполняемым оператором `+`.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="0c3a8-122">Дополнительные сведения об этих преобразованиях см. в разделе [оператор +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0c3a8-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0c3a8-123">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="0c3a8-123">Overloading</span></span>  
 <span data-ttu-id="0c3a8-124">Оператор `+` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0c3a8-125">Перегрузка оператора `+` влияет на поведение оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="0c3a8-126">Если в коде используется `+=` в классе или структуре, которая перегружает `+`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0c3a8-127">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0c3a8-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c3a8-128">Пример</span><span class="sxs-lookup"><span data-stu-id="0c3a8-128">Example</span></span>  
 <span data-ttu-id="0c3a8-129">В следующем примере оператор `+=` используется для объединения значения одной переменной с другой.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="0c3a8-130">Первая часть использует `+=` с числовыми переменными для добавления одного значения в другое.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="0c3a8-131">Во второй части используется `+=` с переменными `String` для сцепления одного значения с другим.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="0c3a8-132">В обоих случаях результат присваивается первой переменной.</span><span class="sxs-lookup"><span data-stu-id="0c3a8-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="0c3a8-133">Значение `num1` теперь равно 13, а значение `str1` теперь равно "103".</span><span class="sxs-lookup"><span data-stu-id="0c3a8-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3a8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0c3a8-134">See also</span></span>

- [<span data-ttu-id="0c3a8-135">Оператор +</span><span class="sxs-lookup"><span data-stu-id="0c3a8-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="0c3a8-136">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="0c3a8-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="0c3a8-137">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="0c3a8-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="0c3a8-138">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="0c3a8-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="0c3a8-139">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c3a8-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0c3a8-140">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="0c3a8-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0c3a8-141">Операторы</span><span class="sxs-lookup"><span data-stu-id="0c3a8-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
