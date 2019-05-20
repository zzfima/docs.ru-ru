---
title: Справочник по C#. Оператор ()
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 412d3ac5296eaf7d67f4a5e84b7a42f6fa5bb8a5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633855"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c0b10-102">Оператор (). Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c0b10-102">() operator (C# Reference)</span></span>

<span data-ttu-id="c0b10-103">Круглые скобки, `()`, обычно используются для вызова метода или делегата либо же в выражениях приведения.</span><span class="sxs-lookup"><span data-stu-id="c0b10-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="c0b10-104">Кроме того, с помощью круглых скобок можно указывать порядок выполнения операций в выражении.</span><span class="sxs-lookup"><span data-stu-id="c0b10-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="c0b10-105">Дополнительные сведения см. в разделе [Добавление скобок](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) руководства по использованию [операторов](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="c0b10-106">Список операторов, упорядоченных по уровню приоритета, см. в статье [Операторы в C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="c0b10-107">Вызов метода</span><span class="sxs-lookup"><span data-stu-id="c0b10-107">Method invocation</span></span>

<span data-ttu-id="c0b10-108">Приведенный ниже пример демонстрирует вызов делегата и метода с аргументами или без них.</span><span class="sxs-lookup"><span data-stu-id="c0b10-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="c0b10-109">Круглые скобки также можно использовать при вызове [конструктора](../../programming-guide/classes-and-structs/constructors.md) с оператором [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="c0b10-110">См. дополнительные сведения о [методах](../../programming-guide/classes-and-structs/methods.md)</span><span class="sxs-lookup"><span data-stu-id="c0b10-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="c0b10-111">и [делегатах](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="c0b10-112">Выражение приведения</span><span class="sxs-lookup"><span data-stu-id="c0b10-112">Cast expression</span></span>

<span data-ttu-id="c0b10-113">Выражение приведения формы `(T)E` вызывает оператор преобразования для преобразования значения выражения `E` в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="c0b10-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="c0b10-114">Если явного преобразования из типа `E` в тип `T` не существует, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="c0b10-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="c0b10-115">Сведения о том, как определять операторы преобразования, см. в статьях о ключевых словах [explicit](../keywords/explicit.md) и [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="c0b10-116">В приведенном ниже примере показано преобразование типов между числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="c0b10-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="c0b10-117">См. дополнительные сведения о [предопределенных явных числовых преобразованиях](../keywords/explicit-numeric-conversions-table.md),</span><span class="sxs-lookup"><span data-stu-id="c0b10-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="c0b10-118">[приведении и преобразовании типов](../../programming-guide/types/casting-and-type-conversions.md) и [операторах преобразования](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c0b10-119">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="c0b10-119">Operator overloadability</span></span>

<span data-ttu-id="c0b10-120">Оператор `()` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c0b10-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c0b10-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c0b10-121">C# language specification</span></span>

<span data-ttu-id="c0b10-122">Дополнительные сведения см. в разделах [Выражения вызова](~/_csharplang/spec/expressions.md#invocation-expressions) и [Выражения приведения](~/_csharplang/spec/expressions.md#cast-expressions) [спецификации C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0b10-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0b10-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c0b10-123">See also</span></span>

- [<span data-ttu-id="c0b10-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c0b10-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0b10-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c0b10-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c0b10-126">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="c0b10-126">C# Operators</span></span>](index.md)
