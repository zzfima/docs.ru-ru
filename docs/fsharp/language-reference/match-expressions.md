---
title: Выражения соответствия
description: Узнайте, как F# выражение match обеспечивает управление ветвлением, основанное на сравнении выражения с набором шаблонов.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627608"
---
# <a name="match-expressions"></a><span data-ttu-id="b5560-103">Выражения соответствия</span><span class="sxs-lookup"><span data-stu-id="b5560-103">Match expressions</span></span>

<span data-ttu-id="b5560-104">`match` Выражение обеспечивает управление ветвлением, основанное на сравнении выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b5560-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5560-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5560-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b5560-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5560-106">Remarks</span></span>

<span data-ttu-id="b5560-107">Выражения сопоставления шаблонов позволяют выполнять сложное ветвление на основе сравнения тестового выражения с набором шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b5560-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="b5560-108">В выражении выражение *теста* сравнивается с каждым шаблоном, а при обнаружении совпадения вычисляется соответствующее результирующее выражение, а итоговое значение возвращается в качестве значения выражения соответствия. `match`</span><span class="sxs-lookup"><span data-stu-id="b5560-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="b5560-109">Функция сопоставления шаблонов, показанная в предыдущем синтаксисе, представляет собой лямбда-выражение, в котором сопоставление шаблонов выполняется непосредственно над аргументом.</span><span class="sxs-lookup"><span data-stu-id="b5560-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="b5560-110">Функция сопоставления шаблонов, показанная в предыдущем синтаксисе, эквивалентна следующей.</span><span class="sxs-lookup"><span data-stu-id="b5560-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="b5560-111">Дополнительные сведения о лямбда-выражениях см [. в разделе Лямбда-выражения: Ключевое](./functions/lambda-expressions-the-fun-keyword.md)слово. `fun`</span><span class="sxs-lookup"><span data-stu-id="b5560-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="b5560-112">Весь набор шаблонов должен охватывать все возможные совпадения входной переменной.</span><span class="sxs-lookup"><span data-stu-id="b5560-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="b5560-113">Часто шаблон подстановочного знака (`_`) используется в качестве последнего шаблона для сопоставления с любыми ранее несовпадающими входными значениями.</span><span class="sxs-lookup"><span data-stu-id="b5560-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="b5560-114">В следующем коде показаны некоторые способы `match` использования выражения.</span><span class="sxs-lookup"><span data-stu-id="b5560-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="b5560-115">Справочные сведения и примеры всех возможных шаблонов, которые можно использовать, см. в разделе [сопоставление шаблонов](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="b5560-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="b5560-116">Условия для шаблонов</span><span class="sxs-lookup"><span data-stu-id="b5560-116">Guards on patterns</span></span>

<span data-ttu-id="b5560-117">`when` Предложение можно использовать для указания дополнительного условия, которым должна удовлетворять переменная для соответствия шаблону.</span><span class="sxs-lookup"><span data-stu-id="b5560-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="b5560-118">Такое предложение называется *условием*.</span><span class="sxs-lookup"><span data-stu-id="b5560-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="b5560-119">Выражение, следующее `when` за ключевым словом, не вычисляется, если в шаблон, связанный с этим условием, не установлено соответствие.</span><span class="sxs-lookup"><span data-stu-id="b5560-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="b5560-120">В следующем примере показано использование условия для указания числового диапазона для шаблона переменной.</span><span class="sxs-lookup"><span data-stu-id="b5560-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="b5560-121">Обратите внимание, что несколько условий объединяются с помощью логических операторов.</span><span class="sxs-lookup"><span data-stu-id="b5560-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="b5560-122">Обратите внимание, что, поскольку значения, отличные от литералов, не могут использоваться в шаблоне, необходимо использовать `when` предложение, если необходимо сравнить некоторую часть входных данных со значением.</span><span class="sxs-lookup"><span data-stu-id="b5560-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="b5560-123">Это продемонстрировано в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="b5560-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="b5560-124">Обратите внимание, что если шаблон объединения охватывается условием, условие применяется ко **всем** шаблонам, а не только к последнему.</span><span class="sxs-lookup"><span data-stu-id="b5560-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="b5560-125">Например, при наличии следующего кода условие `when a > 12` применяется `A a` к и `B a`:</span><span class="sxs-lookup"><span data-stu-id="b5560-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b5560-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b5560-126">See also</span></span>

- [<span data-ttu-id="b5560-127">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="b5560-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b5560-128">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="b5560-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b5560-129">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="b5560-129">Pattern Matching</span></span>](pattern-matching.md)
