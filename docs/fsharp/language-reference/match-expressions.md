---
title: Выражения Match
description: Узнайте, как F# выражение соответствия позволяет управлять ветвлением основывается на сравнении выражения с набором шаблонов.
ms.date: 04/19/2018
ms.openlocfilehash: 69ff8de1617e6b55d112d310bfcd8b2f967b6e8a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645202"
---
# <a name="match-expressions"></a><span data-ttu-id="f6bf5-103">Выражения Match</span><span class="sxs-lookup"><span data-stu-id="f6bf5-103">Match expressions</span></span>

<span data-ttu-id="f6bf5-104">`match` Выражение позволяет управлять ветвлением основывается на сравнении выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6bf5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6bf5-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="f6bf5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6bf5-106">Remarks</span></span>

<span data-ttu-id="f6bf5-107">Выражения сопоставления шаблонов разрешают использовать сложные на основе сравнения тестового выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="f6bf5-108">В `match` выражения, *тестовое выражение* сравнивается с каждым шаблоном, в свою очередь, а также при обнаружении совпадения, соответствующий *результирующее выражение* вычисляется и результирующее значение равно возвращены в качестве значения выражения match.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="f6bf5-109">Сопоставление функции показано в предыдущем синтаксисе шаблонов является лямбда-выражение, в какой шаблон соответствия выполняется непосредственно в аргументе.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="f6bf5-110">Функция, показанный в предыдущем синтаксисе сопоставления шаблонов, эквивалентно следующему.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="f6bf5-111">Дополнительные сведения о лямбда-выражениях см. в разделе [лямбда-выражения: `fun` Ключевое слово](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="f6bf5-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="f6bf5-112">Полный набор шаблонов должны охватывать все возможные сочетания входной переменной.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="f6bf5-113">Часто, используйте шаблон подстановочного знака (`_`) как последний шаблон в соответствии с любой ранее несопоставленных входных значений.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="f6bf5-114">В следующем коде показано несколько способов, в котором `match` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="f6bf5-115">Справочные сведения и примеры всех шаблонов, которые можно использовать, см. в разделе [сопоставление шаблонов](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="f6bf5-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="f6bf5-116">Условия при работе с шаблонами</span><span class="sxs-lookup"><span data-stu-id="f6bf5-116">Guards on patterns</span></span>

<span data-ttu-id="f6bf5-117">Можно использовать `when` предложение, чтобы указать дополнительное условие, переменная должна удовлетворять должно соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="f6bf5-118">Такое предложение называется *защиты*.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="f6bf5-119">Выражение, следующее `when` ключевое слово вычисляется только в том случае, если соответствие шаблона, связанного с этим условием.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="f6bf5-120">Следующий пример иллюстрирует использование условия для задания числового диапазона шаблона переменной.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="f6bf5-121">Обратите внимание на то, что несколько условий объединяются с помощью логических операторов.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="f6bf5-122">Обратите внимание, что поскольку значения, отличные от литералы не может использоваться в шаблоне, необходимо использовать `when` предложение, если необходимо сравнить некоторая часть входных данных со значением.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="f6bf5-123">Это показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f6bf5-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="f6bf5-124">Обратите внимание, что при шаблон объединения Охватываемой условие, условие применяется к **все** шаблонов, а не только последний.</span><span class="sxs-lookup"><span data-stu-id="f6bf5-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="f6bf5-125">Например, имеется следующий код, условие `when a > 12` применяется к обоим `A a` и `B a`:</span><span class="sxs-lookup"><span data-stu-id="f6bf5-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="f6bf5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f6bf5-126">See also</span></span>

- [<span data-ttu-id="f6bf5-127">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f6bf5-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f6bf5-128">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f6bf5-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="f6bf5-129">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="f6bf5-129">Pattern Matching</span></span>](pattern-matching.md)
