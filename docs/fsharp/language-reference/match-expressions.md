---
title: 'Выражения Match (F #)'
description: 'Узнайте, как выражения F # совпадения обеспечивает управление ветвлением, которое основывается на сравнении выражения с набором шаблонов.'
ms.date: 04/19/2018
ms.openlocfilehash: 22cc4b7a87a60d8a5dcbe05ac5abec5560a37516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565182"
---
# <a name="match-expressions"></a><span data-ttu-id="1a922-103">Выражения Match</span><span class="sxs-lookup"><span data-stu-id="1a922-103">Match expressions</span></span>

<span data-ttu-id="1a922-104">`match` Выражение позволяет управлять ветвлением основывается на сравнении выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1a922-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a922-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a922-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="1a922-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a922-106">Remarks</span></span>

<span data-ttu-id="1a922-107">Соответствующие шаблону выражения позволяют выполнять сложное ветвление на основе сравнения тестового выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1a922-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="1a922-108">В `match` выражение, *тестовое выражение* сравнивается с каждым шаблоном, в свою очередь, а также при обнаружении совпадения, соответствующий *результирующее выражение* вычисляется и итоговое значение возвращены в качестве значения выражения match.</span><span class="sxs-lookup"><span data-stu-id="1a922-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="1a922-109">Функция, показанный в предыдущем синтаксисе сопоставления шаблонов является лямбда-выражение, в какой шаблон соответствия выполняется непосредственно в аргументе.</span><span class="sxs-lookup"><span data-stu-id="1a922-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="1a922-110">Функция, показанный в предыдущем синтаксисе сопоставления шаблонов, эквивалентно следующему.</span><span class="sxs-lookup"><span data-stu-id="1a922-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="1a922-111">Дополнительные сведения о лямбда-выражениях см. в разделе [лямбда-выражения: `fun` ключевое слово](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="1a922-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="1a922-112">Полный набор шаблонов должен охватывать все возможные сочетания входной переменной.</span><span class="sxs-lookup"><span data-stu-id="1a922-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="1a922-113">Как правило, этот шаблон используется (`_`) как последний шаблон для сопоставления любого ранее несопоставленных входных значений.</span><span class="sxs-lookup"><span data-stu-id="1a922-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="1a922-114">Следующий код иллюстрирует некоторые ситуации, в которых `match` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="1a922-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="1a922-115">Справочные сведения и примеры всех шаблонов, которые можно использовать, в разделе [соответствие шаблону](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="1a922-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="1a922-116">Условия при работе с шаблонами</span><span class="sxs-lookup"><span data-stu-id="1a922-116">Guards on patterns</span></span>

<span data-ttu-id="1a922-117">Можно использовать `when` предложений, чтобы задать дополнительное условие, которому должна удовлетворять переменной должно соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="1a922-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="1a922-118">Такое предложение называется *защиты*.</span><span class="sxs-lookup"><span data-stu-id="1a922-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="1a922-119">Следующее выражение `when` ключевое слово вычисляется только в том случае, если соответствие шаблона, связанного с этим условием.</span><span class="sxs-lookup"><span data-stu-id="1a922-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="1a922-120">Следующий пример иллюстрирует использование условия для задания числового диапазона шаблона переменной.</span><span class="sxs-lookup"><span data-stu-id="1a922-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="1a922-121">Обратите внимание, что несколько условий объединяются с помощью логических операторов.</span><span class="sxs-lookup"><span data-stu-id="1a922-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="1a922-122">Обратите внимание, что поскольку значения, отличные от литералы не может использоваться в шаблоне, необходимо использовать `when` предложение, если необходимо сравнить некоторая часть входных данных со значением.</span><span class="sxs-lookup"><span data-stu-id="1a922-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="1a922-123">Это показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="1a922-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="1a922-124">Обратите внимание на то, когда шаблон объединения охватывается условие, условие применяется к **все** шаблонов, а не только последний из них.</span><span class="sxs-lookup"><span data-stu-id="1a922-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="1a922-125">Например, имеется следующий код, условие `when a > 12` относится как к `A a` и `B a`:</span><span class="sxs-lookup"><span data-stu-id="1a922-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1a922-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1a922-126">See also</span></span>

[<span data-ttu-id="1a922-127">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="1a922-127">F# Language Reference</span></span>](index.md)  
[<span data-ttu-id="1a922-128">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="1a922-128">Active Patterns</span></span>](active-patterns.md)  
[<span data-ttu-id="1a922-129">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="1a922-129">Pattern Matching</span></span>](pattern-matching.md)  
