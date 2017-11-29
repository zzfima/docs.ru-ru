---
title: "Исключения: функция raise (F#)"
description: "Узнайте, как используется функция F # «raise» указывает, что произошла ошибка или исключительное состояние."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="919dc-104">Исключения: функция raise</span><span class="sxs-lookup"><span data-stu-id="919dc-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="919dc-105">`raise` Функция используется для указания того, произошла ошибка или исключительное состояние.</span><span class="sxs-lookup"><span data-stu-id="919dc-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="919dc-106">Сведения об ошибке записывается в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="919dc-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="919dc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="919dc-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="919dc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="919dc-108">Remarks</span></span>
<span data-ttu-id="919dc-109">`raise` Функция создает объект исключения и инициирует процесс освобождения стека.</span><span class="sxs-lookup"><span data-stu-id="919dc-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="919dc-110">Процесс освобождения стека управляется общеязыковой среды выполнения (CLR), поэтому этот процесс происходит так же, как в любом другом языке .NET.</span><span class="sxs-lookup"><span data-stu-id="919dc-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="919dc-111">Процесс освобождения стека заключается в поиске обработчика исключений, который соответствует порожденное исключение.</span><span class="sxs-lookup"><span data-stu-id="919dc-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="919dc-112">Поиск начинается в текущем `try...with` выражения, если таковой имеется.</span><span class="sxs-lookup"><span data-stu-id="919dc-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="919dc-113">Каждый шаблон в `with` блок проверяется по порядку.</span><span class="sxs-lookup"><span data-stu-id="919dc-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="919dc-114">Если найден подходящий обработчик исключений, исключение считается как обработанное; в противном случае стек освобождается и `with` блоков в цепочке вызовов проверяются, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="919dc-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="919dc-115">Любой `finally` блоки, которые встречаются в цепочке вызовов, также последовательно выполняются в процессе освобождения стека.</span><span class="sxs-lookup"><span data-stu-id="919dc-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="919dc-116">`raise` Функция эквивалентна `throw` в C# или C++.</span><span class="sxs-lookup"><span data-stu-id="919dc-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="919dc-117">Используйте `reraise` в обработчике catch для распространения этого же исключения в цепочке вызовов.</span><span class="sxs-lookup"><span data-stu-id="919dc-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="919dc-118">В следующих примерах кода показано использование `raise` функция создает исключение.</span><span class="sxs-lookup"><span data-stu-id="919dc-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="919dc-119">`raise` Функция также может использоваться для создания исключений .NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="919dc-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="919dc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="919dc-120">See Also</span></span>
[<span data-ttu-id="919dc-121">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="919dc-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="919dc-122">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="919dc-122">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="919dc-123">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="919dc-123">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="919dc-124">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="919dc-124">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="919dc-125">Исключения: функция `failwith`</span><span class="sxs-lookup"><span data-stu-id="919dc-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="919dc-126">Исключения: функция `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="919dc-126">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
