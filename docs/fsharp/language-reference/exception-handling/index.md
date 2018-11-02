---
title: Обработка исключений (F#)
description: Основы обработки исключений в F# и ссылки на исключение, обработка выражения и функции.
ms.date: 05/16/2016
ms.openlocfilehash: fc89feb0d21bc823cb105e435413f8309cd6174c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "33564330"
---
# <a name="exception-handling"></a><span data-ttu-id="dd3c5-103">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="dd3c5-103">Exception Handling</span></span>

<span data-ttu-id="dd3c5-104">Эта статья содержит сведения о поддержке обработки исключений в языке F#.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-104">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="dd3c5-105">Основы обработки исключений</span><span class="sxs-lookup"><span data-stu-id="dd3c5-105">Exception Handling Basics</span></span>
<span data-ttu-id="dd3c5-106">Обработка исключений является стандартным способом для обработки ошибок в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="dd3c5-107">Поэтому этот механизм должен поддерживаться любым языком .NET, включая F#.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="dd3c5-108">*Исключение* — это объект, инкапсулирующий информацию об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="dd3c5-109">При возникновении ошибки возникают исключения и обычное выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="dd3c5-110">Вместо этого среда выполнения ищет подходящий обработчик для исключения.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="dd3c5-111">Поиск начинается в текущей функции и продолжается вверх по стеку через все уровни вызывающих объектов, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="dd3c5-112">Затем этот обработчик запускается.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-112">Then the handler is executed.</span></span>

<span data-ttu-id="dd3c5-113">Кроме того, по мере раскрутки стека среда выполнения выполняет весь код в блоках `finally`, обеспечивая правильную очистку объектов во время процесса раскрутки.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="dd3c5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dd3c5-114">Related Topics</span></span>

|<span data-ttu-id="dd3c5-115">Заголовок</span><span class="sxs-lookup"><span data-stu-id="dd3c5-115">Title</span></span>|<span data-ttu-id="dd3c5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dd3c5-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="dd3c5-117">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="dd3c5-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="dd3c5-118">Описывает объявление типа исключения.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-118">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="dd3c5-119">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="dd3c5-119">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="dd3c5-120">Описывает языковую конструкцию, поддерживающую обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-120">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="dd3c5-121">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="dd3c5-121">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="dd3c5-122">Описывает языковую конструкцию, позволяющую выполнять код очистки по мере раскрутки стека при возникновении исключения.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="dd3c5-123">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="dd3c5-123">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="dd3c5-124">Описывает активацию объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-124">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="dd3c5-125">Исключения: функция `failwith`</span><span class="sxs-lookup"><span data-stu-id="dd3c5-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="dd3c5-126">Описывает создание общего исключения F#.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-126">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="dd3c5-127">Исключения: функция `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="dd3c5-127">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="dd3c5-128">Описывает создание исключения недопустимого аргумента.</span><span class="sxs-lookup"><span data-stu-id="dd3c5-128">Describes how to generate an invalid argument exception.</span></span>|
