---
title: "Рекурсивные функции. Ключевое слово rec (F#)"
description: "Узнайте, как ключевое слово «rec» F # для определения рекурсивной функции используется с ключевым словом «let»."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="0c956-104">Рекурсивные функции. Ключевое слово rec</span><span class="sxs-lookup"><span data-stu-id="0c956-104">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="0c956-105">`rec` Ключевое слово используется совместно с `let` ключевое слово для определения рекурсивной функции.</span><span class="sxs-lookup"><span data-stu-id="0c956-105">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="0c956-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c956-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="0c956-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c956-107">Remarks</span></span>
<span data-ttu-id="0c956-108">Рекурсивные функции, функции, которые вызывают сами, определяются явно в языке F #.</span><span class="sxs-lookup"><span data-stu-id="0c956-108">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="0c956-109">Это делает доступными идентификаторов, которая определена в области видимости функции.</span><span class="sxs-lookup"><span data-stu-id="0c956-109">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="0c956-110">Следующий код иллюстрирует рекурсивную функцию, которая вычисляет  *n* Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="0c956-110">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="0c956-111">На практике подобное приведенный выше код является лишних затрат времени процессора и памяти, так как подразумевает перерасчет ранее вычисленных значений.</span><span class="sxs-lookup"><span data-stu-id="0c956-111">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="0c956-112">Методы являются неявно рекурсивными в пределах типа; Нет необходимости для добавления `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0c956-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="0c956-113">Привязки let в пределах классов не являются неявно рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="0c956-113">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="0c956-114">Взаимно рекурсивные функции</span><span class="sxs-lookup"><span data-stu-id="0c956-114">Mutually Recursive Functions</span></span>
<span data-ttu-id="0c956-115">Иногда функции являются *взаимно рекурсивные*, это значит, что круг, где одна функция вызывает другую, который в свою очередь вызывает первый, с любого количества вызовов между ними.</span><span class="sxs-lookup"><span data-stu-id="0c956-115">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="0c956-116">Необходимо определить такие функции в один `let` привязки с использованием `and` ключевое слово, чтобы связать их друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0c956-116">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="0c956-117">В следующем примере показаны два взаимно рекурсивные функции.</span><span class="sxs-lookup"><span data-stu-id="0c956-117">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="0c956-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c956-118">See Also</span></span>
[<span data-ttu-id="0c956-119">Функции</span><span class="sxs-lookup"><span data-stu-id="0c956-119">Functions</span></span>](index.md)
