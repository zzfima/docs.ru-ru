---
title: Циклы. Выражение for...to
description: См. в разделе как F# for... выражение используется для итерации в цикле по диапазону значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 5b7bb9bac659ddf1d457be1ce17e90a2593666de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645237"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="b3b08-103">Циклы. Выражение for...to</span><span class="sxs-lookup"><span data-stu-id="b3b08-103">Loops: for...to Expression</span></span>

<span data-ttu-id="b3b08-104">`for...to` Выражение используется для циклической итерации по диапазону значений переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="b3b08-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3b08-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3b08-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="b3b08-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3b08-106">Remarks</span></span>

<span data-ttu-id="b3b08-107">Тип идентификатора выводится из типа *запустить* и *Готово* выражения.</span><span class="sxs-lookup"><span data-stu-id="b3b08-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="b3b08-108">Типы для этих выражений должны быть 32-разрядных целых чисел.</span><span class="sxs-lookup"><span data-stu-id="b3b08-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="b3b08-109">Несмотря на то что технически выражения, `for...to` больше напоминает традиционный оператор в процедурном языке программирования.</span><span class="sxs-lookup"><span data-stu-id="b3b08-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="b3b08-110">Тип возвращаемого значения для *телом выражения* должно быть `unit`.</span><span class="sxs-lookup"><span data-stu-id="b3b08-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="b3b08-111">Ниже приведены примеры различных вариантов использования `for...to` выражение.</span><span class="sxs-lookup"><span data-stu-id="b3b08-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="b3b08-112">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="b3b08-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="b3b08-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b3b08-113">See also</span></span>

- [<span data-ttu-id="b3b08-114">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="b3b08-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b3b08-115">Циклы. `for...in` Выражение</span><span class="sxs-lookup"><span data-stu-id="b3b08-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="b3b08-116">Циклы. `while...do` Выражение</span><span class="sxs-lookup"><span data-stu-id="b3b08-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
