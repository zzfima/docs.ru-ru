---
title: Обработка и создание исключений в .NET
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263e6394a57ec3e7ef00eb79671d9b8ac47e724f
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862832"
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="0e926-102">Обработка и создание исключений в .NET</span><span class="sxs-lookup"><span data-stu-id="0e926-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="0e926-103">Необходимо реализовать возможность единообразной обработки приложениями ошибок, происходящих во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0e926-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="0e926-104">Среда .NET предоставляет модель для единообразного уведомления приложений об ошибках: операции .NET информируют о сбое посредством выдачи исключений.</span><span class="sxs-lookup"><span data-stu-id="0e926-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="0e926-105">Исключения</span><span class="sxs-lookup"><span data-stu-id="0e926-105">Exceptions</span></span>

<span data-ttu-id="0e926-106">Исключение — это любое состояние ошибки или непредвиденное поведение, возникающее при выполнении программы.</span><span class="sxs-lookup"><span data-stu-id="0e926-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="0e926-107">Исключения могут возникать из-за сбоя в вашем или вызываемом коде (например, в общей библиотеке), недоступности ресурсов ОС, неожиданных состояний, возникающих в среде выполнения (например, код, который невозможно проверить) и по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="0e926-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that can't be verified), and so on.</span></span> <span data-ttu-id="0e926-108">После некоторых из этих состояний приложение может восстановиться, после других — нет.</span><span class="sxs-lookup"><span data-stu-id="0e926-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="0e926-109">В большинстве случаев вы можете выполнить восстановление после большинства исключений в приложении, но не после исключений среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0e926-109">Although you can recover from most application exceptions, you can't recover from most runtime exceptions.</span></span>

<span data-ttu-id="0e926-110">В .NET исключение — это объект, наследуемый от класса <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e926-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0e926-111">Исключение создается из области кода, где произошла проблема.</span><span class="sxs-lookup"><span data-stu-id="0e926-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="0e926-112">Исключение передается вверх по стеку до тех пор, пока его не обработает приложение либо программа не завершится.</span><span class="sxs-lookup"><span data-stu-id="0e926-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="0e926-113">Исключения и традиционные методы обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="0e926-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="0e926-114">Традиционно модели обработки ошибок разных языков программирования основываются либо на уникальном для языка способе обнаружения ошибок и отыскании для них обработчиков, либо на механизме обработки ошибок, предоставляемом операционной системой.</span><span class="sxs-lookup"><span data-stu-id="0e926-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="0e926-115">Способ обработки исключений, реализуемый в .NET, обладает следующими преимуществами:</span><span class="sxs-lookup"><span data-stu-id="0e926-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="0e926-116">Создание и обработка исключений работают одинаково для языков программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="0e926-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="0e926-117">Не требует определенного синтаксиса языка для обработки исключений, а позволяет каждому языку определить собственный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0e926-117">Doesn't require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="0e926-118">Исключения можно создавать между разными процессами и даже компьютерами.</span><span class="sxs-lookup"><span data-stu-id="0e926-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="0e926-119">В приложение можно добавить код обработки исключений для повышения надежности программы.</span><span class="sxs-lookup"><span data-stu-id="0e926-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="0e926-120">Исключения обеспечивают ряд преимуществ по сравнению с другими методами уведомления об ошибках, например кодами возврата.</span><span class="sxs-lookup"><span data-stu-id="0e926-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="0e926-121">Сбои не остаются незамеченными, так как среда выполнения завершает работу приложения при наличии необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="0e926-121">Failures don't go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="0e926-122">Недопустимые значения не распространяются по системе из-за того, что код не способен выполнить проверку кода возврата ошибки.</span><span class="sxs-lookup"><span data-stu-id="0e926-122">Invalid values don't continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span>

## <a name="common-exceptions"></a><span data-ttu-id="0e926-123">Часто встречающиеся исключения</span><span class="sxs-lookup"><span data-stu-id="0e926-123">Common exceptions</span></span>

<span data-ttu-id="0e926-124">В следующей таблице перечислены некоторые общие исключения с примерами возможных причин.</span><span class="sxs-lookup"><span data-stu-id="0e926-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="0e926-125">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="0e926-125">Exception type</span></span> | <span data-ttu-id="0e926-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="0e926-126">Description</span></span> | <span data-ttu-id="0e926-127">Пример</span><span class="sxs-lookup"><span data-stu-id="0e926-127">Example</span></span> |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | <span data-ttu-id="0e926-128">Базовый класс для всех исключений.</span><span class="sxs-lookup"><span data-stu-id="0e926-128">Base class for all exceptions.</span></span> | <span data-ttu-id="0e926-129">Отсутствует (используйте производный класс этого исключения).</span><span class="sxs-lookup"><span data-stu-id="0e926-129">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <span data-ttu-id="0e926-130">Вызывается средой выполнения только при неправильной индексации массива.</span><span class="sxs-lookup"><span data-stu-id="0e926-130">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="0e926-131">Индексирование массива вне допустимого диапазона:</span><span class="sxs-lookup"><span data-stu-id="0e926-131">Indexing an array outside its valid range:</span></span> <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | <span data-ttu-id="0e926-132">Вызывается средой выполнения только в том случае, если имеется ссылка на пустой объект.</span><span class="sxs-lookup"><span data-stu-id="0e926-132">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | <span data-ttu-id="0e926-133">Вызывается методами в недопустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="0e926-133">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="0e926-134">Вызов `Enumerator.MoveNext()` после удаления элемента из базовой коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e926-134">Calling `Enumerator.MoveNext()` after removing an item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <span data-ttu-id="0e926-135">Базовый класс для всех исключений аргументов.</span><span class="sxs-lookup"><span data-stu-id="0e926-135">Base class for all argument exceptions.</span></span> | <span data-ttu-id="0e926-136">Отсутствует (используйте производный класс этого исключения).</span><span class="sxs-lookup"><span data-stu-id="0e926-136">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <span data-ttu-id="0e926-137">Вызывается методами, которые не допускают пустой аргумент.</span><span class="sxs-lookup"><span data-stu-id="0e926-137">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | <span data-ttu-id="0e926-138">Вызывается методами, проверяющими попадание аргументов в заданный диапазон.</span><span class="sxs-lookup"><span data-stu-id="0e926-138">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="0e926-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0e926-139">See also</span></span>

- [<span data-ttu-id="0e926-140">Класс Exception и его свойства</span><span class="sxs-lookup"><span data-stu-id="0e926-140">Exception Class and Properties</span></span>](exception-class-and-properties.md)  
- [<span data-ttu-id="0e926-141">Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений</span><span class="sxs-lookup"><span data-stu-id="0e926-141">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)  
- [<span data-ttu-id="0e926-142">Практическое руководство. Использование определенных исключений в блоке catch</span><span class="sxs-lookup"><span data-stu-id="0e926-142">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)  
- [<span data-ttu-id="0e926-143">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="0e926-143">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)  
- [<span data-ttu-id="0e926-144">Практическое руководство. Создание пользовательских исключений</span><span class="sxs-lookup"><span data-stu-id="0e926-144">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)  
- [<span data-ttu-id="0e926-145">Использование обработчиков исключений с пользовательской фильтрацией</span><span class="sxs-lookup"><span data-stu-id="0e926-145">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)  
- [<span data-ttu-id="0e926-146">Практическое руководство. Использование блоков Finally</span><span class="sxs-lookup"><span data-stu-id="0e926-146">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)  
- [<span data-ttu-id="0e926-147">Обработка исключений COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="0e926-147">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)  
- [<span data-ttu-id="0e926-148">Рекомендации по обработке исключений</span><span class="sxs-lookup"><span data-stu-id="0e926-148">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)  
- <span data-ttu-id="0e926-149">[What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Что нужно знать всем разработчикам об исключениях в среде выполнения).</span><span class="sxs-lookup"><span data-stu-id="0e926-149">[What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>
