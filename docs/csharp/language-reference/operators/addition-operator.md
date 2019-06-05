---
title: + и += (операторы) — справочник по C#
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300117"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="0ca9c-102">+ и += (операторы) (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0ca9c-102">+ and += operators (C# Reference)</span></span>

<span data-ttu-id="0ca9c-103">Оператор `+` поддерживается встроенными числовыми типами, типом [string](../keywords/string.md) и типами [delegate](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="0ca9c-104">Сведения об арифметическом операторе `+` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор сложения +](arithmetic-operators.md#addition-operator-) в статье [Арифметические операторы](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="0ca9c-105">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="0ca9c-105">String concatenation</span></span>

<span data-ttu-id="0ca9c-106">Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="0ca9c-107">В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):</span><span class="sxs-lookup"><span data-stu-id="0ca9c-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="0ca9c-108">Объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="0ca9c-108">Delegate combination</span></span>

<span data-ttu-id="0ca9c-109">Для операндов того же типа [delegate](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала первый, а затем второй операнд.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="0ca9c-110">Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="0ca9c-111">Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:</span><span class="sxs-lookup"><span data-stu-id="0ca9c-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="0ca9c-112">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-112">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="0ca9c-113">Оператор присваивания сложения (+=)</span><span class="sxs-lookup"><span data-stu-id="0ca9c-113">Addition assignment operator +=</span></span>

<span data-ttu-id="0ca9c-114">Выражение, использующее оператор `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="0ca9c-114">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="0ca9c-115">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="0ca9c-115">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="0ca9c-116">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-116">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="0ca9c-117">В следующем примере иллюстрируется использование оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-117">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

<span data-ttu-id="0ca9c-118">Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-118">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="0ca9c-119">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-119">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0ca9c-120">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="0ca9c-120">Operator overloadability</span></span>

<span data-ttu-id="0ca9c-121">Определяемый пользователем тип может [перегружать](../keywords/operator.md) оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-121">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="0ca9c-122">При перегрузке бинарного оператора `+` неявно перегружается и соответствующий оператор `+=`.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-122">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="0ca9c-123">Определяемый пользователем тип не может перегружать оператор `+=` явным образом.</span><span class="sxs-lookup"><span data-stu-id="0ca9c-123">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0ca9c-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0ca9c-124">C# language specification</span></span>

<span data-ttu-id="0ca9c-125">См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ca9c-125">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ca9c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0ca9c-126">See also</span></span>

- [<span data-ttu-id="0ca9c-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0ca9c-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0ca9c-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0ca9c-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0ca9c-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0ca9c-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0ca9c-130">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="0ca9c-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="0ca9c-131">Практическое руководство. Сцепка нескольких строк</span><span class="sxs-lookup"><span data-stu-id="0ca9c-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="0ca9c-132">Делегаты</span><span class="sxs-lookup"><span data-stu-id="0ca9c-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="0ca9c-133">События</span><span class="sxs-lookup"><span data-stu-id="0ca9c-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="0ca9c-134">Инструкции checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="0ca9c-134">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="0ca9c-135">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="0ca9c-135">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="0ca9c-136">Операторы - и -=</span><span class="sxs-lookup"><span data-stu-id="0ca9c-136">- and -= operators</span></span>](subtraction-operator.md)
