---
title: ?? Справочник по C#. Оператор -
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816010"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4e9f8-103">??</span><span class="sxs-lookup"><span data-stu-id="4e9f8-103">??</span></span> <span data-ttu-id="4e9f8-104">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4e9f8-104">operator (C# Reference)</span></span>

<span data-ttu-id="4e9f8-105">Оператор объединения с NULL `??` возвращает значение своего операнда слева, если его значение не равно `null`. В противном случае он вычисляет операнд справа и возвращает его результат.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="4e9f8-106">Оператор `??` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="4e9f8-107">Оператор объединения с NULL имеет правую ассоциативность, то есть выражение формы</span><span class="sxs-lookup"><span data-stu-id="4e9f8-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="4e9f8-108">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="4e9f8-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="4e9f8-109">Оператор `??` может быть полезен в таких случаях:</span><span class="sxs-lookup"><span data-stu-id="4e9f8-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="4e9f8-110">В выражениях с [NULL-условными операторами ?. и ?[]](member-access-operators.md#null-conditional-operators--and-) можно использовать оператор объединения с NULL, чтобы задать альтернативное выражение для оценки на случай, если результат выражения с NULL-условной операцией будет равен `null`.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="4e9f8-111">При работе с [типами, допускающими значение NULL](../../programming-guide/nullable-types/index.md), и если нужно указать значение базового типа значения, используйте оператор объединения с NULL для указания значения, возвращаемого в том случае, если значение типа, допускающего значение NULL, равно `null`.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="4e9f8-112">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="4e9f8-113">Начиная с C# 7.0 можно сократить код проверки аргументов, используя [выражение `throw`](../keywords/throw.md#the-throw-expression) в качестве правого операнда оператора объединения с NULL:</span><span class="sxs-lookup"><span data-stu-id="4e9f8-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="4e9f8-114">В предыдущем примере также демонстрируются способы определения свойства с помощью [членов, заданных выражениями](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="4e9f8-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4e9f8-115">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="4e9f8-115">Operator overloadability</span></span>

<span data-ttu-id="4e9f8-116">Оператор объединения с NULL перегружать нельзя.</span><span class="sxs-lookup"><span data-stu-id="4e9f8-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4e9f8-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4e9f8-117">C# language specification</span></span>

<span data-ttu-id="4e9f8-118">Дополнительные сведения см. в разделе об [операторе объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4e9f8-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e9f8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4e9f8-119">See also</span></span>

- [<span data-ttu-id="4e9f8-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4e9f8-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4e9f8-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4e9f8-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4e9f8-122">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4e9f8-122">C# operators</span></span>](index.md)
- <span data-ttu-id="4e9f8-123">[Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="4e9f8-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="4e9f8-124">Оператор ?</span><span class="sxs-lookup"><span data-stu-id="4e9f8-124">?: operator</span></span>](conditional-operator.md)
