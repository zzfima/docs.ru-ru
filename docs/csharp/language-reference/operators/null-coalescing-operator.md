---
title: ?? и ??= — справочник по C#
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
ms.openlocfilehash: b3d56c6c08443d344002b8e780a72fc547c316bb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712654"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="f54ba-103">??</span><span class="sxs-lookup"><span data-stu-id="f54ba-103">??</span></span> <span data-ttu-id="f54ba-104">и ??= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f54ba-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="f54ba-105">Оператор объединения с NULL `??` возвращает значение своего операнда слева, если его значение не равно `null`. В противном случае он вычисляет операнд справа и возвращает его результат.</span><span class="sxs-lookup"><span data-stu-id="f54ba-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="f54ba-106">Оператор `??` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="f54ba-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="f54ba-107">Начиная с C# 8.0 можно использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f54ba-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="f54ba-108">Оператор `??=` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="f54ba-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="f54ba-109">Левый операнд оператора `??=` должен быть переменной, [свойством](../../programming-guide/classes-and-structs/properties.md) или элементом [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f54ba-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="f54ba-110">В C# 7.3 и более ранних версий левый операнд оператора `??` должен иметь либо [ссылочный тип](../keywords/reference-types.md), либо [тип значения, допускающий значение NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="f54ba-110">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="f54ba-111">Начиная с C# 8.0 это требование заменяется следующим: тип левого операнда операторов `??` и `??=` не может быть типом значения, не допускающим значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f54ba-111">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="f54ba-112">В частности, начиная с версии C# 8.0, можно использовать операторы объединения со значением NULL с неограниченными параметрами типа:</span><span class="sxs-lookup"><span data-stu-id="f54ba-112">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="f54ba-113">Операторы объединения со значением NULL являются правоассоциативными.</span><span class="sxs-lookup"><span data-stu-id="f54ba-113">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="f54ba-114">То есть выражения в форме</span><span class="sxs-lookup"><span data-stu-id="f54ba-114">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="f54ba-115">вычисляются как</span><span class="sxs-lookup"><span data-stu-id="f54ba-115">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="f54ba-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="f54ba-116">Examples</span></span>

<span data-ttu-id="f54ba-117">Операторы `??` и `??=` могут быть полезны в таких случаях:</span><span class="sxs-lookup"><span data-stu-id="f54ba-117">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="f54ba-118">В выражениях с [NULL-условными операторами ?. и ?[]](member-access-operators.md#null-conditional-operators--and-) можно использовать оператор `null`, чтобы задать альтернативное выражение для оценки на случай, если результат выражения с NULL-условной операцией будет равен `??`.</span><span class="sxs-lookup"><span data-stu-id="f54ba-118">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="f54ba-119">Когда вы работаете с [типами, допускающими значение NULL](../builtin-types/nullable-value-types.md), и вам нужно указать значение базового типа значения, используйте оператор `??` для указания значения, возвращаемого в том случае, если значение типа, допускающего значение NULL, равно `null`.</span><span class="sxs-lookup"><span data-stu-id="f54ba-119">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="f54ba-120">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="f54ba-120">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="f54ba-121">Начиная с версии C# 7.0, можно сократить код проверки аргументов, используя [выражение `throw`](../keywords/throw.md#the-throw-expression) в качестве правого операнда оператора `??`:</span><span class="sxs-lookup"><span data-stu-id="f54ba-121">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="f54ba-122">В предыдущем примере также демонстрируются способы определения свойства с помощью [членов, заданных выражениями](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="f54ba-122">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="f54ba-123">Начиная с версии C# 8.0, можно использовать оператор `??=` для замены кода формы</span><span class="sxs-lookup"><span data-stu-id="f54ba-123">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="f54ba-124">следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f54ba-124">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="f54ba-125">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="f54ba-125">Operator overloadability</span></span>

<span data-ttu-id="f54ba-126">Операторы `??` и `??=` не могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="f54ba-126">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f54ba-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f54ba-127">C# language specification</span></span>

<span data-ttu-id="f54ba-128">Дополнительные сведения об операторе `??` см. в разделе об [операторе объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f54ba-128">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="f54ba-129">См. сведения об операторе `??=` в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="f54ba-129">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f54ba-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f54ba-130">See also</span></span>

- [<span data-ttu-id="f54ba-131">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f54ba-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f54ba-132">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f54ba-132">C# operators</span></span>](index.md)
- <span data-ttu-id="f54ba-133">[Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="f54ba-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="f54ba-134">Оператор ?</span><span class="sxs-lookup"><span data-stu-id="f54ba-134">?: operator</span></span>](conditional-operator.md)
