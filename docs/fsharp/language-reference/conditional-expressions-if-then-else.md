---
title: Условные выражения. if... then...else (F#)
description: 'Дополнительные сведения о записи условные выражения на языке F # для выполнения различных ветвей кода.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="08e46-103">Условные выражения. `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="08e46-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="08e46-104">`if...then...else` Выражение выполняет различные ветви кода и имеет разные значения в зависимости от заданного логического выражения.</span><span class="sxs-lookup"><span data-stu-id="08e46-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="08e46-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08e46-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="08e46-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="08e46-106">Remarks</span></span>
<span data-ttu-id="08e46-107">В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* запускает.</span><span class="sxs-lookup"><span data-stu-id="08e46-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="08e46-108">В отличие от других языков, `if...then...else` конструктор является выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="08e46-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="08e46-109">Это означает, что она создает значение, которое является значением последнего выражения в ветвь, для которой выполняется.</span><span class="sxs-lookup"><span data-stu-id="08e46-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="08e46-110">Типы значений, получаемых в каждой ветви должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="08e46-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="08e46-111">При наличии без явного указания `else` ветви, но его тип — `unit`.</span><span class="sxs-lookup"><span data-stu-id="08e46-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="08e46-112">Таким образом Если тип `then` ветвь — любой тип, отличный от `unit`, должно быть `else` с тем же типом возврата ветви.</span><span class="sxs-lookup"><span data-stu-id="08e46-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="08e46-113">При объединении `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.</span><span class="sxs-lookup"><span data-stu-id="08e46-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="08e46-114">Пример</span><span class="sxs-lookup"><span data-stu-id="08e46-114">Example</span></span>
<span data-ttu-id="08e46-115">Следующий пример показывает, как использовать `if...then...else` выражение.</span><span class="sxs-lookup"><span data-stu-id="08e46-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="08e46-116">См. также</span><span class="sxs-lookup"><span data-stu-id="08e46-116">See Also</span></span>
[<span data-ttu-id="08e46-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="08e46-117">F# Language Reference</span></span>](index.md)

