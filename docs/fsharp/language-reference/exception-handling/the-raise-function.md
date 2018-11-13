---
title: 'Исключения: функция raise (F#)'
description: Узнайте, как используется функция F# «raise» указывает, что ошибку или исключительную ситуацию.
ms.date: 05/16/2016
ms.openlocfilehash: 537d274659d29404380bfdd56310ac267372bb98
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43778263"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="a5807-103">Исключения: функция raise</span><span class="sxs-lookup"><span data-stu-id="a5807-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="a5807-104">`raise` Функция используется для указания, что произошло ошибку или исключительную ситуацию.</span><span class="sxs-lookup"><span data-stu-id="a5807-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="a5807-105">Сведения об ошибке записывается в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="a5807-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5807-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5807-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="a5807-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5807-107">Remarks</span></span>

<span data-ttu-id="a5807-108">`raise` Функция создает объект исключения и инициирует процесс освобождения стека.</span><span class="sxs-lookup"><span data-stu-id="a5807-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="a5807-109">Процесс освобождения стека управляет среда CLR (CLR), поэтому этот процесс происходит так же, как в любом другом языке .NET.</span><span class="sxs-lookup"><span data-stu-id="a5807-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="a5807-110">Процесс освобождения стека заключается в поиске обработчик исключений, который соответствует порожденное исключение.</span><span class="sxs-lookup"><span data-stu-id="a5807-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="a5807-111">Поиск начинается в текущем `try...with` выражения, если таковой имеется.</span><span class="sxs-lookup"><span data-stu-id="a5807-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="a5807-112">Каждый шаблон `with` блока установлен, в порядке.</span><span class="sxs-lookup"><span data-stu-id="a5807-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="a5807-113">При обнаружении соответствующего обработчика исключений, исключение считается обработанным; в противном случае стек освобождается и `with` блоков в цепочке вызовов проверяются, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="a5807-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="a5807-114">Любой `finally` блоки, которые встречаются в цепочке вызовов, также выполняются в последовательности раскрутки стека.</span><span class="sxs-lookup"><span data-stu-id="a5807-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="a5807-115">`raise` Функция является эквивалентом `throw` в C# или C++.</span><span class="sxs-lookup"><span data-stu-id="a5807-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="a5807-116">Используйте `reraise` в обработчике catch для распространения вверх по цепи вызова одно и то же исключение.</span><span class="sxs-lookup"><span data-stu-id="a5807-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="a5807-117">В следующих примерах кода показано использование `raise` функция создает исключение.</span><span class="sxs-lookup"><span data-stu-id="a5807-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="a5807-118">`raise` Функция также может использоваться для создания исключений .NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5807-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="a5807-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a5807-119">See also</span></span>

- [<span data-ttu-id="a5807-120">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="a5807-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="a5807-121">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="a5807-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="a5807-122">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="a5807-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="a5807-123">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="a5807-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="a5807-124">Исключения: функция `failwith`</span><span class="sxs-lookup"><span data-stu-id="a5807-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="a5807-125">Исключения: функция `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="a5807-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
