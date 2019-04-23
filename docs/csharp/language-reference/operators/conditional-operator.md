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
ms.openlocfilehash: c03fa202b413c98230ba70ca7a0b709d7865cb91
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427387"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d2fd6-102">?: Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="d2fd6-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="d2fd6-103">Условный оператор `?:`, известный как тернарный условный оператор, вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений, в зависимости от того, чему равно значение логического выражения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="d2fd6-104">Начиная с C# 7.2, [условное выражение REF](#conditional-ref-expression) возвращает ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="d2fd6-105">Для условного оператора используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d2fd6-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="d2fd6-106">Выражение `condition` должно принимать значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="d2fd6-107">Если `condition` принимает значение `true`, вычисляется выражение `consequent`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="d2fd6-108">Если `condition` принимает значение `false`, вычисляется выражение `alternative`, а результат становится результатом операции.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="d2fd6-109">Вычисляется только выражение `consequent` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="d2fd6-110">Параметры `consequent` и `alternative` должны быть одинакового типа, или должно существовать неявное преобразование из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="d2fd6-111">Условный оператор имеет правую ассоциативность, то есть выражение формы.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="d2fd6-112">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="d2fd6-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="d2fd6-113">В следующем примере иллюстрируется использование условного оператора:</span><span class="sxs-lookup"><span data-stu-id="d2fd6-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="d2fd6-114">Условное выражение REF</span><span class="sxs-lookup"><span data-stu-id="d2fd6-114">Conditional ref expression</span></span>

<span data-ttu-id="d2fd6-115">Начиная с C# 7.2, условное выражение REF можно использовать для того, чтобы вернуть ссылку на результат одного из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="d2fd6-116">Можно назначить эту ссылку [ссылочной локальной переменной](../keywords/ref.md#ref-locals) или [ссылочной локальной переменной только для чтения](../keywords/ref.md#ref-readonly-locals) или же использовать ее как [возвращаемое ссылочное значение](../keywords/ref.md#reference-return-values) или как [`ref` параметр метода](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="d2fd6-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="d2fd6-117">Для условного выражения REF используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d2fd6-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="d2fd6-118">Подобно исходному условному оператору, условное выражение REF вычисляет только одно из двух выражений: `consequent` или `alternative`.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="d2fd6-119">Для условного выражения REF тип `consequent` и `alternative` должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-119">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="d2fd6-120">В следующем примере иллюстрируется использование условного выражения REF:</span><span class="sxs-lookup"><span data-stu-id="d2fd6-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="d2fd6-121">Дополнительные сведения см. в [примечании к предлагаемой функции](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="d2fd6-121">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="d2fd6-122">Условный оператор и оператор `if..else`</span><span class="sxs-lookup"><span data-stu-id="d2fd6-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="d2fd6-123">Если использовать условный оператор с оператором [if-else](../keywords/if-else.md), может получиться более лаконичный код в случаях, когда необходимо условно вычислить значение.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="d2fd6-124">В следующем примере иллюстрируются два вида классификации целого числа как положительного или отрицательного:</span><span class="sxs-lookup"><span data-stu-id="d2fd6-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="d2fd6-125">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="d2fd6-125">Operator overloadability</span></span>

<span data-ttu-id="d2fd6-126">Условный оператор не может быть перегружен.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d2fd6-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d2fd6-127">C# language specification</span></span>

<span data-ttu-id="d2fd6-128">Дополнительные сведения см. в разделе [Условный оператор](~/_csharplang/spec/expressions.md#conditional-operator) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2fd6-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2fd6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d2fd6-129">See also</span></span>

- [<span data-ttu-id="d2fd6-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d2fd6-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d2fd6-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d2fd6-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d2fd6-132">Операторы C#</span><span class="sxs-lookup"><span data-stu-id="d2fd6-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d2fd6-133">if-else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d2fd6-133">if-else statement</span></span>](../keywords/if-else.md)
- [<span data-ttu-id="d2fd6-134">?.</span><span class="sxs-lookup"><span data-stu-id="d2fd6-134">?.</span></span> <span data-ttu-id="d2fd6-135">Операторы ?. и ?[]</span><span class="sxs-lookup"><span data-stu-id="d2fd6-135">and ?[] Operators</span></span>](null-conditional-operators.md)
- [<span data-ttu-id="d2fd6-136">??</span><span class="sxs-lookup"><span data-stu-id="d2fd6-136">??</span></span> <span data-ttu-id="d2fd6-137">Оператор</span><span class="sxs-lookup"><span data-stu-id="d2fd6-137">Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="d2fd6-138">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="d2fd6-138">ref keyword</span></span>](../keywords/ref.md)
