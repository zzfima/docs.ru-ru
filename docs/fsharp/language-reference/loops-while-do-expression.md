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
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="56211-104">Циклы: выражение while...do</span><span class="sxs-lookup"><span data-stu-id="56211-104">Loops: while...do Expression</span></span>

<span data-ttu-id="56211-105">`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="56211-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="56211-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56211-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="56211-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="56211-107">Remarks</span></span>
<span data-ttu-id="56211-108">*Тестовое выражение* вычисляется; Если это `true`, *выражение тела* выполняется и снова вычисляется выражение.</span><span class="sxs-lookup"><span data-stu-id="56211-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="56211-109">*Выражение тела* должен иметь тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="56211-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="56211-110">Если выражение является `false`, окончания итерации.</span><span class="sxs-lookup"><span data-stu-id="56211-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="56211-111">Следующий пример иллюстрирует использование `while...do` выражение.</span><span class="sxs-lookup"><span data-stu-id="56211-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="56211-112">Результат выполнения предыдущего кода является поток случайных чисел от 1 до 20, последнее из которых — 10.</span><span class="sxs-lookup"><span data-stu-id="56211-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="56211-113">Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `while...do` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="56211-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="56211-114">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="56211-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="56211-115">См. также</span><span class="sxs-lookup"><span data-stu-id="56211-115">See Also</span></span>
[<span data-ttu-id="56211-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="56211-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="56211-117">Циклы: выражение `for...in`</span><span class="sxs-lookup"><span data-stu-id="56211-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="56211-118">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="56211-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
