---
title: "Циклы. Выражение for...to (F#)"
description: ". В разделе как F # оператор for... выражение используется для перебора в цикле диапазона значений переменной цикла."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="fa39b-104">Циклы. Выражение for...to</span><span class="sxs-lookup"><span data-stu-id="fa39b-104">Loops: for...to Expression</span></span>

<span data-ttu-id="fa39b-105">`for...to` Выражение используется для перебора в цикле диапазона значений переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="fa39b-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="fa39b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa39b-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="fa39b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa39b-107">Remarks</span></span>
<span data-ttu-id="fa39b-108">Тип идентификатора выводится из типа *запустить* и *Готово* выражения.</span><span class="sxs-lookup"><span data-stu-id="fa39b-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="fa39b-109">Типы для этих выражений должны быть 32-разрядных целых чисел.</span><span class="sxs-lookup"><span data-stu-id="fa39b-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="fa39b-110">Несмотря на то что технически выражения, `for...to` — это больше похоже на традиционный оператор в императивном языке программирования.</span><span class="sxs-lookup"><span data-stu-id="fa39b-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="fa39b-111">Тип возвращаемого значения для *выражение тела* должен быть `unit`.</span><span class="sxs-lookup"><span data-stu-id="fa39b-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="fa39b-112">В следующих примерах показано различные способы использования `for...to` выражение.</span><span class="sxs-lookup"><span data-stu-id="fa39b-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="fa39b-113">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="fa39b-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="fa39b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fa39b-114">See Also</span></span>
[<span data-ttu-id="fa39b-115">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="fa39b-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="fa39b-116">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="fa39b-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="fa39b-117">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="fa39b-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
