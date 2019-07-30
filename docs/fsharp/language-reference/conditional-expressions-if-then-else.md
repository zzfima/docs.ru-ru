---
title: 'Условные выражения: if... затем... Кроме'
description: Сведения о написании условных выражений F# в для выполнения различных ветвей кода.
ms.date: 05/16/2016
ms.openlocfilehash: 825149bf296eded3cc2b4d8847ba4d82bea40cdc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630390"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="d5023-103">Условные выражения:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="d5023-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="d5023-104">`if...then...else` Выражение выполняет различные ветви кода, а также вычисляет различные значения в зависимости от заданного логического выражения.</span><span class="sxs-lookup"><span data-stu-id="d5023-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5023-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5023-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="d5023-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5023-106">Remarks</span></span>

<span data-ttu-id="d5023-107">В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение принимает `true`значение; в противном случае — *Expression2* .</span><span class="sxs-lookup"><span data-stu-id="d5023-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="d5023-108">В отличие от других языков, `if...then...else` конструкция является выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="d5023-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="d5023-109">Это означает, что он создает значение, которое является значением последнего выражения в ветви, в которой выполняется.</span><span class="sxs-lookup"><span data-stu-id="d5023-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="d5023-110">Типы значений, создаваемых в каждой ветви, должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="d5023-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="d5023-111">Если явная `else` ветвь отсутствует, ее тип — `unit`.</span><span class="sxs-lookup"><span data-stu-id="d5023-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="d5023-112">Поэтому, если тип `then` ветви отличается от `unit`типа `else` , необходимо наличие ветви с таким же типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d5023-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="d5023-113">При совместном `if...then...else` связывании выражений можно использовать ключевое слово `elif` , а `else if`не. они эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="d5023-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="d5023-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d5023-114">Example</span></span>

<span data-ttu-id="d5023-115">В следующем примере показано, `if...then...else` как использовать выражение.</span><span class="sxs-lookup"><span data-stu-id="d5023-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="d5023-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d5023-116">See also</span></span>

- [<span data-ttu-id="d5023-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="d5023-117">F# Language Reference</span></span>](index.md)
