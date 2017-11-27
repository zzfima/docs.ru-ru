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
ms.openlocfilehash: 3531a112eb53657d5e9102d5e5f3be988360b76e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="50c08-104">Условные выражения.`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="50c08-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="50c08-105">`if...then...else` Выражение выполняет различные ветви кода и имеет разные значения в зависимости от заданного логического выражения.</span><span class="sxs-lookup"><span data-stu-id="50c08-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="50c08-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50c08-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="50c08-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="50c08-107">Remarks</span></span>
<span data-ttu-id="50c08-108">В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* запускает.</span><span class="sxs-lookup"><span data-stu-id="50c08-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="50c08-109">В отличие от других языков, `if...then...else` конструктор является выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="50c08-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="50c08-110">Это означает, что она создает значение, которое является значением последнего выражения в ветвь, для которой выполняется.</span><span class="sxs-lookup"><span data-stu-id="50c08-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="50c08-111">Типы значений, получаемых в каждой ветви должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="50c08-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="50c08-112">При наличии без явного указания `else` ветви, но его тип — `unit`.</span><span class="sxs-lookup"><span data-stu-id="50c08-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="50c08-113">Таким образом Если тип `then` ветвь — любой тип, отличный от `unit`, должно быть `else` с тем же типом возврата ветви.</span><span class="sxs-lookup"><span data-stu-id="50c08-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="50c08-114">При объединении `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.</span><span class="sxs-lookup"><span data-stu-id="50c08-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="50c08-115">Пример</span><span class="sxs-lookup"><span data-stu-id="50c08-115">Example</span></span>
<span data-ttu-id="50c08-116">Следующий пример показывает, как использовать `if...then...else` выражение.</span><span class="sxs-lookup"><span data-stu-id="50c08-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
John
910 is less than 20
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="50c08-117">См. также</span><span class="sxs-lookup"><span data-stu-id="50c08-117">See Also</span></span>
[<span data-ttu-id="50c08-118">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="50c08-118">F# Language Reference</span></span>](index.md)

