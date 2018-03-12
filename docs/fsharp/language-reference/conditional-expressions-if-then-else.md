---
title: "Условные выражения. if... then...else (F#)"
description: "Дополнительные сведения о записи условные выражения на языке F # для выполнения различных ветвей кода."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 5823e46cd13053fcd31f94f2d79d1f7470ca5118
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="944a2-104">Условные выражения. `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="944a2-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="944a2-105">`if...then...else` Выражение выполняет различные ветви кода и имеет разные значения в зависимости от заданного логического выражения.</span><span class="sxs-lookup"><span data-stu-id="944a2-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="944a2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="944a2-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="944a2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="944a2-107">Remarks</span></span>
<span data-ttu-id="944a2-108">В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* запускает.</span><span class="sxs-lookup"><span data-stu-id="944a2-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="944a2-109">В отличие от других языков, `if...then...else` конструктор является выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="944a2-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="944a2-110">Это означает, что она создает значение, которое является значением последнего выражения в ветвь, для которой выполняется.</span><span class="sxs-lookup"><span data-stu-id="944a2-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="944a2-111">Типы значений, получаемых в каждой ветви должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="944a2-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="944a2-112">При наличии без явного указания `else` ветви, но его тип — `unit`.</span><span class="sxs-lookup"><span data-stu-id="944a2-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="944a2-113">Таким образом Если тип `then` ветвь — любой тип, отличный от `unit`, должно быть `else` с тем же типом возврата ветви.</span><span class="sxs-lookup"><span data-stu-id="944a2-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="944a2-114">При объединении `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.</span><span class="sxs-lookup"><span data-stu-id="944a2-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="944a2-115">Пример</span><span class="sxs-lookup"><span data-stu-id="944a2-115">Example</span></span>
<span data-ttu-id="944a2-116">Следующий пример показывает, как использовать `if...then...else` выражение.</span><span class="sxs-lookup"><span data-stu-id="944a2-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="944a2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="944a2-117">See Also</span></span>
[<span data-ttu-id="944a2-118">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="944a2-118">F# Language Reference</span></span>](index.md)

