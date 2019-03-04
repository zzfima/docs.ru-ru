---
title: Справочник по C#. Оператор *=
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967390"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b4752-102">Оператор \*= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b4752-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="b4752-103">Оператор присваивания умножения.</span><span class="sxs-lookup"><span data-stu-id="b4752-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="b4752-104">Выражение, использующее оператор `*=`, такое как</span><span class="sxs-lookup"><span data-stu-id="b4752-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="b4752-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="b4752-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="b4752-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b4752-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="b4752-107">Для числовых типов [оператор \*](multiplication-operator.md) вычисляет результат двух операндов.</span><span class="sxs-lookup"><span data-stu-id="b4752-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="b4752-108">В следующем примере иллюстрируется использование оператора `*=`.</span><span class="sxs-lookup"><span data-stu-id="b4752-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="b4752-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="b4752-109">Operator overloadability</span></span>

<span data-ttu-id="b4752-110">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор умножения](multiplication-operator.md) `*`, оператор присваивания умножения `*=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="b4752-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="b4752-111">Определяемый пользователем тип не может перегружать оператор присваивания умножения явным образом.</span><span class="sxs-lookup"><span data-stu-id="b4752-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4752-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b4752-112">C# language specification</span></span>

<span data-ttu-id="b4752-113">Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4752-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4752-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b4752-114">See also</span></span>

- [<span data-ttu-id="b4752-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b4752-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4752-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b4752-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b4752-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b4752-117">C# Operators</span></span>](index.md)
