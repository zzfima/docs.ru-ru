---
title: Рекурсивные функции. Ключевое слово rec (F#)
description: Узнайте, как F# слово «rec» используется с ключевым словом «let» для определения рекурсивной функции.
ms.date: 05/16/2016
ms.openlocfilehash: 0db3ed7f85a1380654f2827b4773985b661589c7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127736"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="2f46b-103">Рекурсивные функции. Ключевое слово rec</span><span class="sxs-lookup"><span data-stu-id="2f46b-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="2f46b-104">`rec` Ключевое слово используется вместе с `let` ключевое слово для определения рекурсивной функции.</span><span class="sxs-lookup"><span data-stu-id="2f46b-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f46b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f46b-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="2f46b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f46b-106">Remarks</span></span>

<span data-ttu-id="2f46b-107">Рекурсивные функции, функции, которые вызывают сами себя, определяются явно при F# языка.</span><span class="sxs-lookup"><span data-stu-id="2f46b-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="2f46b-108">Это делает доступным идентификатор, который определяется в области видимости функции.</span><span class="sxs-lookup"><span data-stu-id="2f46b-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="2f46b-109">Следующий код иллюстрирует рекурсивную функцию, которая вычисляет *n*<sup>th</sup> число Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="2f46b-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="2f46b-110">На практике, приведенный выше код неэффективен времени процессора и памяти, так как подразумевает перерасчет ранее вычисленных значений.</span><span class="sxs-lookup"><span data-stu-id="2f46b-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="2f46b-111">Методы являются неявно рекурсивными в пределах типа; Нет необходимости, чтобы добавить `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2f46b-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="2f46b-112">Привязки let в классах не являются неявно рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="2f46b-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="2f46b-113">Взаимно рекурсивные функции</span><span class="sxs-lookup"><span data-stu-id="2f46b-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="2f46b-114">Иногда функции являются *взаимно рекурсивные*, это значит, что круг, где одна функция вызывает другую, которая в свою очередь вызывает первый, с любым количеством вызовов между ними.</span><span class="sxs-lookup"><span data-stu-id="2f46b-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="2f46b-115">Такие функции должны определять вместе в одном `let` привязка, с помощью `and` ключевое слово, чтобы связать их друг с другом.</span><span class="sxs-lookup"><span data-stu-id="2f46b-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="2f46b-116">В следующем примере показано два взаимно рекурсивные функции.</span><span class="sxs-lookup"><span data-stu-id="2f46b-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="2f46b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2f46b-117">See also</span></span>

- [<span data-ttu-id="2f46b-118">Функции</span><span class="sxs-lookup"><span data-stu-id="2f46b-118">Functions</span></span>](index.md)
