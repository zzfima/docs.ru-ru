---
title: + и += (операторы). Справочник по C#
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
ms.openlocfilehash: 258adc45fc6874cca5829479eef1196ebea1e300
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347980"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="fd3ec-102">Операторы + и +=. Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fd3ec-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="fd3ec-103">Оператор `+` поддерживается встроенными числовыми типами, типом [string](../keywords/string.md) и типами [delegate](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="fd3ec-104">Сведения об арифметическом операторе `+` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор сложения +](arithmetic-operators.md#addition-operator-) в статье [Арифметические операторы](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="fd3ec-105">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="fd3ec-105">String concatenation</span></span>

<span data-ttu-id="fd3ec-106">Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="fd3ec-107">В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):</span><span class="sxs-lookup"><span data-stu-id="fd3ec-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="fd3ec-108">Объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="fd3ec-108">Delegate combination</span></span>

<span data-ttu-id="fd3ec-109">Для операндов того же типа [delegate](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала левый, а затем правый операнд.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="fd3ec-110">Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="fd3ec-111">Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:</span><span class="sxs-lookup"><span data-stu-id="fd3ec-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="fd3ec-112">Для удаления делегатов используйте [оператор `-`](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="fd3ec-113">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="fd3ec-114">Оператор присваивания сложения (+=)</span><span class="sxs-lookup"><span data-stu-id="fd3ec-114">Addition assignment operator +=</span></span>

<span data-ttu-id="fd3ec-115">Выражение, использующее оператор `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="fd3ec-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="fd3ec-116">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="fd3ec-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="fd3ec-117">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="fd3ec-118">В следующем примере иллюстрируется использование оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="fd3ec-119">Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="fd3ec-120">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="fd3ec-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="fd3ec-121">Operator overloadability</span></span>

<span data-ttu-id="fd3ec-122">Определяемый пользователем тип может [перегружать](../keywords/operator.md) оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-122">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="fd3ec-123">При перегрузке бинарного оператора `+` неявно перегружается и соответствующий оператор `+=`.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="fd3ec-124">Определяемый пользователем тип не может перегружать оператор `+=` явным образом.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd3ec-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fd3ec-125">C# language specification</span></span>

<span data-ttu-id="fd3ec-126">См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd3ec-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fd3ec-127">See also</span></span>

- [<span data-ttu-id="fd3ec-128">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fd3ec-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fd3ec-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="fd3ec-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="fd3ec-130">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="fd3ec-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="fd3ec-131">Практическое руководство. Сцепка нескольких строк</span><span class="sxs-lookup"><span data-stu-id="fd3ec-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="fd3ec-132">Делегаты</span><span class="sxs-lookup"><span data-stu-id="fd3ec-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="fd3ec-133">События</span><span class="sxs-lookup"><span data-stu-id="fd3ec-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="fd3ec-134">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="fd3ec-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="fd3ec-135">Операторы - и -=</span><span class="sxs-lookup"><span data-stu-id="fd3ec-135">- and -= operators</span></span>](subtraction-operator.md)
