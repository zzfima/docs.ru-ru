---
title: "Выражения match (F#)"
description: "Узнайте, как выражения F # совпадения обеспечивает управление ветвлением, которое основывается на сравнении выражения с набором шаблонов."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="409e6-104">Выражения match</span><span class="sxs-lookup"><span data-stu-id="409e6-104">Match Expressions</span></span>

<span data-ttu-id="409e6-105">`match` Выражение позволяет управлять ветвлением основывается на сравнении выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="409e6-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="409e6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="409e6-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="409e6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="409e6-107">Remarks</span></span>

<span data-ttu-id="409e6-108">Соответствующие шаблону выражения позволяют выполнять сложное ветвление на основе сравнения тестового выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="409e6-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="409e6-109">В `match` выражение, *тестовое выражение* сравнивается с каждым шаблоном, в свою очередь, а также при обнаружении совпадения, соответствующий *результирующее выражение* вычисляется и итоговое значение возвращены в качестве значения выражения match.</span><span class="sxs-lookup"><span data-stu-id="409e6-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="409e6-110">Функция, показанный в предыдущем синтаксисе сопоставления шаблонов является лямбда-выражение, в какой шаблон соответствия выполняется непосредственно в аргументе.</span><span class="sxs-lookup"><span data-stu-id="409e6-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="409e6-111">Функция, показанный в предыдущем синтаксисе сопоставления шаблонов, эквивалентно следующему.</span><span class="sxs-lookup"><span data-stu-id="409e6-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="409e6-112">Дополнительные сведения о лямбда-выражениях см. в разделе [лямбда-выражения: `fun` ключевое слово](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="409e6-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="409e6-113">Полный набор шаблонов должен охватывать все возможные сочетания входной переменной.</span><span class="sxs-lookup"><span data-stu-id="409e6-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="409e6-114">Как правило, этот шаблон используется (`_`) как последний шаблон для сопоставления любого ранее несопоставленных входных значений.</span><span class="sxs-lookup"><span data-stu-id="409e6-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="409e6-115">Следующий код иллюстрирует некоторые ситуации, в которых `match` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="409e6-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="409e6-116">Справочные сведения и примеры всех шаблонов, которые можно использовать, в разделе [соответствие шаблону](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="409e6-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="409e6-117">Условия при работе с шаблонами</span><span class="sxs-lookup"><span data-stu-id="409e6-117">Guards on Patterns</span></span>

<span data-ttu-id="409e6-118">Можно использовать `when` предложений, чтобы задать дополнительное условие, которому должна удовлетворять переменной должно соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="409e6-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="409e6-119">Такое предложение называется *защиты*.</span><span class="sxs-lookup"><span data-stu-id="409e6-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="409e6-120">Следующее выражение `when` ключевое слово вычисляется только в том случае, если соответствие шаблона, связанного с этим условием.</span><span class="sxs-lookup"><span data-stu-id="409e6-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="409e6-121">Следующий пример иллюстрирует использование условия для задания числового диапазона шаблона переменной.</span><span class="sxs-lookup"><span data-stu-id="409e6-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="409e6-122">Обратите внимание, что несколько условий объединяются с помощью логических операторов.</span><span class="sxs-lookup"><span data-stu-id="409e6-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="409e6-123">Обратите внимание, что поскольку значения, отличные от литералы не может использоваться в шаблоне, необходимо использовать `when` предложение, если необходимо сравнить некоторая часть входных данных со значением.</span><span class="sxs-lookup"><span data-stu-id="409e6-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="409e6-124">Это показано в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="409e6-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="409e6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="409e6-125">See Also</span></span>

[<span data-ttu-id="409e6-126">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="409e6-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="409e6-127">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="409e6-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="409e6-128">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="409e6-128">Pattern Matching</span></span>](pattern-matching.md)
