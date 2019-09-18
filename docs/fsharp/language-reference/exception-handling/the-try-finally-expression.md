---
title: Исключения. Выражение try...finally
description: Узнайте, F# как "try... Наконец "выражение позволяет выполнять код очистки, даже если блок кода создает исключение.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddb64ac13b307404864ec5b54f26fd8a7a3d7d8
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082998"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="32b38-103">Исключения. Выражение try...finally</span><span class="sxs-lookup"><span data-stu-id="32b38-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="32b38-104">`try...finally` Выражение позволяет выполнять код очистки, даже если блок кода создает исключение.</span><span class="sxs-lookup"><span data-stu-id="32b38-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="32b38-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32b38-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="32b38-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="32b38-106">Remarks</span></span>

<span data-ttu-id="32b38-107">Выражение можно использовать для выполнения кода в *Expression2* в предыдущем синтаксисе независимо от того, создано ли исключение во время выполнения *expression1.* `try...finally`</span><span class="sxs-lookup"><span data-stu-id="32b38-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="32b38-108">Тип *Expression2* не влияет на значение всего выражения; тип, возвращаемый, если исключение не возникает, является последним значением в *expression1*.</span><span class="sxs-lookup"><span data-stu-id="32b38-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="32b38-109">При возникновении исключения значение не возвращается, а поток управления передается в следующий обработчик исключений, находящийся выше по стеку вызовов.</span><span class="sxs-lookup"><span data-stu-id="32b38-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="32b38-110">Если обработчик исключений не найден, программа завершает работу.</span><span class="sxs-lookup"><span data-stu-id="32b38-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="32b38-111">Перед выполнением кода в обработчике сопоставления или завершения программы выполняется код в `finally` ветви.</span><span class="sxs-lookup"><span data-stu-id="32b38-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="32b38-112">В следующем коде показано использование `try...finally` выражения.</span><span class="sxs-lookup"><span data-stu-id="32b38-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="32b38-113">На консоль выводятся следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="32b38-113">The output to the console is as follows.</span></span>

```console
Closing stream
Exception handled.
```

<span data-ttu-id="32b38-114">Как видно из выходных данных, поток был закрыт до обработки внешнего исключения, а файл `test.txt` содержит текст `test1`, указывающий на то, что буферы были сброшены и записаны на диск, даже если исключение передано. Управление внешним обработчиком исключений.</span><span class="sxs-lookup"><span data-stu-id="32b38-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="32b38-115">Обратите внимание `try...with` , что конструкция является отдельной конструкцией `try...finally` из конструкции.</span><span class="sxs-lookup"><span data-stu-id="32b38-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="32b38-116">Поэтому, если в коде требуется `with` блок `finally` и блок, необходимо вложить две конструкции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="32b38-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="32b38-117">В контексте вычислительных выражений, включая выражения последовательности и асинхронные рабочие процессы, **попробуйте... выражения finally** могут иметь пользовательскую реализацию.</span><span class="sxs-lookup"><span data-stu-id="32b38-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="32b38-118">Дополнительные сведения см. в разделе [выражения вычислений](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="32b38-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32b38-119">См. также</span><span class="sxs-lookup"><span data-stu-id="32b38-119">See also</span></span>

- [<span data-ttu-id="32b38-120">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="32b38-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="32b38-121">Исключения. `try...with` Выражение</span><span class="sxs-lookup"><span data-stu-id="32b38-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
