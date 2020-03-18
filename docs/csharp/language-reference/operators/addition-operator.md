---
title: + и += (операторы). Справочник по C#
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
ms.openlocfilehash: cafd07f4b4aefdcc4b43750d61c155fe3d65aa46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398103"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="78a0b-102">Операторы + и +=. Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="78a0b-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="78a0b-103">Операторы `+` и `+=` поддерживаются встроенными [целыми](../builtin-types/integral-numeric-types.md) числовыми типами и числовыми типами [с плавающей запятой](../builtin-types/floating-point-numeric-types.md), а также [строковым](../builtin-types/reference-types.md#the-string-type) типом и типами[делегатов](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="78a0b-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="78a0b-104">Сведения об арифметическом операторе `+` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор сложения +](arithmetic-operators.md#addition-operator-) в статье [Арифметические операторы](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="78a0b-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="78a0b-105">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="78a0b-105">String concatenation</span></span>

<span data-ttu-id="78a0b-106">Если один или оба операнда имеют тип [string](../builtin-types/reference-types.md#the-string-type), оператор `+` сцепляет строковые представления этих операндов.</span><span class="sxs-lookup"><span data-stu-id="78a0b-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](snippets/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="78a0b-107">В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):</span><span class="sxs-lookup"><span data-stu-id="78a0b-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](snippets/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="78a0b-108">Объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="78a0b-108">Delegate combination</span></span>

<span data-ttu-id="78a0b-109">Для операндов того же типа [delegate](../builtin-types/reference-types.md#the-delegate-type) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала левый, а затем правый операнд.</span><span class="sxs-lookup"><span data-stu-id="78a0b-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="78a0b-110">Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`).</span><span class="sxs-lookup"><span data-stu-id="78a0b-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="78a0b-111">Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:</span><span class="sxs-lookup"><span data-stu-id="78a0b-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](snippets/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="78a0b-112">Для удаления делегатов используйте [оператор `-`](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="78a0b-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="78a0b-113">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="78a0b-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="78a0b-114">Оператор присваивания сложения (+=)</span><span class="sxs-lookup"><span data-stu-id="78a0b-114">Addition assignment operator +=</span></span>

<span data-ttu-id="78a0b-115">Выражение, использующее оператор `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="78a0b-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="78a0b-116">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="78a0b-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="78a0b-117">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="78a0b-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="78a0b-118">В следующем примере иллюстрируется использование оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="78a0b-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](snippets/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="78a0b-119">Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="78a0b-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="78a0b-120">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="78a0b-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="78a0b-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="78a0b-121">Operator overloadability</span></span>

<span data-ttu-id="78a0b-122">Определяемый пользователем тип может [перегружать](operator-overloading.md) оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="78a0b-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="78a0b-123">При перегрузке бинарного оператора `+` неявно перегружается и соответствующий оператор `+=`.</span><span class="sxs-lookup"><span data-stu-id="78a0b-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="78a0b-124">Определяемый пользователем тип не может перегружать оператор `+=` явным образом.</span><span class="sxs-lookup"><span data-stu-id="78a0b-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="78a0b-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="78a0b-125">C# language specification</span></span>

<span data-ttu-id="78a0b-126">См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="78a0b-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78a0b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="78a0b-127">See also</span></span>

- [<span data-ttu-id="78a0b-128">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="78a0b-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="78a0b-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="78a0b-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="78a0b-130">Сцепка нескольких строк</span><span class="sxs-lookup"><span data-stu-id="78a0b-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="78a0b-131">События</span><span class="sxs-lookup"><span data-stu-id="78a0b-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="78a0b-132">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="78a0b-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="78a0b-133">Операторы - и -=</span><span class="sxs-lookup"><span data-stu-id="78a0b-133">- and -= operators</span></span>](subtraction-operator.md)
