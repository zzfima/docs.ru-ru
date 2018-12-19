---
title: + Оператор. Справочник по C#
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 92e20dad8ae6358f71137e955bb80e3641a66a54
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237757"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8fbe5-102">Оператор + (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8fbe5-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="8fbe5-103">Оператор `+` поддерживается в двух формах: унарный оператор сложения или бинарный оператор сложения.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="8fbe5-104">Оператор унарного сложения</span><span class="sxs-lookup"><span data-stu-id="8fbe5-104">Unary plus operator</span></span>

<span data-ttu-id="8fbe5-105">Унарный оператор `+` возвращает значение полученного операнда.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-105">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="8fbe5-106">Он поддерживается всеми числовыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-106">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="8fbe5-107">Арифметическое сложение</span><span class="sxs-lookup"><span data-stu-id="8fbe5-107">Numeric addition</span></span>

<span data-ttu-id="8fbe5-108">Для числовых типов оператор `+` вычисляет сумму двух операндов:</span><span class="sxs-lookup"><span data-stu-id="8fbe5-108">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="8fbe5-109">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="8fbe5-109">String concatenation</span></span>

<span data-ttu-id="8fbe5-110">Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-110">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="8fbe5-111">В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):</span><span class="sxs-lookup"><span data-stu-id="8fbe5-111">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="8fbe5-112">Объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="8fbe5-112">Delegate combination</span></span>

<span data-ttu-id="8fbe5-113">Для типов [делегата](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала первый, а затем второй операнд.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-113">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="8fbe5-114">Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`).</span><span class="sxs-lookup"><span data-stu-id="8fbe5-114">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="8fbe5-115">Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:</span><span class="sxs-lookup"><span data-stu-id="8fbe5-115">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="8fbe5-116">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="8fbe5-116">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8fbe5-117">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="8fbe5-117">Operator overloadability</span></span>

<span data-ttu-id="8fbe5-118">Пользовательские типы могут [перегружать](../keywords/operator.md) унарный и бинарный операторы `+`.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-118">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="8fbe5-119">При перегрузке бинарного оператора `+` неявно перегружается и соответствующий [оператор присвоения сложения](addition-assignment-operator.md) `+=`.</span><span class="sxs-lookup"><span data-stu-id="8fbe5-119">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8fbe5-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8fbe5-120">C# language specification</span></span>

<span data-ttu-id="8fbe5-121">См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="8fbe5-121">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fbe5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8fbe5-122">See also</span></span>

- [<span data-ttu-id="8fbe5-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8fbe5-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8fbe5-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8fbe5-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8fbe5-125">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8fbe5-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="8fbe5-126">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="8fbe5-126">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="8fbe5-127">Практическое руководство. Сцепка нескольких строк</span><span class="sxs-lookup"><span data-stu-id="8fbe5-127">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="8fbe5-128">Делегаты</span><span class="sxs-lookup"><span data-stu-id="8fbe5-128">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="8fbe5-129">Инструкции checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="8fbe5-129">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
