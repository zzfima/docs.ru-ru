---
title: Оператор <<= — справочник по C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219455"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="27902-102">Справочник по C#. Оператор \<\<=</span><span class="sxs-lookup"><span data-stu-id="27902-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="27902-103">Оператор присваивания сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="27902-103">The left-shift assignment operator.</span></span>

<span data-ttu-id="27902-104">Выражение, использующее оператор `<<=`, такое как</span><span class="sxs-lookup"><span data-stu-id="27902-104">An expression using the `<<=` operator, such as</span></span>

```csharp
x <<= y
```

<span data-ttu-id="27902-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="27902-105">is equivalent to</span></span>

```csharp
x = x << y
```

<span data-ttu-id="27902-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="27902-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="27902-107">[Оператор `<<`](left-shift-operator.md) сдвигает первый операнд влево на число битов, определяемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="27902-107">The [`<<` operator](left-shift-operator.md) shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="27902-108">В следующем примере иллюстрируется использование оператора `<<=`.</span><span class="sxs-lookup"><span data-stu-id="27902-108">The following example demonstrates the usage of the `<<=` operator:</span></span>

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="27902-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="27902-109">Operator overloadability</span></span>

<span data-ttu-id="27902-110">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `<<`](left-shift-operator.md), то оператор присваивания сдвига влево `<<=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="27902-110">If a user-defined type [overloads](../keywords/operator.md) the [`<<` operator](left-shift-operator.md), the left-shift assignment operator `<<=` is implicitly overloaded.</span></span> <span data-ttu-id="27902-111">Пользовательский тип не может перегружать оператор присваивания сдвига влево явным образом.</span><span class="sxs-lookup"><span data-stu-id="27902-111">A user-defined type cannot explicitly overload the left-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="27902-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="27902-112">C# language specification</span></span>

<span data-ttu-id="27902-113">Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="27902-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27902-114">См. также</span><span class="sxs-lookup"><span data-stu-id="27902-114">See also</span></span>

- [<span data-ttu-id="27902-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="27902-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27902-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="27902-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="27902-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="27902-117">C# Operators</span></span>](index.md)
