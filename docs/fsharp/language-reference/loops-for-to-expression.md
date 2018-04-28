---
title: Циклы. Выражение for...to (F#)
description: '. В разделе как F # оператор for... выражение используется для перебора в цикле диапазона значений переменной цикла.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a><span data-ttu-id="49224-103">Циклы. Выражение for...to</span><span class="sxs-lookup"><span data-stu-id="49224-103">Loops: for...to Expression</span></span>

<span data-ttu-id="49224-104">`for...to` Выражение используется для перебора в цикле диапазона значений переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="49224-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="49224-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49224-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="49224-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="49224-106">Remarks</span></span>
<span data-ttu-id="49224-107">Тип идентификатора выводится из типа *запустить* и *Готово* выражения.</span><span class="sxs-lookup"><span data-stu-id="49224-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="49224-108">Типы для этих выражений должны быть 32-разрядных целых чисел.</span><span class="sxs-lookup"><span data-stu-id="49224-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="49224-109">Несмотря на то что технически выражения, `for...to` — это больше похоже на традиционный оператор в императивном языке программирования.</span><span class="sxs-lookup"><span data-stu-id="49224-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="49224-110">Тип возвращаемого значения для *выражение тела* должен быть `unit`.</span><span class="sxs-lookup"><span data-stu-id="49224-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="49224-111">В следующих примерах показано различные способы использования `for...to` выражение.</span><span class="sxs-lookup"><span data-stu-id="49224-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="49224-112">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="49224-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="49224-113">См. также</span><span class="sxs-lookup"><span data-stu-id="49224-113">See Also</span></span>
[<span data-ttu-id="49224-114">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="49224-114">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="49224-115">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="49224-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="49224-116">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="49224-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
