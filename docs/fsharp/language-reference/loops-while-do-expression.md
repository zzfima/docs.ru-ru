---
title: 'Циклы: выражение while...do (F#)'
description: В разделе как while... выполните выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 847f99faab42c8805bd788e42e3f24ad6369ba52
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="f9169-103">Циклы: выражение while...do</span><span class="sxs-lookup"><span data-stu-id="f9169-103">Loops: while...do Expression</span></span>

<span data-ttu-id="f9169-104">`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="f9169-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="f9169-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9169-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="f9169-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9169-106">Remarks</span></span>
<span data-ttu-id="f9169-107">*Тестовое выражение* вычисляется; Если это `true`, *выражение тела* выполняется и снова вычисляется выражение.</span><span class="sxs-lookup"><span data-stu-id="f9169-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="f9169-108">*Выражение тела* должен иметь тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="f9169-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="f9169-109">Если выражение является `false`, окончания итерации.</span><span class="sxs-lookup"><span data-stu-id="f9169-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="f9169-110">Следующий пример иллюстрирует использование `while...do` выражение.</span><span class="sxs-lookup"><span data-stu-id="f9169-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="f9169-111">Результат выполнения предыдущего кода является поток случайных чисел от 1 до 20, последнее из которых — 10.</span><span class="sxs-lookup"><span data-stu-id="f9169-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="f9169-112">Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `while...do` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="f9169-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="f9169-113">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f9169-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f9169-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f9169-114">See Also</span></span>
[<span data-ttu-id="f9169-115">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f9169-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f9169-116">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="f9169-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="f9169-117">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="f9169-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
