---
title: Циклы. Выражение for...to (F#)
description: См. в разделе как F# for... выражение используется для итерации в цикле по диапазону значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43800473"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="3cea7-103">Циклы. Выражение for...to</span><span class="sxs-lookup"><span data-stu-id="3cea7-103">Loops: for...to Expression</span></span>

<span data-ttu-id="3cea7-104">`for...to` Выражение используется для циклической итерации по диапазону значений переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="3cea7-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cea7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cea7-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="3cea7-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cea7-106">Remarks</span></span>

<span data-ttu-id="3cea7-107">Тип идентификатора выводится из типа *запустить* и *Готово* выражения.</span><span class="sxs-lookup"><span data-stu-id="3cea7-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="3cea7-108">Типы для этих выражений должны быть 32-разрядных целых чисел.</span><span class="sxs-lookup"><span data-stu-id="3cea7-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="3cea7-109">Несмотря на то что технически выражения, `for...to` больше напоминает традиционный оператор в процедурном языке программирования.</span><span class="sxs-lookup"><span data-stu-id="3cea7-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="3cea7-110">Тип возвращаемого значения для *телом выражения* должно быть `unit`.</span><span class="sxs-lookup"><span data-stu-id="3cea7-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="3cea7-111">Ниже приведены примеры различных вариантов использования `for...to` выражение.</span><span class="sxs-lookup"><span data-stu-id="3cea7-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="3cea7-112">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="3cea7-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="3cea7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3cea7-113">See also</span></span>

- [<span data-ttu-id="3cea7-114">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="3cea7-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3cea7-115">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="3cea7-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="3cea7-116">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="3cea7-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
