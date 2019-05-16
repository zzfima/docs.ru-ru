---
title: 'Циклы: выражение while...do'
description: См. в разделе как while... сделать выражение используется для выполнения итерации (в цикле), пока заданное условие теста истинно.
ms.date: 05/16/2016
ms.openlocfilehash: 5823ace27348ff4d4397a726bf2254f8fa0ee09b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641833"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="9f078-103">Циклы: выражение while...do</span><span class="sxs-lookup"><span data-stu-id="9f078-103">Loops: while...do Expression</span></span>

<span data-ttu-id="9f078-104">`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное условие теста истинно.</span><span class="sxs-lookup"><span data-stu-id="9f078-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f078-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f078-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="9f078-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f078-106">Remarks</span></span>

<span data-ttu-id="9f078-107">*Тестовое выражение* вычисляется; Если это `true`, *телом выражения* выполняется и снова вычисляется выражение.</span><span class="sxs-lookup"><span data-stu-id="9f078-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="9f078-108">*Телом выражения* должен иметь тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="9f078-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="9f078-109">Если выражение является `false`, завершения итерации.</span><span class="sxs-lookup"><span data-stu-id="9f078-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="9f078-110">Следующий пример иллюстрирует использование `while...do` выражение.</span><span class="sxs-lookup"><span data-stu-id="9f078-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="9f078-111">Результат выполнения предыдущего кода — это поток случайных чисел от 1 до 20, последнее из которых — 10.</span><span class="sxs-lookup"><span data-stu-id="9f078-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="9f078-112">Можно использовать `while...do` в выражениях последовательности и другие вычисления выражения, в этом случае настроенную версию `while...do` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="9f078-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="9f078-113">Дополнительные сведения см. в разделе [последовательностей](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения вычисления](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9f078-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f078-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9f078-114">See also</span></span>

- [<span data-ttu-id="9f078-115">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="9f078-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9f078-116">Циклы. `for...in` Выражение</span><span class="sxs-lookup"><span data-stu-id="9f078-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="9f078-117">Циклы. `for...to` Выражение</span><span class="sxs-lookup"><span data-stu-id="9f078-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
