---
title: Отложенные вычисления (F#)
description: 'Узнайте, как F # отложенные вычисления могут повысить производительность приложений и библиотек.'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676523"
---
# <a name="lazy-computations"></a><span data-ttu-id="7ae08-103">Отложенные вычисления</span><span class="sxs-lookup"><span data-stu-id="7ae08-103">Lazy Computations</span></span>

<span data-ttu-id="7ae08-104">*Отложенные вычисления* — это вычисления, которые выполняются не сразу, но когда требуется результат.</span><span class="sxs-lookup"><span data-stu-id="7ae08-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="7ae08-105">Это может помочь повысить производительность кода.</span><span class="sxs-lookup"><span data-stu-id="7ae08-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ae08-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ae08-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="7ae08-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ae08-107">Remarks</span></span>

<span data-ttu-id="7ae08-108">В приведенном выше синтаксисе *выражение* приведен код, который вычисляется только в том случае, если результат является обязательным, и *идентификатор* является значение, в котором хранится результат.</span><span class="sxs-lookup"><span data-stu-id="7ae08-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="7ae08-109">Значение имеет тип [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), где фактический тип, используемый для `'T` определяется на основе результата выражения.</span><span class="sxs-lookup"><span data-stu-id="7ae08-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="7ae08-110">Отложенные вычисления позволяют повысить производительность, ограничивая выполнение вычислений только ситуаций, в которых потребуется результат.</span><span class="sxs-lookup"><span data-stu-id="7ae08-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="7ae08-111">Чтобы принудительно выполнить вычисления, вызовите метод `Force`.</span><span class="sxs-lookup"><span data-stu-id="7ae08-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="7ae08-112">`Force` приводит к выполнению должна выполнять только один раз.</span><span class="sxs-lookup"><span data-stu-id="7ae08-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="7ae08-113">Последующие вызовы `Force` возвращают же результат, но не выполняется никакой код.</span><span class="sxs-lookup"><span data-stu-id="7ae08-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="7ae08-114">Следующий код иллюстрирует использование отложенного вычисления и использование `Force`.</span><span class="sxs-lookup"><span data-stu-id="7ae08-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="7ae08-115">В этом коде, тип `result` — `Lazy<int>`и `Force` возвращает метод `int`.</span><span class="sxs-lookup"><span data-stu-id="7ae08-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="7ae08-116">Отложенные вычисления, но не `Lazy` введите, также используется для последовательностей.</span><span class="sxs-lookup"><span data-stu-id="7ae08-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="7ae08-117">Дополнительные сведения см. в разделе [последовательностей](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="7ae08-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ae08-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae08-118">See also</span></span>

- [<span data-ttu-id="7ae08-119">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="7ae08-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7ae08-120">Lazyextensions-модуль</span><span class="sxs-lookup"><span data-stu-id="7ae08-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
