---
title: Оператор &amp;= (справочник по C#)
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980613"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="91754-102">Оператор &amp;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="91754-102">&amp;= Operator (C# Reference)</span></span>

<span data-ttu-id="91754-103">Оператор присваивания И.</span><span class="sxs-lookup"><span data-stu-id="91754-103">The AND assignment operator.</span></span>

<span data-ttu-id="91754-104">Выражение, использующее оператор `&=`, такое как</span><span class="sxs-lookup"><span data-stu-id="91754-104">An expression using the `&=` operator, such as</span></span>

```csharp
x &= y
```

<span data-ttu-id="91754-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="91754-105">is equivalent to</span></span>

```csharp
x = x & y
```

<span data-ttu-id="91754-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="91754-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="91754-107">Для целочисленных операндов [`&`оператор ](and-operator.md) вычисляет побитовую логическую операцию И; для операндов типа [bool](../keywords/bool.md) оператор вычисляет логическую операцию И.</span><span class="sxs-lookup"><span data-stu-id="91754-107">For integer operands, the [`&` operator](and-operator.md) computes the bitwise logical AND of its operands; for [bool](../keywords/bool.md) operands, it computes the logical AND of its operands.</span></span>

<span data-ttu-id="91754-108">В следующем примере иллюстрируется использование оператора `&=`.</span><span class="sxs-lookup"><span data-stu-id="91754-108">The following example demonstrates the usage of the `&=` operator:</span></span>

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a><span data-ttu-id="91754-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="91754-109">Operator overloadability</span></span>

<span data-ttu-id="91754-110">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `&`](and-operator.md), то оператор присваивания И `&=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="91754-110">If a user-defined type [overloads](../keywords/operator.md) the [`&` operator](and-operator.md), the AND assignment operator `&=` is implicitly overloaded.</span></span> <span data-ttu-id="91754-111">Определяемый пользователем тип не может перегружать оператор присваивания И явным образом.</span><span class="sxs-lookup"><span data-stu-id="91754-111">A user-defined type cannot explicitly overload the AND assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="91754-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="91754-112">C# language specification</span></span>

<span data-ttu-id="91754-113">Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="91754-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91754-114">См. также</span><span class="sxs-lookup"><span data-stu-id="91754-114">See also</span></span>

- [<span data-ttu-id="91754-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="91754-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="91754-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="91754-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="91754-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="91754-117">C# Operators</span></span>](index.md)
