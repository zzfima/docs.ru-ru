---
title: "Циклы: выражение while...do (F#)"
description: "В разделе как while... выполните выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 6a186d75dcda383764949c2cd3b09bc9e3d1080a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="25970-104">Циклы: выражение while...do</span><span class="sxs-lookup"><span data-stu-id="25970-104">Loops: while...do Expression</span></span>

<span data-ttu-id="25970-105">`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="25970-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="25970-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25970-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="25970-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="25970-107">Remarks</span></span>
<span data-ttu-id="25970-108">*Тестовое выражение* вычисляется; Если это `true`, *выражение тела* выполняется и снова вычисляется выражение.</span><span class="sxs-lookup"><span data-stu-id="25970-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="25970-109">*Выражение тела* должен иметь тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="25970-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="25970-110">Если выражение является `false`, окончания итерации.</span><span class="sxs-lookup"><span data-stu-id="25970-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="25970-111">Следующий пример иллюстрирует использование `while...do` выражение.</span><span class="sxs-lookup"><span data-stu-id="25970-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="25970-112">Результат выполнения предыдущего кода является поток случайных чисел от 1 до 20, последнее из которых — 10.</span><span class="sxs-lookup"><span data-stu-id="25970-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="25970-113">Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `while...do` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="25970-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="25970-114">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25970-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="25970-115">См. также</span><span class="sxs-lookup"><span data-stu-id="25970-115">See Also</span></span>
[<span data-ttu-id="25970-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="25970-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="25970-117">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="25970-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="25970-118">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="25970-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
