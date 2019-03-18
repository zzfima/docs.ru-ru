---
title: Лучшие методики обработки исключений
ms.date: 12/05.2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: e069e9556b02221a91dafdd9f224940aed8476b8
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845938"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="2891c-102">Лучшие методики обработки исключений</span><span class="sxs-lookup"><span data-stu-id="2891c-102">Best practices for exceptions</span></span>

<span data-ttu-id="2891c-103">Хорошо спроектированное приложение обрабатывает исключения и ошибки, чтобы предотвратить сбои приложения.</span><span class="sxs-lookup"><span data-stu-id="2891c-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="2891c-104">В этом разделе описываются рекомендации по обработке и созданию исключений.</span><span class="sxs-lookup"><span data-stu-id="2891c-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a><span data-ttu-id="2891c-105">Использование блоков try/catch/finally для восстановления после ошибок или высвобождения ресурсов</span><span class="sxs-lookup"><span data-stu-id="2891c-105">Use try/catch/finally blocks to recover from errors or release resources</span></span>

<span data-ttu-id="2891c-106">Используйте блоки `try`/`catch`, выделив с их помощью код, который потенциально может явиться источником исключения, ***таким образом*** можно будет выполнить восстановление кода после возникновения этого исключения.</span><span class="sxs-lookup"><span data-stu-id="2891c-106">Use `try`/`catch` blocks around code that can potentially generate an exception ***and*** your code can recover from that exception.</span></span> <span data-ttu-id="2891c-107">В блоках `catch` следует всегда упорядочивать исключения от более производных к менее производным.</span><span class="sxs-lookup"><span data-stu-id="2891c-107">In `catch` blocks, always order exceptions from the most derived to the least derived.</span></span> <span data-ttu-id="2891c-108">Все исключения, производные от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="2891c-108">All exceptions derive from <xref:System.Exception>.</span></span> <span data-ttu-id="2891c-109">Более производные исключения не обрабатываются предложением catch, которому предшествует предложение catch для базового класса исключения.</span><span class="sxs-lookup"><span data-stu-id="2891c-109">More derived exceptions are not handled by a catch clause that is preceded by a catch clause for a base exception class.</span></span> <span data-ttu-id="2891c-110">Если ваш код не удается восстановить после возникновения исключения, не перехватывайте это исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-110">When your code cannot recover from an exception, don't catch that exception.</span></span> <span data-ttu-id="2891c-111">Включите методы выше по стеку вызовов для восстановления по мере возможности.</span><span class="sxs-lookup"><span data-stu-id="2891c-111">Enable methods further up the call stack to recover if possible.</span></span>

<span data-ttu-id="2891c-112">Очистите ресурсы, выделенные с помощью инструкций `using` или блоков `finally`.</span><span class="sxs-lookup"><span data-stu-id="2891c-112">Clean up resources allocated with either `using` statements, or `finally` blocks.</span></span> <span data-ttu-id="2891c-113">Рекомендуется использовать инструкции `using` для автоматической очистки ресурсов при возникновении исключений.</span><span class="sxs-lookup"><span data-stu-id="2891c-113">Prefer `using` statements to automatically clean up resources when exceptions are thrown.</span></span> <span data-ttu-id="2891c-114">Используйте блоки `finally`, чтобы очистить ресурсы, которые не реализуют <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="2891c-114">Use `finally` blocks to clean up resources that don't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="2891c-115">Код в предложении `finally` выполняется почти всегда — даже при возникновении исключений.</span><span class="sxs-lookup"><span data-stu-id="2891c-115">Code in a `finally` clause is almost always executed even when exceptions are thrown.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="2891c-116">Обработка общих условий без выдачи исключений</span><span class="sxs-lookup"><span data-stu-id="2891c-116">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="2891c-117">Для условий, которые могут возникнуть, но способны вызвать исключение, рекомендуется реализовать обработку таким способом, который позволит избежать исключения.</span><span class="sxs-lookup"><span data-stu-id="2891c-117">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="2891c-118">Например, при попытке закрыть уже закрытое подключение возникает `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="2891c-118">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="2891c-119">Этого можно избежать, используя оператор `if` для проверки состояния подключения перед попыткой закрыть его.</span><span class="sxs-lookup"><span data-stu-id="2891c-119">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

<span data-ttu-id="2891c-120">Если состояние подключения перед закрытием не проверяется, исключение `InvalidOperationException` можно перехватить.</span><span class="sxs-lookup"><span data-stu-id="2891c-120">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

<span data-ttu-id="2891c-121">Выбор конкретного способа зависит от того, насколько часто ожидается возникновение данного события.</span><span class="sxs-lookup"><span data-stu-id="2891c-121">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="2891c-122">Используйте обработку исключений, если событие не происходит очень часто, то есть если событие носит действительно исключительный характер и указывает на ошибку (например, в случае неожиданного конца файла).</span><span class="sxs-lookup"><span data-stu-id="2891c-122">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="2891c-123">При использовании обработки исключений в обычных условиях выполняется меньше кода.</span><span class="sxs-lookup"><span data-stu-id="2891c-123">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="2891c-124">Если событие происходит регулярно в рамках нормальной работы программы, выполняйте проверку на наличие ошибок прямо в коде.</span><span class="sxs-lookup"><span data-stu-id="2891c-124">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="2891c-125">Проверка на наличие распространенных условий ошибки позволяет выполнять меньший объем кода благодаря устранению исключений.</span><span class="sxs-lookup"><span data-stu-id="2891c-125">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="2891c-126">Устранение исключений при разработке классов</span><span class="sxs-lookup"><span data-stu-id="2891c-126">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="2891c-127">Класс может предоставлять методы и свойства, позволяющие избежать вызова, способного выдать исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-127">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="2891c-128">Например, класс <xref:System.IO.FileStream> содержит методы, позволяющие определить, достигнут ли конец файла.</span><span class="sxs-lookup"><span data-stu-id="2891c-128">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="2891c-129">Это позволяет избежать появления исключения, создаваемого в случае выполнения чтения после окончания файла.</span><span class="sxs-lookup"><span data-stu-id="2891c-129">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="2891c-130">В следующем примере показан способ чтения до конца файла без выдачи исключения.</span><span class="sxs-lookup"><span data-stu-id="2891c-130">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

<span data-ttu-id="2891c-131">Другой способ устранения исключений заключается в том, что для наиболее общих и часто встречающихся ошибок следует возвращать значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2891c-131">Another way to avoid exceptions is to return `null` for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="2891c-132">Такие ошибки могут относиться к обычному потоку управления.</span><span class="sxs-lookup"><span data-stu-id="2891c-132">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="2891c-133">Возвращая значение `null` в таких случаях, можно сократить влияние на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="2891c-133">By returning `null` in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="2891c-134">Выдача исключений вместо возврата кода ошибки</span><span class="sxs-lookup"><span data-stu-id="2891c-134">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="2891c-135">Исключения гарантируют, что сбои не останутся незамеченными из-за того, что вызывающий код не проверил код возврата.</span><span class="sxs-lookup"><span data-stu-id="2891c-135">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span>

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="2891c-136">Использование предопределенных типов исключений .NET</span><span class="sxs-lookup"><span data-stu-id="2891c-136">Use the predefined .NET exception types</span></span>

<span data-ttu-id="2891c-137">Создавайте новый класс исключений, только если предопределенное исключение не подходит.</span><span class="sxs-lookup"><span data-stu-id="2891c-137">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="2891c-138">Например:</span><span class="sxs-lookup"><span data-stu-id="2891c-138">For example:</span></span>

- <span data-ttu-id="2891c-139">Вызывайте исключение <xref:System.InvalidOperationException>, если значение свойства или вызов метода не соответствуют текущему состоянию объекта.</span><span class="sxs-lookup"><span data-stu-id="2891c-139">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="2891c-140">Порождайте исключение <xref:System.ArgumentException> или одного из предварительно определенных классов, которые являются производными от <xref:System.ArgumentException>, если передаются недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="2891c-140">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="2891c-141">Завершайте имена классов исключений словом `Exception`</span><span class="sxs-lookup"><span data-stu-id="2891c-141">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="2891c-142">Если требуется пользовательское исключение, присвойте ему соответствующее имя и сделайте его производным от класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="2891c-142">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="2891c-143">Например:</span><span class="sxs-lookup"><span data-stu-id="2891c-143">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="2891c-144">Включение трех конструкторов в пользовательские классы исключений</span><span class="sxs-lookup"><span data-stu-id="2891c-144">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="2891c-145">При создании собственных классов исключений можно использовать по меньшей мере три общих конструктора: конструктор по умолчанию, конструктор, принимающий строковое сообщение, и конструктор, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-145">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="2891c-146"><xref:System.Exception.%23ctor>, использующий значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2891c-146"><xref:System.Exception.%23ctor>, which uses default values.</span></span>

* <span data-ttu-id="2891c-147"><xref:System.Exception.%23ctor%28System.String%29>, принимающий строковое сообщение.</span><span class="sxs-lookup"><span data-stu-id="2891c-147"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>

* <span data-ttu-id="2891c-148"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-148"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>

<span data-ttu-id="2891c-149">Пример см. в статье [Практическое руководство. Создание пользовательских исключений](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2891c-149">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="2891c-150">Обеспечение доступности данных об исключении при удаленном выполнении кода</span><span class="sxs-lookup"><span data-stu-id="2891c-150">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="2891c-151">При создании пользовательских исключений следует обеспечить доступность метаданных исключений для удаленно исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="2891c-151">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span>

<span data-ttu-id="2891c-152">Например, для реализаций .NET, которые поддерживают домены приложений, могут возникать исключения для этих доменов.</span><span class="sxs-lookup"><span data-stu-id="2891c-152">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="2891c-153">Предположим, что домен приложения А создает домен приложения В, который выполняет код, вызывающий исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-153">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="2891c-154">Чтобы домен приложения A правильно перехватил и обработал исключение, он должен найти сборку, которая содержит исключение, порожденное доменом приложения B. Если домен приложения B порождает исключение, содержащееся в сборке в его базовой папке приложения, но не в базовой папке приложения домена A, то домен приложения A не сможет найти исключение и среда CLR породит исключение <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="2891c-154">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="2891c-155">Чтобы избежать такой ситуации, можно развернуть сборку, содержащую сведения об исключении, двумя способами:</span><span class="sxs-lookup"><span data-stu-id="2891c-155">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="2891c-156">Поместите эту сборку в общую базу приложения, совместно используемую обоими доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="2891c-156">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="2891c-157">\- или -</span><span class="sxs-lookup"><span data-stu-id="2891c-157">\- or -</span></span>

- <span data-ttu-id="2891c-158">Если у этих доменов нет общей базы приложения, то подпишите сборку, содержащую сведения об исключении, строгим именем и разверните ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="2891c-158">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="2891c-159">Использование грамматически правильных сообщений об ошибке</span><span class="sxs-lookup"><span data-stu-id="2891c-159">Use grammatically correct error messages</span></span>

<span data-ttu-id="2891c-160">Составляйте понятные предложения, указывая в конце знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="2891c-160">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="2891c-161">Каждое предложение в строке, назначенной свойству <xref:System.Exception.Message?displayProperty=nameWithType>, должно заканчиваться точкой.</span><span class="sxs-lookup"><span data-stu-id="2891c-161">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="2891c-162">Например, "Таблица журнала переполнена."</span><span class="sxs-lookup"><span data-stu-id="2891c-162">For example, "The log table has overflowed."</span></span> <span data-ttu-id="2891c-163">будет подходящей строкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="2891c-163">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="2891c-164">Включение локализованной строки сообщения в каждое исключение</span><span class="sxs-lookup"><span data-stu-id="2891c-164">Include a localized string message in every exception</span></span>

<span data-ttu-id="2891c-165">Сообщение об ошибке, показываемое пользователю, извлекается из свойства <xref:System.Exception.Message?displayProperty=nameWithType> созданного исключения, а не из имени класса исключения.</span><span class="sxs-lookup"><span data-stu-id="2891c-165">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="2891c-166">Как правило, вы присваиваете значение свойству <xref:System.Exception.Message?displayProperty=nameWithType>, передав строку сообщения аргументу `message` [конструктора исключений](xref:System.Exception.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="2891c-166">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span>

<span data-ttu-id="2891c-167">Для локализованных приложений необходимо предоставить строку локализованного сообщения для всех исключений, которые может создавать приложение.</span><span class="sxs-lookup"><span data-stu-id="2891c-167">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="2891c-168">Используйте файлы ресурсов для предоставления локализованных сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2891c-168">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="2891c-169">Сведения о локализации приложений и получении локализованных строк см. в разделе [Ресурсы в классических приложениях](../../framework/resources/index.md) и <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2891c-169">For information on localizing applications and retrieving localized strings, see [Resources in Desktop Apps](../../framework/resources/index.md) and <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="2891c-170">Предоставление дополнительных свойств в пользовательских исключениях по мере необходимости</span><span class="sxs-lookup"><span data-stu-id="2891c-170">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="2891c-171">Дополнительные сведения (кроме строки настраиваемого сообщения) включайте в исключение только в случаях, когда в соответствии со сценарием программирования такие дополнительные сведения могут оказаться полезными.</span><span class="sxs-lookup"><span data-stu-id="2891c-171">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="2891c-172">Например, исключение <xref:System.IO.FileNotFoundException> предоставляет свойство <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="2891c-172">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="2891c-173">Размещение операторов throw для удобной трассировки стека</span><span class="sxs-lookup"><span data-stu-id="2891c-173">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="2891c-174">Трассировка стека начинается в операторе, породившем исключение, и завершается оператором `catch`, перехватывающим это исключение.</span><span class="sxs-lookup"><span data-stu-id="2891c-174">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="2891c-175">Использование методов построителя исключений</span><span class="sxs-lookup"><span data-stu-id="2891c-175">Use exception builder methods</span></span>

<span data-ttu-id="2891c-176">Обычно класс генерирует одно и то же исключение из различных мест своей реализации.</span><span class="sxs-lookup"><span data-stu-id="2891c-176">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="2891c-177">Чтобы избежать повторения кода, используйте вспомогательные методы, создающие исключение и затем возвращающие его.</span><span class="sxs-lookup"><span data-stu-id="2891c-177">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="2891c-178">Например:</span><span class="sxs-lookup"><span data-stu-id="2891c-178">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

<span data-ttu-id="2891c-179">В некоторых случаях для создания исключения лучше воспользоваться конструктором исключений.</span><span class="sxs-lookup"><span data-stu-id="2891c-179">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="2891c-180">В качестве примера можно привести класс глобальных исключений, например <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="2891c-180">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a><span data-ttu-id="2891c-181">Восстановление состояния, если методы не выполняются из-за исключения</span><span class="sxs-lookup"><span data-stu-id="2891c-181">Restore state when methods don't complete due to exceptions</span></span>

<span data-ttu-id="2891c-182">Вызывающие объекты должны предполагать, что при создании исключения из метода не возникают побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="2891c-182">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="2891c-183">Например, если у вас есть код, который передает деньги, списывая их с одного счета и внося на другой, и при начислении средств возникает исключение, списание средств применяться не должно.</span><span class="sxs-lookup"><span data-stu-id="2891c-183">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

<span data-ttu-id="2891c-184">Описанный выше метод непосредственно не создает исключения, однако при его написании необходимо соблюдать осторожность, чтобы при сбое операции начисления списание отменялось.</span><span class="sxs-lookup"><span data-stu-id="2891c-184">The method above does not directly throw any exceptions, but must be written defensively so that if the deposit operation fails, the withdrawal is reversed.</span></span>

<span data-ttu-id="2891c-185">Один из способов обработки в этой ситуации заключается в перехвате всех исключений, выданных транзакцией начисления средств, и откате транзакции списания средств.</span><span class="sxs-lookup"><span data-stu-id="2891c-185">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

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

<span data-ttu-id="2891c-186">В этом примере показано использование `throw` для повторного порождения исходного исключения. Это позволяет вызывающим объектам проще установить фактическую причину проблемы, не обращаясь к свойству <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="2891c-186">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="2891c-187">Альтернативным способом является выдача нового исключения с включением исходного исключения в качестве внутреннего:</span><span class="sxs-lookup"><span data-stu-id="2891c-187">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

## <a name="see-also"></a><span data-ttu-id="2891c-188">См. также</span><span class="sxs-lookup"><span data-stu-id="2891c-188">See also</span></span>

- [<span data-ttu-id="2891c-189">Исключения</span><span class="sxs-lookup"><span data-stu-id="2891c-189">Exceptions</span></span>](index.md)
