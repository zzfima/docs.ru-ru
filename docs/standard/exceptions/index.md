---
title: "Обработка и создание исключений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d44996042d167c029291f2b454dc1a22cfbcfb4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="ea2de-102">Обработка и создание исключений в .NET</span><span class="sxs-lookup"><span data-stu-id="ea2de-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="ea2de-103">Необходимо реализовать возможность единообразной обработки приложениями ошибок, происходящих во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea2de-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="ea2de-104">Среда .NET предоставляет модель для единообразного уведомления приложений об ошибках: операции .NET информируют о сбое посредством выдачи исключений.</span><span class="sxs-lookup"><span data-stu-id="ea2de-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="ea2de-105">Исключения</span><span class="sxs-lookup"><span data-stu-id="ea2de-105">Exceptions</span></span>

<span data-ttu-id="ea2de-106">Исключение — это любое состояние ошибки или непредвиденное поведение, возникающее при выполнении программы.</span><span class="sxs-lookup"><span data-stu-id="ea2de-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="ea2de-107">Исключения могут возникать из-за сбоя в вашем или вызываемом коде (например, в общей библиотеке), недоступности ресурсов ОС, неожиданных состояний, возникающих в среде выполнения (например, код, который невозможно проверить), и так далее.</span><span class="sxs-lookup"><span data-stu-id="ea2de-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="ea2de-108">После некоторых из этих состояний приложение может восстановиться, после других — нет.</span><span class="sxs-lookup"><span data-stu-id="ea2de-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="ea2de-109">Несмотря на то что можно выполнить восстановление после большинства исключений приложения, выполнить восстановление после большинства исключений среды выполнения невозможно.</span><span class="sxs-lookup"><span data-stu-id="ea2de-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="ea2de-110">В .NET исключение — это объект, наследуемый от класса [System.Exception](xref:System.Exception).</span><span class="sxs-lookup"><span data-stu-id="ea2de-110">In .NET, an exception is an object that inherits from the [System.Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="ea2de-111">Исключение создается из области кода, где произошла проблема.</span><span class="sxs-lookup"><span data-stu-id="ea2de-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="ea2de-112">Исключение передается вверх по стеку до тех пор, пока его не обработает приложение либо программа не завершится.</span><span class="sxs-lookup"><span data-stu-id="ea2de-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="ea2de-113">Исключения и традиционные методы обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="ea2de-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="ea2de-114">Традиционно модели обработки ошибок разных языков программирования основываются либо на уникальном для языка способе обнаружения ошибок и отыскании для них обработчиков, либо на механизме обработки ошибок, предоставляемом операционной системой.</span><span class="sxs-lookup"><span data-stu-id="ea2de-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="ea2de-115">Способ обработки исключений, реализуемый в .NET, обладает следующими преимуществами:</span><span class="sxs-lookup"><span data-stu-id="ea2de-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="ea2de-116">Создание и обработка исключений работают одинаково для языков программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="ea2de-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="ea2de-117">Не требует определенного синтаксиса языка для обработки исключений, а позволяет каждому языку определить свой собственный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="ea2de-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="ea2de-118">Исключения можно создавать между разными процессами и даже компьютерами.</span><span class="sxs-lookup"><span data-stu-id="ea2de-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="ea2de-119">В приложение можно добавить код обработки исключений для повышения надежности программы.</span><span class="sxs-lookup"><span data-stu-id="ea2de-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="ea2de-120">Исключения обеспечивают ряд преимуществ по сравнению с другими методами уведомления об ошибках, например кодами возврата.</span><span class="sxs-lookup"><span data-stu-id="ea2de-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="ea2de-121">Сбои не остаются незамеченными, так как при наличии необработанного исключения среда выполнения завершает работу приложения.</span><span class="sxs-lookup"><span data-stu-id="ea2de-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="ea2de-122">Недопустимые значения не распространяются по системе из-за того, что код не способен выполнить проверку кода возврата ошибки.</span><span class="sxs-lookup"><span data-stu-id="ea2de-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="ea2de-123">Общие исключения</span><span class="sxs-lookup"><span data-stu-id="ea2de-123">Common Exceptions</span></span>

<span data-ttu-id="ea2de-124">В следующей таблице перечислены некоторые общие исключения с примерами возможных причин.</span><span class="sxs-lookup"><span data-stu-id="ea2de-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="ea2de-125">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="ea2de-125">Exception type</span></span> | <span data-ttu-id="ea2de-126">Базовый тип</span><span class="sxs-lookup"><span data-stu-id="ea2de-126">Base type</span></span> | <span data-ttu-id="ea2de-127">Описание</span><span class="sxs-lookup"><span data-stu-id="ea2de-127">Description</span></span> | <span data-ttu-id="ea2de-128">Пример</span><span class="sxs-lookup"><span data-stu-id="ea2de-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | <span data-ttu-id="ea2de-129">Базовый класс для всех исключений.</span><span class="sxs-lookup"><span data-stu-id="ea2de-129">Base class for all exceptions.</span></span> | <span data-ttu-id="ea2de-130">Отсутствует (используйте производный класс этого исключения).</span><span class="sxs-lookup"><span data-stu-id="ea2de-130">None (use a derived class of this exception).</span></span> |
| @System.IndexOutOfRangeException | @System.Exception | <span data-ttu-id="ea2de-131">Вызывается средой выполнения только при неправильной индексации массива.</span><span class="sxs-lookup"><span data-stu-id="ea2de-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="ea2de-132">Индексирование массива вне допустимого диапазона: `arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="ea2de-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| @System.NullReferenceException | @System.Exception | <span data-ttu-id="ea2de-133">Вызывается средой выполнения только в том случае, если имеется ссылка на пустой объект.</span><span class="sxs-lookup"><span data-stu-id="ea2de-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | <span data-ttu-id="ea2de-134">Вызывается методами в недопустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="ea2de-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="ea2de-135">Вызов `Enumerator.GetNext()` после удаления элемента из базовой коллекции.</span><span class="sxs-lookup"><span data-stu-id="ea2de-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| @System.ArgumentException | @System.Exception | <span data-ttu-id="ea2de-136">Базовый класс для всех исключений аргументов.</span><span class="sxs-lookup"><span data-stu-id="ea2de-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="ea2de-137">Отсутствует (используйте производный класс этого исключения).</span><span class="sxs-lookup"><span data-stu-id="ea2de-137">None (use a derived class of this exception).</span></span> |
| @System.ArgumentNullException | @System.Exception | <span data-ttu-id="ea2de-138">Вызывается методами, которые не допускают пустой аргумент.</span><span class="sxs-lookup"><span data-stu-id="ea2de-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | <span data-ttu-id="ea2de-139">Вызывается методами, проверяющими попадание аргументов в заданный диапазон.</span><span class="sxs-lookup"><span data-stu-id="ea2de-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="ea2de-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ea2de-140">See Also</span></span>

* [<span data-ttu-id="ea2de-141">Класс Exception и его свойства</span><span class="sxs-lookup"><span data-stu-id="ea2de-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="ea2de-142">Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений</span><span class="sxs-lookup"><span data-stu-id="ea2de-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="ea2de-143">Практическое руководство. Использование определенных исключений в блоке catch</span><span class="sxs-lookup"><span data-stu-id="ea2de-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="ea2de-144">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="ea2de-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="ea2de-145">Практическое руководство. Создание пользовательских исключений</span><span class="sxs-lookup"><span data-stu-id="ea2de-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="ea2de-146">Использование обработчиков исключений с пользовательской фильтрацией</span><span class="sxs-lookup"><span data-stu-id="ea2de-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="ea2de-147">Практическое руководство. Использование блоков Finally</span><span class="sxs-lookup"><span data-stu-id="ea2de-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="ea2de-148">Обработка исключений COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ea2de-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="ea2de-149">Рекомендации по обработке исключений</span><span class="sxs-lookup"><span data-stu-id="ea2de-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="ea2de-150">Дополнительные сведения о работе исключений в .NET см. в разделе [Что должен знать любой разработчик об исключениях в среде выполнения](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="ea2de-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>

