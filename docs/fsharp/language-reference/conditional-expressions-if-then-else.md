---
title: Условные выражения. if... then...else (F#)
description: Вы можете научиться писать условных выражений в F# для выполнения различных ветвей кода.
ms.date: 05/16/2016
ms.openlocfilehash: 10e4224bef772f00520cf5a0fff2f2920147c2fc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "44177605"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="4e424-103">Условные выражения. `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="4e424-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="4e424-104">`if...then...else` Выражение выполняет различные ветви кода и имеет другое значение в зависимости от заданного логического выражения.</span><span class="sxs-lookup"><span data-stu-id="4e424-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e424-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e424-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="4e424-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e424-106">Remarks</span></span>

<span data-ttu-id="4e424-107">В приведенном выше синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* выполняется.</span><span class="sxs-lookup"><span data-stu-id="4e424-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="4e424-108">В отличие от других языков, `if...then...else` конструкция представляет собой выражение, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="4e424-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="4e424-109">Это означает, что она формирует значение, которое является значением последнего выражения в ветвь, которая выполняет.</span><span class="sxs-lookup"><span data-stu-id="4e424-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="4e424-110">Типы значений, получаемых в каждой ветви должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="4e424-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="4e424-111">Если имеется без явного указания `else` ветви, его тип — `unit`.</span><span class="sxs-lookup"><span data-stu-id="4e424-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="4e424-112">Таким образом Если тип `then` ветвь — это любой тип, отличное от `unit`, должна существовать `else` ветви с тем же типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="4e424-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="4e424-113">При объединении в `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.</span><span class="sxs-lookup"><span data-stu-id="4e424-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="4e424-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4e424-114">Example</span></span>

<span data-ttu-id="4e424-115">В следующем примере показано, как использовать `if...then...else` выражение.</span><span class="sxs-lookup"><span data-stu-id="4e424-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="4e424-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4e424-116">See also</span></span>

- [<span data-ttu-id="4e424-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="4e424-117">F# Language Reference</span></span>](index.md)
