---
title: Справочник по C#. Оператор /=
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286524"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b87c4-102">Оператор /= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b87c4-102">/= Operator (C# Reference)</span></span>

<span data-ttu-id="b87c4-103">Оператор присваивания деления.</span><span class="sxs-lookup"><span data-stu-id="b87c4-103">The division assignment operator.</span></span>

<span data-ttu-id="b87c4-104">Выражение, использующее оператор `/=`, такое как</span><span class="sxs-lookup"><span data-stu-id="b87c4-104">An expression using the `/=` operator, such as</span></span>

```csharp
x /= y
```

<span data-ttu-id="b87c4-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="b87c4-105">is equivalent to</span></span>

```csharp
x = x / y
```

<span data-ttu-id="b87c4-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b87c4-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="b87c4-107">[Оператор деления](division-operator.md) (`/`) делит первый операнд на второй.</span><span class="sxs-lookup"><span data-stu-id="b87c4-107">The [division operator](division-operator.md) `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="b87c4-108">Он поддерживается всеми числовыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="b87c4-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="b87c4-109">В следующем примере иллюстрируется использование оператора `/=`.</span><span class="sxs-lookup"><span data-stu-id="b87c4-109">The following example demonstrates the usage of the `/=` operator:</span></span>

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="b87c4-110">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="b87c4-110">Operator overloadability</span></span>

<span data-ttu-id="b87c4-111">Если пользовательский тип [перегружает](../keywords/operator.md) [оператор деления](division-operator.md) `/`, оператор присваивания деления `/=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="b87c4-111">If a user-defined type [overloads](../keywords/operator.md) the [division operator](division-operator.md) `/`, the division assignment operator `/=` is implicitly overloaded.</span></span> <span data-ttu-id="b87c4-112">Пользовательский тип не может перегружать оператор присваивания деления явным образом.</span><span class="sxs-lookup"><span data-stu-id="b87c4-112">A user-defined type cannot explicitly overload the division assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b87c4-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b87c4-113">C# language specification</span></span>

<span data-ttu-id="b87c4-114">Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b87c4-114">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b87c4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b87c4-115">See also</span></span>

- [<span data-ttu-id="b87c4-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b87c4-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b87c4-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b87c4-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b87c4-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b87c4-118">C# Operators</span></span>](index.md)
