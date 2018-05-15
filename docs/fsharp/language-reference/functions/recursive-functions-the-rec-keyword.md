---
title: Рекурсивные функции. Ключевое слово rec (F#)
description: 'Узнайте, как ключевое слово «rec» F # для определения рекурсивной функции используется с ключевым словом «let».'
ms.date: 05/16/2016
ms.openlocfilehash: 6039a48eae2b16aa1d82617176460d727a878d87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="b8d77-103">Рекурсивные функции. Ключевое слово rec</span><span class="sxs-lookup"><span data-stu-id="b8d77-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="b8d77-104">`rec` Ключевое слово используется совместно с `let` ключевое слово для определения рекурсивной функции.</span><span class="sxs-lookup"><span data-stu-id="b8d77-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="b8d77-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8d77-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b8d77-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8d77-106">Remarks</span></span>
<span data-ttu-id="b8d77-107">Рекурсивные функции, функции, которые вызывают сами, определяются явно в языке F #.</span><span class="sxs-lookup"><span data-stu-id="b8d77-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="b8d77-108">Это делает доступными идентификаторов, которая определена в области видимости функции.</span><span class="sxs-lookup"><span data-stu-id="b8d77-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="b8d77-109">Следующий код иллюстрирует рекурсивную функцию, которая вычисляет *n*Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="b8d77-109">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="b8d77-110">На практике подобное приведенный выше код является лишних затрат времени процессора и памяти, так как подразумевает перерасчет ранее вычисленных значений.</span><span class="sxs-lookup"><span data-stu-id="b8d77-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="b8d77-111">Методы являются неявно рекурсивными в пределах типа; Нет необходимости для добавления `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b8d77-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="b8d77-112">Привязки let в пределах классов не являются неявно рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="b8d77-112">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="b8d77-113">Взаимно рекурсивные функции</span><span class="sxs-lookup"><span data-stu-id="b8d77-113">Mutually Recursive Functions</span></span>
<span data-ttu-id="b8d77-114">Иногда функции являются *взаимно рекурсивные*, это значит, что круг, где одна функция вызывает другую, который в свою очередь вызывает первый, с любого количества вызовов между ними.</span><span class="sxs-lookup"><span data-stu-id="b8d77-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="b8d77-115">Необходимо определить такие функции в один `let` привязки с использованием `and` ключевое слово, чтобы связать их друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b8d77-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="b8d77-116">В следующем примере показаны два взаимно рекурсивные функции.</span><span class="sxs-lookup"><span data-stu-id="b8d77-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="b8d77-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d77-117">See Also</span></span>
[<span data-ttu-id="b8d77-118">Функции</span><span class="sxs-lookup"><span data-stu-id="b8d77-118">Functions</span></span>](index.md)
