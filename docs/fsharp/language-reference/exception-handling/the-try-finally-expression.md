---
title: 'Выражения: выражение try...finally (F#)'
description: 'Узнайте, как F # "try... finally" выражение дает возможность выполнить код очистки, даже если блок кода выдал исключение.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 588e4edb4d25c6d25ef103ba724613db997f68d7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="3920e-103">Выражения: выражение try...finally</span><span class="sxs-lookup"><span data-stu-id="3920e-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="3920e-104">`try...finally` Выражение дает возможность выполнить код очистки, даже если блок кода выдал исключение.</span><span class="sxs-lookup"><span data-stu-id="3920e-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="3920e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3920e-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="3920e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3920e-106">Remarks</span></span>
<span data-ttu-id="3920e-107">`try...finally` Выражение можно использовать для выполнения кода в *expression2* приведенный выше синтаксис, независимо от того, создается ли исключение во время выполнения *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3920e-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="3920e-108">Тип *expression2* не влияет на значение всего выражения; Если исключения не возникло, возвращаемым типом является последнее значение в *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3920e-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="3920e-109">При возникновении исключения, не имеет значения, и поток управления передает Далее соответствующего обработчика исключений в стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="3920e-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="3920e-110">Если не обнаруживается, выполнение программы прекращается.</span><span class="sxs-lookup"><span data-stu-id="3920e-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="3920e-111">Перед выполнением кода в соответствующий обработчик или завершении работы программы, код в `finally` выполняет ветвь.</span><span class="sxs-lookup"><span data-stu-id="3920e-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="3920e-112">В следующем коде показано использование `try...finally` выражение.</span><span class="sxs-lookup"><span data-stu-id="3920e-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="3920e-113">Ниже приведен вывод на консоль.</span><span class="sxs-lookup"><span data-stu-id="3920e-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="3920e-114">Как видно из выходных данных, поток был закрыт, прежде чем исключение было обработано и файл `test.txt` с текстом `test1`, указывающая, что буферы были записаны на диск и записываются на диск, несмотря на то, что исключение передаются Управление внешнему обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="3920e-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="3920e-115">Обратите внимание, что `try...with` конструкция — это отдельные конструкции `try...finally` построения.</span><span class="sxs-lookup"><span data-stu-id="3920e-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="3920e-116">Таким образом Если код требует выполнения обоих `with` блока и `finally` блока, нужно вложить две конструкции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="3920e-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="3920e-117">В контексте вычисления выражений, включая выражения последовательностей и асинхронные рабочие потоки **try... finally** выражения могут иметь собственную реализацию.</span><span class="sxs-lookup"><span data-stu-id="3920e-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="3920e-118">Дополнительные сведения см. в разделе [вычислительных выражениях](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3920e-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="3920e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3920e-119">See Also</span></span>
[<span data-ttu-id="3920e-120">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="3920e-120">Exception Handling</span></span>](index.md)

[<span data-ttu-id="3920e-121">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="3920e-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
