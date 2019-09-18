---
title: ?? и ??= — справочник по C#
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 1e94038a41a6a6cc19be6c67bff2891397793fb3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924680"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="bdea1-103">??</span><span class="sxs-lookup"><span data-stu-id="bdea1-103">??</span></span> <span data-ttu-id="bdea1-104">и ??= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bdea1-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="bdea1-105">Оператор объединения с NULL `??` возвращает значение своего операнда слева, если его значение не равно `null`. В противном случае он вычисляет операнд справа и возвращает его результат.</span><span class="sxs-lookup"><span data-stu-id="bdea1-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="bdea1-106">Оператор `??` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="bdea1-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="bdea1-107">Начиная с C# 8.0 можно использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="bdea1-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="bdea1-108">Оператор `??=` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="bdea1-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="bdea1-109">Левый операнд оператора `??=` должен быть переменной, [свойством](../../programming-guide/classes-and-structs/properties.md) или элементом [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="bdea1-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span> <span data-ttu-id="bdea1-110">Дополнительные сведения о присваивании объединения со значением NULL см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="bdea1-110">For more information about null-coalescing assignment, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

<span data-ttu-id="bdea1-111">В C# 7.3 и более ранних версий левый операнд оператора `??` должен иметь либо ссылочный тип, либо [тип значения, допускающий значение NULL](../../programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="bdea1-111">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a reference type or a [nullable value type](../../programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="bdea1-112">Начиная с C# 8.0 это требование заменяется следующим: тип левого операнда операторов `??` и `??=` не может быть типом значения, не допускающим значение NULL.</span><span class="sxs-lookup"><span data-stu-id="bdea1-112">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="bdea1-113">В частности, можно использовать операторы объединения со значением NULL с неограниченными параметрами типа в C# 8.0 и более поздних версиях:</span><span class="sxs-lookup"><span data-stu-id="bdea1-113">In particular, you can use the null-coalescing operators with unconstrained type parameters in C# 8.0 and later:</span></span>

[!code-csharp[unconstrained type parameter](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="bdea1-114">Операторы объединения со значением NULL являются правоассоциативными.</span><span class="sxs-lookup"><span data-stu-id="bdea1-114">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="bdea1-115">То есть выражения в форме</span><span class="sxs-lookup"><span data-stu-id="bdea1-115">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="bdea1-116">вычисляются как</span><span class="sxs-lookup"><span data-stu-id="bdea1-116">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="bdea1-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="bdea1-117">Examples</span></span>

<span data-ttu-id="bdea1-118">Операторы `??` и `??=` могут быть полезны в таких случаях:</span><span class="sxs-lookup"><span data-stu-id="bdea1-118">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="bdea1-119">В выражениях с [NULL-условными операторами ?. и ?[]](member-access-operators.md#null-conditional-operators--and-) можно использовать оператор объединения с NULL, чтобы задать альтернативное выражение для оценки на случай, если результат выражения с NULL-условной операцией будет равен `null`.</span><span class="sxs-lookup"><span data-stu-id="bdea1-119">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="bdea1-120">При работе с [типами, допускающими значение NULL](../../programming-guide/nullable-types/index.md), и если нужно указать значение базового типа значения, используйте оператор объединения с NULL для указания значения, возвращаемого в том случае, если значение типа, допускающего значение NULL, равно `null`.</span><span class="sxs-lookup"><span data-stu-id="bdea1-120">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="bdea1-121">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="bdea1-121">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="bdea1-122">Начиная с C# 7.0 можно сократить код проверки аргументов, используя [выражение `throw`](../keywords/throw.md#the-throw-expression) в качестве правого операнда оператора объединения с NULL:</span><span class="sxs-lookup"><span data-stu-id="bdea1-122">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="bdea1-123">В предыдущем примере также демонстрируются способы определения свойства с помощью [членов, заданных выражениями](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="bdea1-123">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="bdea1-124">Начиная с C# 8.0 можно использовать оператор `??=` для замены кода формы</span><span class="sxs-lookup"><span data-stu-id="bdea1-124">Starting with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="bdea1-125">на новый код:</span><span class="sxs-lookup"><span data-stu-id="bdea1-125">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="bdea1-126">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="bdea1-126">Operator overloadability</span></span>

<span data-ttu-id="bdea1-127">Операторы `??` и `??=` не могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="bdea1-127">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bdea1-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bdea1-128">C# language specification</span></span>

<span data-ttu-id="bdea1-129">Дополнительные сведения об операторе `??` см. в разделе об [операторе объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bdea1-129">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdea1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bdea1-130">See also</span></span>

- [<span data-ttu-id="bdea1-131">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bdea1-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bdea1-132">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="bdea1-132">C# operators</span></span>](index.md)
- <span data-ttu-id="bdea1-133">[Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="bdea1-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="bdea1-134">Оператор ?</span><span class="sxs-lookup"><span data-stu-id="bdea1-134">?: operator</span></span>](conditional-operator.md)
