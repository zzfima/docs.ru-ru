---
title: Оператор ^
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: b9860b7b6e076fc9c0288818aa9e4f2c0fc4c356
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331111"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9fa5f-102">Оператор ^ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fa5f-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="9fa5f-103">Порождает число в степень другого числа.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fa5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fa5f-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="9fa5f-105">Части</span><span class="sxs-lookup"><span data-stu-id="9fa5f-105">Parts</span></span>

`number`\
<span data-ttu-id="9fa5f-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-106">Required.</span></span> <span data-ttu-id="9fa5f-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="9fa5f-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-108">Required.</span></span> <span data-ttu-id="9fa5f-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="9fa5f-110">Результат</span><span class="sxs-lookup"><span data-stu-id="9fa5f-110">Result</span></span>

<span data-ttu-id="9fa5f-111">Результат `number` возводится в степень `exponent`, всегда как значение `Double`.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="9fa5f-112">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="9fa5f-112">Supported Types</span></span>

<span data-ttu-id="9fa5f-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-113">`Double`.</span></span> <span data-ttu-id="9fa5f-114">Операнды любого другого типа преобразуются в `Double`.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fa5f-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="9fa5f-115">Remarks</span></span>

<span data-ttu-id="9fa5f-116">Visual Basic всегда выполняет возведение в степень в [типе данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="9fa5f-117">Значение `exponent` может быть дробным, отрицательным или обоими.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="9fa5f-118">Если в одном выражении выполняется несколько возможного возведения в степень, то оператор `^` вычисляется так, как он встретился слева направо.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="9fa5f-119">Оператор `^` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9fa5f-120">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9fa5f-121">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="9fa5f-122">Пример</span><span class="sxs-lookup"><span data-stu-id="9fa5f-122">Example</span></span>

<span data-ttu-id="9fa5f-123">В следующем примере оператор `^` используется для возведения числа в степень экспоненты.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="9fa5f-124">Результатом является первый операнд, возведенный в степень второго.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="9fa5f-125">В предыдущем примере получены следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="9fa5f-126">для `exp1` задано значение 4 (2 в квадрате).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="9fa5f-127">для `exp2` задано значение 19683 (3 куб, затем значение Cube).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="9fa5f-128">для `exp3` задано значение-125 (-5 кубd).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="9fa5f-129">для параметра `exp4` задано значение 625 (от-5 до четвертой мощности).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="9fa5f-130">для `exp5` задано значение 2 (кубический корень из 8).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="9fa5f-131">для `exp6` установлено значение 0,5 (1,0, деленное на кубический корень из 8).</span><span class="sxs-lookup"><span data-stu-id="9fa5f-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="9fa5f-132">Обратите внимание на важность круглых скобок в выражениях из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="9fa5f-133">Из-за *приоритета операторов*Visual Basic обычно выполняет оператор `^` перед любыми другими, даже унарным оператором `–`.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="9fa5f-134">Если `exp4` и `exp6` были вычислены без скобок, они могли бы получить следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="9fa5f-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="9fa5f-135">`exp4 = -5 ^ 4` будет вычисляться как – (от 5 до четвертой мощности), что приведет к 625.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="9fa5f-136">`exp6 = 8 ^ -1.0 / 3.0` вычисляется как (от 8 до – 1 или 0,125), разделенного на 3,0, что приведет к 0.041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="9fa5f-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fa5f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9fa5f-137">See also</span></span>

- [<span data-ttu-id="9fa5f-138">Оператор ^=</span><span class="sxs-lookup"><span data-stu-id="9fa5f-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="9fa5f-139">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="9fa5f-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="9fa5f-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fa5f-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9fa5f-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="9fa5f-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9fa5f-142">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fa5f-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
