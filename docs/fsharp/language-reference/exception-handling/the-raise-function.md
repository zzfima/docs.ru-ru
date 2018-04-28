---
title: 'Исключения: функция raise (F#)'
description: 'Узнайте, как используется функция F # «raise» указывает, что произошла ошибка или исключительное состояние.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: 6bc62b13467b8cf4cfcb22f7d4a5f3464236f6d1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="130bc-103">Исключения: функция raise</span><span class="sxs-lookup"><span data-stu-id="130bc-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="130bc-104">`raise` Функция используется для указания того, произошла ошибка или исключительное состояние.</span><span class="sxs-lookup"><span data-stu-id="130bc-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="130bc-105">Сведения об ошибке записывается в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="130bc-105">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="130bc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="130bc-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="130bc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="130bc-107">Remarks</span></span>
<span data-ttu-id="130bc-108">`raise` Функция создает объект исключения и инициирует процесс освобождения стека.</span><span class="sxs-lookup"><span data-stu-id="130bc-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="130bc-109">Процесс освобождения стека управляется общеязыковой среды выполнения (CLR), поэтому этот процесс происходит так же, как в любом другом языке .NET.</span><span class="sxs-lookup"><span data-stu-id="130bc-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="130bc-110">Процесс освобождения стека заключается в поиске обработчика исключений, который соответствует порожденное исключение.</span><span class="sxs-lookup"><span data-stu-id="130bc-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="130bc-111">Поиск начинается в текущем `try...with` выражения, если таковой имеется.</span><span class="sxs-lookup"><span data-stu-id="130bc-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="130bc-112">Каждый шаблон в `with` блок проверяется по порядку.</span><span class="sxs-lookup"><span data-stu-id="130bc-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="130bc-113">Если найден подходящий обработчик исключений, исключение считается как обработанное; в противном случае стек освобождается и `with` блоков в цепочке вызовов проверяются, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="130bc-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="130bc-114">Любой `finally` блоки, которые встречаются в цепочке вызовов, также последовательно выполняются в процессе освобождения стека.</span><span class="sxs-lookup"><span data-stu-id="130bc-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="130bc-115">`raise` Функция эквивалентна `throw` в C# или C++.</span><span class="sxs-lookup"><span data-stu-id="130bc-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="130bc-116">Используйте `reraise` в обработчике catch для распространения этого же исключения в цепочке вызовов.</span><span class="sxs-lookup"><span data-stu-id="130bc-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="130bc-117">В следующих примерах кода показано использование `raise` функция создает исключение.</span><span class="sxs-lookup"><span data-stu-id="130bc-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="130bc-118">`raise` Функция также может использоваться для создания исключений .NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="130bc-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="130bc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="130bc-119">See Also</span></span>
[<span data-ttu-id="130bc-120">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="130bc-120">Exception Handling</span></span>](index.md)

[<span data-ttu-id="130bc-121">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="130bc-121">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="130bc-122">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="130bc-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="130bc-123">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="130bc-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="130bc-124">Исключения: функция `failwith`</span><span class="sxs-lookup"><span data-stu-id="130bc-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="130bc-125">Исключения: функция `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="130bc-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
