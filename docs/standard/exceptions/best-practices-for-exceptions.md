---
title: "Лучшие методики обработки исключений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: "28"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87f9287c3714416ee5d6b63f3c9db311bb97b131
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2017
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="767de-102">Лучшие методики обработки исключений</span><span class="sxs-lookup"><span data-stu-id="767de-102">Best practices for exceptions</span></span>

<span data-ttu-id="767de-103">Хорошо спроектированное приложение обрабатывает исключения и ошибки, чтобы предотвратить сбои приложения.</span><span class="sxs-lookup"><span data-stu-id="767de-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="767de-104">В этом разделе описываются рекомендации по обработке и созданию исключений.</span><span class="sxs-lookup"><span data-stu-id="767de-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks"></a><span data-ttu-id="767de-105">Использование блоков try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="767de-105">Use try/catch/finally blocks</span></span>

<span data-ttu-id="767de-106">Используйте блоки `try`/`catch`/`finally` для выделения кода, который может стать источником исключения.</span><span class="sxs-lookup"><span data-stu-id="767de-106">Use `try`/`catch`/`finally` blocks around code that can potentially generate an exception.</span></span> 

<span data-ttu-id="767de-107">В блоках `catch` следует всегда упорядочивать исключения от более конкретных к более общим.</span><span class="sxs-lookup"><span data-stu-id="767de-107">In `catch` blocks, always order exceptions from the most specific to the least specific.</span></span>

<span data-ttu-id="767de-108">Используйте блок `finally` для очистки ресурсов с учетом возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="767de-108">Use a `finally` block to clean up resources, whether you can recover or not.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="767de-109">Обработка общих условий без выдачи исключений</span><span class="sxs-lookup"><span data-stu-id="767de-109">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="767de-110">Для условий, которые могут возникнуть, но способны вызвать исключение, рекомендуется реализовать обработку таким способом, который позволит избежать исключения.</span><span class="sxs-lookup"><span data-stu-id="767de-110">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="767de-111">Например, при попытке закрыть уже закрытое подключение возникает `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="767de-111">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="767de-112">Этого можно избежать, используя оператор `if` для проверки состояния подключения перед попыткой закрыть его.</span><span class="sxs-lookup"><span data-stu-id="767de-112">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

<span data-ttu-id="767de-113">Если состояние подключения перед закрытием не проверяется, исключение `InvalidOperationException` можно перехватить.</span><span class="sxs-lookup"><span data-stu-id="767de-113">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

<span data-ttu-id="767de-114">Выбор конкретного способа зависит от того, насколько часто ожидается возникновение данного события.</span><span class="sxs-lookup"><span data-stu-id="767de-114">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="767de-115">Используйте обработку исключений, если событие не происходит очень часто, то есть если событие носит действительно исключительный характер и указывает на ошибку (например, в случае неожиданного конца файла).</span><span class="sxs-lookup"><span data-stu-id="767de-115">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="767de-116">При использовании обработки исключений в обычных условиях выполняется меньше кода.</span><span class="sxs-lookup"><span data-stu-id="767de-116">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="767de-117">Если событие происходит регулярно в рамках нормальной работы программы, выполняйте проверку на наличие ошибок прямо в коде.</span><span class="sxs-lookup"><span data-stu-id="767de-117">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="767de-118">Проверка на наличие распространенных условий ошибки позволяет выполнять меньший объем кода благодаря устранению исключений.</span><span class="sxs-lookup"><span data-stu-id="767de-118">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="767de-119">Устранение исключений при разработке классов</span><span class="sxs-lookup"><span data-stu-id="767de-119">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="767de-120">Класс может предоставлять методы и свойства, позволяющие избежать вызова, способного выдать исключение.</span><span class="sxs-lookup"><span data-stu-id="767de-120">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="767de-121">Например, класс <xref:System.IO.FileStream> содержит методы, позволяющие определить, достигнут ли конец файла.</span><span class="sxs-lookup"><span data-stu-id="767de-121">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="767de-122">Это позволяет избежать появления исключения, создаваемого в случае выполнения чтения после окончания файла.</span><span class="sxs-lookup"><span data-stu-id="767de-122">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="767de-123">В следующем примере показан способ чтения до конца файла без выдачи исключения.</span><span class="sxs-lookup"><span data-stu-id="767de-123">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

<span data-ttu-id="767de-124">Другой способ устранения исключений заключается в том, что для наиболее общих и часто встречающихся ошибок следует возвращать значение NULL.</span><span class="sxs-lookup"><span data-stu-id="767de-124">Another way to avoid exceptions is to return null for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="767de-125">Такие ошибки могут относиться к обычному потоку управления.</span><span class="sxs-lookup"><span data-stu-id="767de-125">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="767de-126">Возвращая значение null в таких случаях, можно сократить влияние на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="767de-126">By returning null in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="767de-127">Выдача исключений вместо возврата кода ошибки</span><span class="sxs-lookup"><span data-stu-id="767de-127">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="767de-128">Исключения гарантируют, что сбои не останутся незамеченными из-за того, что вызывающий код не проверил код возврата.</span><span class="sxs-lookup"><span data-stu-id="767de-128">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span> 

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="767de-129">Использование предопределенных типов исключений .NET</span><span class="sxs-lookup"><span data-stu-id="767de-129">Use the predefined .NET exception types</span></span>

<span data-ttu-id="767de-130">Создавайте новый класс исключений, только если предопределенное исключение не подходит.</span><span class="sxs-lookup"><span data-stu-id="767de-130">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="767de-131">Например:</span><span class="sxs-lookup"><span data-stu-id="767de-131">For example:</span></span>

- <span data-ttu-id="767de-132">Вызывайте исключение <xref:System.InvalidOperationException>, если значение свойства или вызов метода не соответствуют текущему состоянию объекта.</span><span class="sxs-lookup"><span data-stu-id="767de-132">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="767de-133">Порождайте исключение <xref:System.ArgumentException> или одного из предварительно определенных классов, которые являются производными от <xref:System.ArgumentException>, если передаются недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="767de-133">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="767de-134">Завершайте имена классов исключений словом `Exception`</span><span class="sxs-lookup"><span data-stu-id="767de-134">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="767de-135">Если требуется пользовательское исключение, присвойте ему соответствующее имя и сделайте его производным от класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="767de-135">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="767de-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="767de-136">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="767de-137">Включение трех конструкторов в пользовательские классы исключений</span><span class="sxs-lookup"><span data-stu-id="767de-137">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="767de-138">При создании собственных классов исключений можно использовать по меньшей мере три общих конструктора: конструктор по умолчанию, конструктор, принимающий строковое сообщение, и конструктор, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="767de-138">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="767de-139"><xref:System.Exception.%23ctor>, которая использует значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="767de-139"><xref:System.Exception.%23ctor>, which uses default values.</span></span>
  
* <span data-ttu-id="767de-140"><xref:System.Exception.%23ctor%28System.String%29>, принимающий строковое сообщение.</span><span class="sxs-lookup"><span data-stu-id="767de-140"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>  
  
* <span data-ttu-id="767de-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="767de-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>  
  
<span data-ttu-id="767de-142">Пример см. в разделе [Практическое руководство. Создание пользовательских исключений](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="767de-142">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="767de-143">Обеспечение доступности данных об исключении при удаленном выполнении кода</span><span class="sxs-lookup"><span data-stu-id="767de-143">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="767de-144">При создании пользовательских исключений следует обеспечить доступность метаданных исключений для удаленно исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="767de-144">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span> 

<span data-ttu-id="767de-145">Например в реализациях .NET, поддерживающие доменов приложений, исключения могут возникать между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="767de-145">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="767de-146">Предположим, что домен приложения А создает домен приложения В, который выполняет код, вызывающий исключение.</span><span class="sxs-lookup"><span data-stu-id="767de-146">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="767de-147">Чтобы домен приложения A правильно перехватил и обработал исключение, он должен найти сборку, которая содержит исключение, порожденное доменом приложения B. Если домен приложения B порождает исключение, содержащееся в сборке в его базовой папке приложения, но не в базовой папке приложения домена A, то домен приложения A не сможет найти исключение и среда CLR породит исключение <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="767de-147">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="767de-148">Чтобы избежать такой ситуации, можно развернуть сборку, содержащую сведения об исключении, двумя способами:</span><span class="sxs-lookup"><span data-stu-id="767de-148">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="767de-149">Поместите эту сборку в общую базу приложения, совместно используемую обоими доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="767de-149">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="767de-150">\- или -</span><span class="sxs-lookup"><span data-stu-id="767de-150">\- or -</span></span>

- <span data-ttu-id="767de-151">Если у этих доменов нет общей базы приложения, то подпишите сборку, содержащую сведения об исключении, строгим именем и разверните ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="767de-151">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="include-a-localized-description-string-in-every-exception"></a><span data-ttu-id="767de-152">Включение локализованной строки описания в каждое исключение</span><span class="sxs-lookup"><span data-stu-id="767de-152">Include a localized description string in every exception</span></span>

<span data-ttu-id="767de-153">Сообщение об ошибке, показываемое пользователю, извлекается из строки описания созданного исключения, а не из имени класса исключения.</span><span class="sxs-lookup"><span data-stu-id="767de-153">The error message that the user sees is derived from the description string of the exception that was thrown, and not from the name of the exception class.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="767de-154">Использование грамматически правильных сообщений об ошибке</span><span class="sxs-lookup"><span data-stu-id="767de-154">Use grammatically correct error messages</span></span>

<span data-ttu-id="767de-155">Составляйте понятные предложения, указывая в конце знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="767de-155">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="767de-156">Каждое предложение в строке описания должно заканчиваться точкой.</span><span class="sxs-lookup"><span data-stu-id="767de-156">Each sentence in a description string of an exception should end in a period.</span></span> <span data-ttu-id="767de-157">Например «переполнение таблицы журнала.»</span><span class="sxs-lookup"><span data-stu-id="767de-157">For example, "The log table has overflowed."</span></span> <span data-ttu-id="767de-158">будет подходящей строкой описания.</span><span class="sxs-lookup"><span data-stu-id="767de-158">would be an appropriate description string.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="767de-159">Предоставление дополнительных свойств в пользовательских исключениях по мере необходимости</span><span class="sxs-lookup"><span data-stu-id="767de-159">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="767de-160">Дополнительные сведения (кроме строки описания) включайте в исключение только в тех случаях, когда в соответствии со сценарием программирования такие дополнительные сведения могут оказаться полезными.</span><span class="sxs-lookup"><span data-stu-id="767de-160">Provide additional properties for an exception (in addition to the description string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="767de-161">Например, исключение <xref:System.IO.FileNotFoundException> предоставляет свойство <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="767de-161">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="767de-162">Размещение операторов throw для удобной трассировки стека</span><span class="sxs-lookup"><span data-stu-id="767de-162">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="767de-163">Трассировка стека начинается в операторе, породившем исключение, и завершается оператором `catch`, перехватывающим это исключение.</span><span class="sxs-lookup"><span data-stu-id="767de-163">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="767de-164">Использование методов построителя исключений</span><span class="sxs-lookup"><span data-stu-id="767de-164">Use exception builder methods</span></span>

<span data-ttu-id="767de-165">Обычно класс генерирует одно и то же исключение из различных мест своей реализации.</span><span class="sxs-lookup"><span data-stu-id="767de-165">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="767de-166">Чтобы избежать повторения кода, используйте вспомогательные методы, создающие исключение и затем возвращающие его.</span><span class="sxs-lookup"><span data-stu-id="767de-166">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="767de-167">Пример:</span><span class="sxs-lookup"><span data-stu-id="767de-167">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
<span data-ttu-id="767de-168">В некоторых случаях для создания исключения лучше воспользоваться конструктором исключений.</span><span class="sxs-lookup"><span data-stu-id="767de-168">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="767de-169">Примером является класс глобальных исключений, таких как <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="767de-169">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a><span data-ttu-id="767de-170">Очистка промежуточных результатов при выдаче исключения</span><span class="sxs-lookup"><span data-stu-id="767de-170">Clean up intermediate results when throwing an exception</span></span>

<span data-ttu-id="767de-171">Вызывающие объекты должны предполагать, что при создании исключения из метода не возникают побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="767de-171">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="767de-172">Например, если у вас есть код, который передает деньги, списывая их с одного счета и внося на другой, и при начислении средств возникает исключение, списание средств применяться не должно.</span><span class="sxs-lookup"><span data-stu-id="767de-172">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

<span data-ttu-id="767de-173">Один из способов обработки в этой ситуации заключается в перехвате всех исключений, выданных транзакцией начисления средств, и откате транзакции списания средств.</span><span class="sxs-lookup"><span data-stu-id="767de-173">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

<span data-ttu-id="767de-174">В этом примере показано использование `throw` для повторного порождения исходного исключения. Это позволяет вызывающим объектам проще установить фактическую причину проблемы, не обращаясь к свойству <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="767de-174">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="767de-175">Альтернативным способом является выдача нового исключения с включением исходного исключения в качестве внутреннего:</span><span class="sxs-lookup"><span data-stu-id="767de-175">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a><span data-ttu-id="767de-176">См. также</span><span class="sxs-lookup"><span data-stu-id="767de-176">See Also</span></span>  
[<span data-ttu-id="767de-177">Исключения</span><span class="sxs-lookup"><span data-stu-id="767de-177">Exceptions</span></span>](index.md)
