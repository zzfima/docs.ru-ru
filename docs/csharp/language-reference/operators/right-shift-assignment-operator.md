---
title: '>>Оператор = — справочник по C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220917"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="48818-102">Оператор >>= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="48818-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="48818-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="48818-103">The right-shift assignment operator.</span></span>

<span data-ttu-id="48818-104">Выражение, использующее оператор `>>=`, такое как</span><span class="sxs-lookup"><span data-stu-id="48818-104">An expression using the `>>=` operator, such as</span></span>

```csharp
x >>= y
```

<span data-ttu-id="48818-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="48818-105">is equivalent to</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="48818-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="48818-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="48818-107">[Оператор `>>`](right-shift-operator.md) сдвигает первый операнд вправо на число битов, определяемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="48818-107">The [`>>` operator](right-shift-operator.md) shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="48818-108">В следующем примере иллюстрируется использование оператора `>>=`.</span><span class="sxs-lookup"><span data-stu-id="48818-108">The following example demonstrates the usage of the `>>=` operator:</span></span>

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="48818-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="48818-109">Operator overloadability</span></span>

<span data-ttu-id="48818-110">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `>>`](right-shift-operator.md), то оператор присваивания сдвига вправо `>>=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="48818-110">If a user-defined type [overloads](../keywords/operator.md) the [`>>` operator](right-shift-operator.md), the right-shift assignment operator `>>=` is implicitly overloaded.</span></span> <span data-ttu-id="48818-111">Пользовательский тип не может перегружать оператор присваивания сдвига вправо явным образом.</span><span class="sxs-lookup"><span data-stu-id="48818-111">A user-defined type cannot explicitly overload the right-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="48818-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="48818-112">C# language specification</span></span>

<span data-ttu-id="48818-113">Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="48818-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48818-114">См. также</span><span class="sxs-lookup"><span data-stu-id="48818-114">See also</span></span>

- [<span data-ttu-id="48818-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="48818-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="48818-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="48818-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="48818-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="48818-117">C# operators</span></span>](index.md)