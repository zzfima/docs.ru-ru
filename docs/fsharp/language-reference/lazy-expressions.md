---
title: Отложенные выражения
description: Узнайте, F# как отложенные выражения могут повысить производительность приложений и библиотек.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630749"
---
# <a name="lazy-expressions"></a><span data-ttu-id="6b96d-103">Отложенные выражения</span><span class="sxs-lookup"><span data-stu-id="6b96d-103">Lazy Expressions</span></span>

<span data-ttu-id="6b96d-104">*Отложенные выражения* — это выражения, которые не оцениваются немедленно, а оцениваются, когда требуется результат.</span><span class="sxs-lookup"><span data-stu-id="6b96d-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="6b96d-105">Это поможет повысить производительность кода.</span><span class="sxs-lookup"><span data-stu-id="6b96d-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b96d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b96d-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="6b96d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b96d-107">Remarks</span></span>

<span data-ttu-id="6b96d-108">В приведенном выше синтаксисе *выражение* — это код, который вычисляется только тогда, когда требуется результат, а *идентификатор* — это значение, в котором хранится результат.</span><span class="sxs-lookup"><span data-stu-id="6b96d-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="6b96d-109">Значение имеет тип [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), где фактический тип, используемый для `'T` , определяется из результата выражения.</span><span class="sxs-lookup"><span data-stu-id="6b96d-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="6b96d-110">Отложенные выражения позволяют повысить производительность за счет ограниченного выполнения выражений только теми ситуациями, в которых требуется результат.</span><span class="sxs-lookup"><span data-stu-id="6b96d-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="6b96d-111">Чтобы принудительно выполнить выражения, вызовите метод `Force`.</span><span class="sxs-lookup"><span data-stu-id="6b96d-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="6b96d-112">`Force`приводит к выполнению выполнения только один раз.</span><span class="sxs-lookup"><span data-stu-id="6b96d-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="6b96d-113">Последующие вызовы `Force` возвращают тот же результат, но не выполняют никакой код.</span><span class="sxs-lookup"><span data-stu-id="6b96d-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="6b96d-114">В следующем коде показано использование отложенных выражений и использование `Force`.</span><span class="sxs-lookup"><span data-stu-id="6b96d-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="6b96d-115">В `result` этом коде тип имеет значение `Lazy<int>`, `int`а `Force` метод возвращает.</span><span class="sxs-lookup"><span data-stu-id="6b96d-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="6b96d-116">Отложенная оценка, но не `Lazy` тип, также используется для последовательностей.</span><span class="sxs-lookup"><span data-stu-id="6b96d-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="6b96d-117">Дополнительные сведения см. в разделе [последовательности](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="6b96d-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b96d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6b96d-118">See also</span></span>

- [<span data-ttu-id="6b96d-119">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6b96d-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6b96d-120">Модуль Лазекстенсионс</span><span class="sxs-lookup"><span data-stu-id="6b96d-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
