---
title: "Обработка исключений (F#)"
description: "Основы обработки исключений в языке F # и ссылки на исключение при обработке выражения и функции."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
ms.openlocfilehash: b61af66e0a70fdf9b86df37418c0284957d1f99e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling"></a><span data-ttu-id="349b3-104">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="349b3-104">Exception Handling</span></span>

<span data-ttu-id="349b3-105">Эта статья содержит сведения о поддержке обработки исключений в языке F#.</span><span class="sxs-lookup"><span data-stu-id="349b3-105">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="349b3-106">Основы обработки исключений</span><span class="sxs-lookup"><span data-stu-id="349b3-106">Exception Handling Basics</span></span>
<span data-ttu-id="349b3-107">Обработка исключений является стандартным способом для обработки ошибок в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="349b3-107">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="349b3-108">Поэтому этот механизм должен поддерживаться любым языком .NET, включая F#.</span><span class="sxs-lookup"><span data-stu-id="349b3-108">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="349b3-109">*Исключение* — это объект, инкапсулирующий информацию об ошибке.</span><span class="sxs-lookup"><span data-stu-id="349b3-109">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="349b3-110">При возникновении ошибки возникают исключения и обычное выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="349b3-110">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="349b3-111">Вместо этого среда выполнения ищет подходящий обработчик для исключения.</span><span class="sxs-lookup"><span data-stu-id="349b3-111">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="349b3-112">Поиск начинается в текущей функции и продолжается вверх по стеку через все уровни вызывающих объектов, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="349b3-112">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="349b3-113">Затем этот обработчик запускается.</span><span class="sxs-lookup"><span data-stu-id="349b3-113">Then the handler is executed.</span></span>

<span data-ttu-id="349b3-114">Кроме того, по мере раскрутки стека среда выполнения выполняет весь код в блоках `finally`, обеспечивая правильную очистку объектов во время процесса раскрутки.</span><span class="sxs-lookup"><span data-stu-id="349b3-114">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="349b3-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="349b3-115">Related Topics</span></span>

|<span data-ttu-id="349b3-116">Заголовок</span><span class="sxs-lookup"><span data-stu-id="349b3-116">Title</span></span>|<span data-ttu-id="349b3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="349b3-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="349b3-118">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="349b3-118">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="349b3-119">Описывает объявление типа исключения.</span><span class="sxs-lookup"><span data-stu-id="349b3-119">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="349b3-120">Исключения: выражение `try...with`</span><span class="sxs-lookup"><span data-stu-id="349b3-120">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="349b3-121">Описывает языковую конструкцию, поддерживающую обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="349b3-121">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="349b3-122">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="349b3-122">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="349b3-123">Описывает языковую конструкцию, позволяющую выполнять код очистки по мере раскрутки стека при возникновении исключения.</span><span class="sxs-lookup"><span data-stu-id="349b3-123">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="349b3-124">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="349b3-124">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="349b3-125">Описывает активацию объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="349b3-125">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="349b3-126">Исключения: функция `failwith`</span><span class="sxs-lookup"><span data-stu-id="349b3-126">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="349b3-127">Описывает создание общего исключения F#.</span><span class="sxs-lookup"><span data-stu-id="349b3-127">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="349b3-128">Исключения: функция `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="349b3-128">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="349b3-129">Описывает создание исключения недопустимого аргумента.</span><span class="sxs-lookup"><span data-stu-id="349b3-129">Describes how to generate an invalid argument exception.</span></span>|
