---
title: 'Циклы: выражение while...do'
description: См. раздел while... выражение do используется для выполнения итеративного выполнения (циклов), пока заданное условие теста имеет значение true.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216635"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="5235a-103">Циклы: выражение while...do</span><span class="sxs-lookup"><span data-stu-id="5235a-103">Loops: while...do Expression</span></span>

<span data-ttu-id="5235a-104">`while...do` Выражение используется для выполнения итеративного выполнения (цикла), пока заданное условие теста имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="5235a-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="5235a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5235a-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="5235a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5235a-106">Remarks</span></span>

<span data-ttu-id="5235a-107">*Тестовое выражение* вычисляется; Если это так ,товыполняетсявыражениеbody,атестовоевыражениесновавычисляется`true`.</span><span class="sxs-lookup"><span data-stu-id="5235a-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="5235a-108">*Выражение текста* должно иметь тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="5235a-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="5235a-109">Если тестовое выражение имеет `false`значение, итерация завершается.</span><span class="sxs-lookup"><span data-stu-id="5235a-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="5235a-110">В следующем примере показано использование `while...do` выражения.</span><span class="sxs-lookup"><span data-stu-id="5235a-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="5235a-111">Выходные данные предыдущего кода — это поток случайных чисел от 1 до 20, последний из которых равен 10.</span><span class="sxs-lookup"><span data-stu-id="5235a-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="5235a-112">Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях. в этом случае используется настроенная `while...do` версия выражения.</span><span class="sxs-lookup"><span data-stu-id="5235a-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="5235a-113">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие процессы](asynchronous-workflows.md)и [вычислительные выражения](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5235a-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5235a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5235a-114">See also</span></span>

- [<span data-ttu-id="5235a-115">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="5235a-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5235a-116">Бираются `for...in`Выражение</span><span class="sxs-lookup"><span data-stu-id="5235a-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="5235a-117">Бираются `for...to`Выражение</span><span class="sxs-lookup"><span data-stu-id="5235a-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
