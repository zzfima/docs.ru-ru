---
title: "Выражения: выражение try...finally (F#)"
description: "Узнайте, как F # \"try... finally\" выражение дает возможность выполнить код очистки, даже если блок кода выдал исключение."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="37229-104">Выражения: выражение try...finally</span><span class="sxs-lookup"><span data-stu-id="37229-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="37229-105">`try...finally` Выражение дает возможность выполнить код очистки, даже если блок кода выдал исключение.</span><span class="sxs-lookup"><span data-stu-id="37229-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="37229-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37229-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="37229-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="37229-107">Remarks</span></span>
<span data-ttu-id="37229-108">`try...finally` Выражение можно использовать для выполнения кода в *expression2* приведенный выше синтаксис, независимо от того, создается ли исключение во время выполнения *expression1*.</span><span class="sxs-lookup"><span data-stu-id="37229-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="37229-109">Тип *expression2* не влияет на значение всего выражения; Если исключения не возникло, возвращаемым типом является последнее значение в *expression1*.</span><span class="sxs-lookup"><span data-stu-id="37229-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="37229-110">При возникновении исключения, не имеет значения, и поток управления передает Далее соответствующего обработчика исключений в стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="37229-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="37229-111">Если не обнаруживается, выполнение программы прекращается.</span><span class="sxs-lookup"><span data-stu-id="37229-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="37229-112">Перед выполнением кода в соответствующий обработчик или завершении работы программы, код в `finally` выполняет ветвь.</span><span class="sxs-lookup"><span data-stu-id="37229-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="37229-113">В следующем коде показано использование `try...finally` выражение.</span><span class="sxs-lookup"><span data-stu-id="37229-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="37229-114">Ниже приведен вывод на консоль.</span><span class="sxs-lookup"><span data-stu-id="37229-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="37229-115">Как видно из выходных данных, поток был закрыт, прежде чем исключение было обработано и файл `test.txt` с текстом `test1`, указывающая, что буферы были записаны на диск и записываются на диск, несмотря на то, что исключение передаются Управление внешнему обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="37229-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="37229-116">Обратите внимание, что `try...with` конструкция — это отдельные конструкции `try...finally` построения.</span><span class="sxs-lookup"><span data-stu-id="37229-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="37229-117">Таким образом Если код требует выполнения обоих `with` блока и `finally` блока, нужно вложить две конструкции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="37229-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="37229-118">В контексте вычисления выражений, включая выражения последовательностей и асинхронные рабочие потоки **try... finally** выражения могут иметь собственную реализацию.</span><span class="sxs-lookup"><span data-stu-id="37229-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="37229-119">Дополнительные сведения см. в разделе [вычислительных выражениях](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="37229-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="37229-120">См. также</span><span class="sxs-lookup"><span data-stu-id="37229-120">See Also</span></span>
[<span data-ttu-id="37229-121">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="37229-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="37229-122">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="37229-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
