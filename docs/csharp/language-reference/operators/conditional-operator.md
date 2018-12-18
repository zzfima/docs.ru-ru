---
title: '?: Справочник по C#. Оператор'
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
ms.openlocfilehash: ca61ee323d98ece1236d9072e14d02385fbdf9f8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241792"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="709a9-102">?: Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="709a9-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="709a9-103">Условный оператор `?:`, известный как тернарный условный оператор, вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений, в зависимости от того, чему равно значение логического выражения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="709a9-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="709a9-104">Начиная с C# 7.2, [условное выражение REF](#conditional-ref-expression) возвращает ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="709a9-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="709a9-105">Для условного оператора используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="709a9-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequence : alternative
```

<span data-ttu-id="709a9-106">Выражение `condition` должно принимать значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="709a9-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="709a9-107">Если `condition` принимает значение `true`, вычисляется выражение `consequence`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="709a9-107">If `condition` evaluates to `true`, the `consequence` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="709a9-108">Если `condition` принимает значение `false`, вычисляется выражение `alternative`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="709a9-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="709a9-109">Вычисляется только выражение `consequence` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="709a9-109">Only `consequence` or `alternative` is evaluated.</span></span>

<span data-ttu-id="709a9-110">Параметры `consequence` и `alternative` должны быть одинакового типа, или должно существовать неявное преобразование из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="709a9-110">The type of `consequence` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="709a9-111">Условный оператор имеет правую ассоциативность, то есть выражение формы.</span><span class="sxs-lookup"><span data-stu-id="709a9-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="709a9-112">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="709a9-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="709a9-113">В следующем примере иллюстрируется использование условного оператора:</span><span class="sxs-lookup"><span data-stu-id="709a9-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref condtional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="709a9-114">Условное выражение REF</span><span class="sxs-lookup"><span data-stu-id="709a9-114">Conditional ref expression</span></span>

<span data-ttu-id="709a9-115">Начиная с C# 7.2, условное выражение REF можно использовать для того, чтобы вернуть ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="709a9-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="709a9-116">Можно назначить эту ссылку [ссылочной локальной переменной](../keywords/ref.md#ref-locals) или [ссылочной локальной переменной только для чтения](../keywords/ref.md#ref-readonly-locals) или же использовать ее как [возвращаемое ссылочное значение](../keywords/ref.md#reference-return-values) или как [`ref` параметр метода](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="709a9-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="709a9-117">Для условного выражения REF используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="709a9-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequence : ref alternative
```

<span data-ttu-id="709a9-118">Подобно исходному условному оператору, условное выражение REF вычисляет только одно из двух выражений: `consequence` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="709a9-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequence` or `alternative`.</span></span>

<span data-ttu-id="709a9-119">Для условного выражения REF тип `consequence` и `alternative` должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="709a9-119">In the case of the conditional ref expression, the type of `consequence` and `alternative` must be the same.</span></span>

<span data-ttu-id="709a9-120">В следующем примере иллюстрируется использование условного выражения REF:</span><span class="sxs-lookup"><span data-stu-id="709a9-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="709a9-121">Дополнительные сведения см. в [примечании к предлагаемой функции](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="709a9-121">For more information, see the [feature proposal note](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="709a9-122">Условный оператор и оператор `if..else`</span><span class="sxs-lookup"><span data-stu-id="709a9-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="709a9-123">Если использовать условный оператор с оператором [if-else](../keywords/if-else.md), может получиться более лаконичный код в случаях, когда необходимо условно вычислить значение.</span><span class="sxs-lookup"><span data-stu-id="709a9-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="709a9-124">В следующем примере иллюстрируются два вида классификации целого числа как положительного или отрицательного:</span><span class="sxs-lookup"><span data-stu-id="709a9-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="709a9-125">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="709a9-125">Operator overloadability</span></span>

<span data-ttu-id="709a9-126">Условный оператор не может быть перегружен.</span><span class="sxs-lookup"><span data-stu-id="709a9-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="709a9-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="709a9-127">C# language specification</span></span>

<span data-ttu-id="709a9-128">Дополнительные сведения см. в разделе [Условный оператор](~/_csharplang/spec/expressions.md#conditional-operator) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="709a9-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="709a9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="709a9-129">See also</span></span>

- [<span data-ttu-id="709a9-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="709a9-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="709a9-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="709a9-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="709a9-132">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="709a9-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="709a9-133">if-else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="709a9-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="709a9-134">[Операторы ?. и ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="709a9-134">[?. and ?[] Operators](null-conditional-operators.md)</span></span>
- [<span data-ttu-id="709a9-135">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="709a9-135">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="709a9-136">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="709a9-136">ref keyword</span></span>](../keywords/ref.md)
