---
title: 'Рекурсивные функции: Ключевое слово REC'
description: Узнайте, как F# ключевое слово "REC" используется с ключевым словом let для определения рекурсивной функции.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630649"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="6c801-103">Рекурсивные функции: Ключевое слово REC</span><span class="sxs-lookup"><span data-stu-id="6c801-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="6c801-104">Ключевое слово используется вместе `let` с ключевым словом для определения рекурсивной функции. `rec`</span><span class="sxs-lookup"><span data-stu-id="6c801-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c801-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c801-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="6c801-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c801-106">Remarks</span></span>

<span data-ttu-id="6c801-107">Рекурсивные функции, которые вызывают сами себя, определяются явным образом на F# языке.</span><span class="sxs-lookup"><span data-stu-id="6c801-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="6c801-108">Это делает определяемый идентификатор доступным в области действия функции.</span><span class="sxs-lookup"><span data-stu-id="6c801-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="6c801-109">В следующем коде показана рекурсивная функция, которая выполняет вычисление *n*-<sup>го</sup> числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="6c801-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="6c801-110">На практике код, подобный приведенному выше, — непроизводительна памяти и процессорного времени, так как он включает перерасчет ранее вычисленных значений.</span><span class="sxs-lookup"><span data-stu-id="6c801-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="6c801-111">Методы неявно являются рекурсивными в пределах типа; нет необходимости добавлять `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6c801-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="6c801-112">Привязки let в классах не являются неявно рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="6c801-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="6c801-113">Взаимные рекурсивные функции</span><span class="sxs-lookup"><span data-stu-id="6c801-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="6c801-114">Иногда функции являются *взаимно рекурсивными*, то есть вызывают форму круга, где одна функция вызывает другую, которая, в свою очередь, вызывает первую, с любым числом вызовов между.</span><span class="sxs-lookup"><span data-stu-id="6c801-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="6c801-115">Необходимо определить такие функции вместе в одной `let` привязке, `and` используя ключевое слово, чтобы связать их вместе.</span><span class="sxs-lookup"><span data-stu-id="6c801-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="6c801-116">В следующем примере показаны две взаимно рекурсивные функции.</span><span class="sxs-lookup"><span data-stu-id="6c801-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="6c801-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6c801-117">See also</span></span>

- [<span data-ttu-id="6c801-118">Функции</span><span class="sxs-lookup"><span data-stu-id="6c801-118">Functions</span></span>](index.md)
