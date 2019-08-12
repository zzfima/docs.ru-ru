---
title: Оператор ?:. Справочник по C#
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 923591634599a6bbac74d43b105f4e46b492fa1a
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796464"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a6ee7-102">Оператор ?: (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a6ee7-102">?: operator (C# reference)</span></span>

<span data-ttu-id="a6ee7-103">Условный оператор `?:`, известный как тернарный условный оператор, вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений, в зависимости от того, чему равно значение логического выражения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="a6ee7-104">Начиная с C# 7.2, [условное выражение REF](#conditional-ref-expression) возвращает ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="a6ee7-105">Для условного оператора используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="a6ee7-106">Выражение `condition` должно принимать значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="a6ee7-107">Если `condition` принимает значение `true`, вычисляется выражение `consequent`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="a6ee7-108">Если `condition` принимает значение `false`, вычисляется выражение `alternative`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="a6ee7-109">Вычисляется только выражение `consequent` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="a6ee7-110">Параметры `consequent` и `alternative` должны быть одинакового типа, или должно существовать неявное преобразование из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="a6ee7-111">Условный оператор имеет правую ассоциативность, то есть выражение формы.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="a6ee7-112">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="a6ee7-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="a6ee7-113">Вы можете использовать следующий мнемонический прием, чтобы запомнить, как оценивается условный оператор:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="a6ee7-114">В следующем примере иллюстрируется использование условного оператора:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="a6ee7-115">Условное выражение REF</span><span class="sxs-lookup"><span data-stu-id="a6ee7-115">Conditional ref expression</span></span>

<span data-ttu-id="a6ee7-116">Начиная с C# 7.2, условное выражение REF можно использовать для того, чтобы вернуть ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-116">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="a6ee7-117">Можно назначить эту ссылку [ссылочной локальной переменной](../keywords/ref.md#ref-locals) или [ссылочной локальной переменной только для чтения](../keywords/ref.md#ref-readonly-locals) или же использовать ее как [возвращаемое ссылочное значение](../keywords/ref.md#reference-return-values) или как [`ref` параметр метода](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="a6ee7-117">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="a6ee7-118">Для условного выражения REF используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="a6ee7-119">Подобно исходному условному оператору, условное выражение REF вычисляет только одно из двух выражений: `consequent` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="a6ee7-120">Для условного выражения REF тип `consequent` и `alternative` должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="a6ee7-121">В следующем примере иллюстрируется использование условного выражения REF:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalRef)]

<span data-ttu-id="a6ee7-122">Дополнительные сведения см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="a6ee7-122">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="a6ee7-123">Условный оператор и оператор `if..else`</span><span class="sxs-lookup"><span data-stu-id="a6ee7-123">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="a6ee7-124">Если использовать условный оператор с оператором [if-else](../keywords/if-else.md), может получиться более лаконичный код в случаях, когда необходимо условно вычислить значение.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-124">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="a6ee7-125">В следующем примере иллюстрируются два вида классификации целого числа как положительного или отрицательного:</span><span class="sxs-lookup"><span data-stu-id="a6ee7-125">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="a6ee7-126">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="a6ee7-126">Operator overloadability</span></span>

<span data-ttu-id="a6ee7-127">Условный оператор не может быть перегружен.</span><span class="sxs-lookup"><span data-stu-id="a6ee7-127">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a6ee7-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a6ee7-128">C# language specification</span></span>

<span data-ttu-id="a6ee7-129">Дополнительные сведения см. в разделе [Условный оператор](~/_csharplang/spec/expressions.md#conditional-operator) статьи [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a6ee7-129">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6ee7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ee7-130">See also</span></span>

- [<span data-ttu-id="a6ee7-131">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a6ee7-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a6ee7-132">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a6ee7-132">C# operators</span></span>](index.md)
- [<span data-ttu-id="a6ee7-133">if-else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a6ee7-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="a6ee7-134">[Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="a6ee7-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="a6ee7-135">Оператор ??</span><span class="sxs-lookup"><span data-stu-id="a6ee7-135">?? operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="a6ee7-136">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="a6ee7-136">ref keyword</span></span>](../keywords/ref.md)
