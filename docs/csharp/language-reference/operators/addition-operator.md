---
title: + Оператор (ссылка C#)
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: ae2774d96bc50afa271fffdea445e640e68c3647
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192308"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="adff1-102">Оператор + (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="adff1-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="adff1-103">Оператор `+` поддерживается в двух формах: унарный оператор сложения или бинарный оператор сложения.</span><span class="sxs-lookup"><span data-stu-id="adff1-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

<span data-ttu-id="adff1-104">Пользовательские типы могут [перегружать](../keywords/operator.md) унарный и бинарный операторы `+`.</span><span class="sxs-lookup"><span data-stu-id="adff1-104">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="adff1-105">При перегрузке бинарного оператора `+` неявно перегружается и соответствующий [оператор присвоения сложения](addition-assignment-operator.md) `+=`.</span><span class="sxs-lookup"><span data-stu-id="adff1-105">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="adff1-106">Оператор унарного сложения</span><span class="sxs-lookup"><span data-stu-id="adff1-106">Unary plus operator</span></span>

<span data-ttu-id="adff1-107">Унарный оператор `+` возвращает значение полученного операнда.</span><span class="sxs-lookup"><span data-stu-id="adff1-107">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="adff1-108">Он поддерживается всеми числовыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="adff1-108">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="adff1-109">Арифметическое сложение</span><span class="sxs-lookup"><span data-stu-id="adff1-109">Numeric addition</span></span>

<span data-ttu-id="adff1-110">Для числовых типов оператор `+` вычисляет сумму двух операндов:</span><span class="sxs-lookup"><span data-stu-id="adff1-110">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="adff1-111">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="adff1-111">String concatenation</span></span>

<span data-ttu-id="adff1-112">Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.</span><span class="sxs-lookup"><span data-stu-id="adff1-112">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="adff1-113">В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):</span><span class="sxs-lookup"><span data-stu-id="adff1-113">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="adff1-114">Объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="adff1-114">Delegate combination</span></span>

<span data-ttu-id="adff1-115">Для типов [делегата](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала первый, а затем второй операнд.</span><span class="sxs-lookup"><span data-stu-id="adff1-115">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="adff1-116">Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`).</span><span class="sxs-lookup"><span data-stu-id="adff1-116">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="adff1-117">Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:</span><span class="sxs-lookup"><span data-stu-id="adff1-117">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="adff1-118">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="adff1-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="adff1-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="adff1-119">C# language specification</span></span>

<span data-ttu-id="adff1-120">См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="adff1-120">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="adff1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="adff1-121">See also</span></span>

- [<span data-ttu-id="adff1-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="adff1-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="adff1-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="adff1-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="adff1-124">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="adff1-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="adff1-125">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="adff1-125">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="adff1-126">Практическое руководство. Сцепка нескольких строк</span><span class="sxs-lookup"><span data-stu-id="adff1-126">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="adff1-127">Делегаты</span><span class="sxs-lookup"><span data-stu-id="adff1-127">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="adff1-128">Операторы checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="adff1-128">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
