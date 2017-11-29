---
title: "Отложенные вычисления (F#)"
description: "Узнайте, как F # отложенные вычисления могут повысить производительность приложений и библиотек."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="0b4b4-104">Отложенные вычисления</span><span class="sxs-lookup"><span data-stu-id="0b4b4-104">Lazy Computations</span></span>

<span data-ttu-id="0b4b4-105">*Отложенные вычисления* — это вычисления, которые выполняются немедленно, а когда требуется результат.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="0b4b4-106">Это может помочь повысить производительность кода.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b4b4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b4b4-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="0b4b4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b4b4-108">Remarks</span></span>

<span data-ttu-id="0b4b4-109">В предыдущем синтаксисе *выражение* — код, который вычисляется только в том случае, когда требуется результат и *идентификатор* представляет собой значение, результат сохраняется.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="0b4b4-110">Значение имеет тип [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), где фактический тип, используемый для `'T` определяется на основе значения выражения.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="0b4b4-111">Отложенные вычисления позволяют повысить производительность, ограничивая выполнение вычислений только ситуаций, в которых потребуется результат.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="0b4b4-112">Чтобы принудительно выполнить вычисления, вызовите метод `Force`.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="0b4b4-113">`Force`вызывает выполнение вычисления только один раз.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="0b4b4-114">Последующие вызовы `Force` возвращают же результат, но не выполняется никакой код.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="0b4b4-115">Следующий код иллюстрирует использование отложенного вычисления и использования `Force`.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="0b4b4-116">В этом коде тип `result` — `Lazy<int>`и `Force` возвращает `int`.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="0b4b4-117">Отложенные вычисления, но не `Lazy` введите, используется также для последовательностей.</span><span class="sxs-lookup"><span data-stu-id="0b4b4-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="0b4b4-118">Дополнительные сведения см. в разделе [последовательности](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="0b4b4-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b4b4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0b4b4-119">See Also</span></span>

[<span data-ttu-id="0b4b4-120">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="0b4b4-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="0b4b4-121">Lazyextensions-модуль</span><span class="sxs-lookup"><span data-stu-id="0b4b4-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
