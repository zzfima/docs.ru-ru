---
title: Лучшие методики обработки исключений — .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 1de231b01e3fa97e78a87ae6b0595a9b5536374e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160174"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="cc5cb-102">Лучшие методики обработки исключений</span><span class="sxs-lookup"><span data-stu-id="cc5cb-102">Best practices for exceptions</span></span>

<span data-ttu-id="cc5cb-103">Хорошо спроектированное приложение обрабатывает исключения и ошибки, чтобы предотвратить сбои приложения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="cc5cb-104">В этом разделе описываются рекомендации по обработке и созданию исключений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a><span data-ttu-id="cc5cb-105">Использование блоков try/catch/finally для восстановления после ошибок или высвобождения ресурсов</span><span class="sxs-lookup"><span data-stu-id="cc5cb-105">Use try/catch/finally blocks to recover from errors or release resources</span></span>

<span data-ttu-id="cc5cb-106">Используйте блоки `try`/`catch`, выделив с их помощью код, который потенциально может явиться источником исключения, ***таким образом*** можно будет выполнить восстановление кода после возникновения этого исключения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-106">Use `try`/`catch` blocks around code that can potentially generate an exception ***and*** your code can recover from that exception.</span></span> <span data-ttu-id="cc5cb-107">В блоках `catch` следует всегда упорядочивать исключения от более производных к менее производным.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-107">In `catch` blocks, always order exceptions from the most derived to the least derived.</span></span> <span data-ttu-id="cc5cb-108">Все исключения, производные от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-108">All exceptions derive from <xref:System.Exception>.</span></span> <span data-ttu-id="cc5cb-109">Более производные исключения не обрабатываются предложением catch, которому предшествует предложение catch для базового класса исключения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-109">More derived exceptions are not handled by a catch clause that is preceded by a catch clause for a base exception class.</span></span> <span data-ttu-id="cc5cb-110">Если ваш код не удается восстановить после возникновения исключения, не перехватывайте это исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-110">When your code cannot recover from an exception, don't catch that exception.</span></span> <span data-ttu-id="cc5cb-111">Включите методы выше по стеку вызовов для восстановления по мере возможности.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-111">Enable methods further up the call stack to recover if possible.</span></span>

<span data-ttu-id="cc5cb-112">Очистите ресурсы, выделенные с помощью инструкций `using` или блоков `finally`.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-112">Clean up resources allocated with either `using` statements, or `finally` blocks.</span></span> <span data-ttu-id="cc5cb-113">Рекомендуется использовать инструкции `using` для автоматической очистки ресурсов при возникновении исключений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-113">Prefer `using` statements to automatically clean up resources when exceptions are thrown.</span></span> <span data-ttu-id="cc5cb-114">Используйте блоки `finally`, чтобы очистить ресурсы, которые не реализуют <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-114">Use `finally` blocks to clean up resources that don't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="cc5cb-115">Код в предложении `finally` выполняется почти всегда — даже при возникновении исключений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-115">Code in a `finally` clause is almost always executed even when exceptions are thrown.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="cc5cb-116">Обработка общих условий без выдачи исключений</span><span class="sxs-lookup"><span data-stu-id="cc5cb-116">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="cc5cb-117">Для условий, которые могут возникнуть, но способны вызвать исключение, рекомендуется реализовать обработку таким способом, который позволит избежать исключения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-117">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="cc5cb-118">Например, при попытке закрыть уже закрытое подключение возникает `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-118">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="cc5cb-119">Этого можно избежать, используя оператор `if` для проверки состояния подключения перед попыткой закрыть его.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-119">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

<span data-ttu-id="cc5cb-120">Если состояние подключения перед закрытием не проверяется, исключение `InvalidOperationException` можно перехватить.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-120">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

<span data-ttu-id="cc5cb-121">Выбор конкретного способа зависит от того, насколько часто ожидается возникновение данного события.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-121">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="cc5cb-122">Используйте обработку исключений, если событие не происходит очень часто, то есть если событие носит действительно исключительный характер и указывает на ошибку (например, в случае неожиданного конца файла).</span><span class="sxs-lookup"><span data-stu-id="cc5cb-122">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="cc5cb-123">При использовании обработки исключений в обычных условиях выполняется меньше кода.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-123">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="cc5cb-124">Если событие происходит регулярно в рамках нормальной работы программы, выполняйте проверку на наличие ошибок прямо в коде.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-124">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="cc5cb-125">Проверка на наличие распространенных условий ошибки позволяет выполнять меньший объем кода благодаря устранению исключений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-125">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="cc5cb-126">Устранение исключений при разработке классов</span><span class="sxs-lookup"><span data-stu-id="cc5cb-126">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="cc5cb-127">Класс может предоставлять методы и свойства, позволяющие избежать вызова, способного выдать исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-127">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="cc5cb-128">Например, класс <xref:System.IO.FileStream> содержит методы, позволяющие определить, достигнут ли конец файла.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-128">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="cc5cb-129">Это позволяет избежать появления исключения, создаваемого в случае выполнения чтения после окончания файла.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-129">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="cc5cb-130">В следующем примере показан способ чтения до конца файла без выдачи исключения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-130">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

<span data-ttu-id="cc5cb-131">Другой способ устранения исключений заключается в том, что для наиболее общих и часто встречающихся ошибок следует возвращать значение NULL (или значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cc5cb-131">Another way to avoid exceptions is to return null (or default) for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="cc5cb-132">Такие ошибки могут относиться к обычному потоку управления.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-132">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="cc5cb-133">Возвращая значение NULL (или значение по умолчанию) в таких случаях, можно уменьшить влияние на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-133">By returning null (or default) in these cases, you minimize the performance impact to an app.</span></span>

<span data-ttu-id="cc5cb-134">При выборе типа значения `Nullable<T>` или значения по умолчанию в качестве индикатора ошибки учитывайте особенности приложения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-134">For value types, whether to use `Nullable<T>` or default as your error indicator is something to consider for your particular app.</span></span> <span data-ttu-id="cc5cb-135">При использовании `Nullable<Guid>``default` принимает значение `null`, а не `Guid.Empty`.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-135">By using `Nullable<Guid>`, `default` becomes `null` instead of `Guid.Empty`.</span></span> <span data-ttu-id="cc5cb-136">В некоторых случаях добавление `Nullable<T>` помогает более точно определить, присутствует или отсутствует значение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-136">Some times, adding `Nullable<T>` can make it clearer when a value is present or absent.</span></span> <span data-ttu-id="cc5cb-137">Но в определенных ситуациях добавление `Nullable<T>` может привести к созданию лишних необязательных случаев для проверки, что повышает вероятность ошибки.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-137">Other times, adding `Nullable<T>` can create extra cases to check that aren't necessary, and only serve to create potential sources of errors.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="cc5cb-138">Выдача исключений вместо возврата кода ошибки</span><span class="sxs-lookup"><span data-stu-id="cc5cb-138">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="cc5cb-139">Исключения гарантируют, что сбои не останутся незамеченными из-за того, что вызывающий код не проверил код возврата.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-139">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span>

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="cc5cb-140">Использование предопределенных типов исключений .NET</span><span class="sxs-lookup"><span data-stu-id="cc5cb-140">Use the predefined .NET exception types</span></span>

<span data-ttu-id="cc5cb-141">Создавайте новый класс исключений, только если предопределенное исключение не подходит.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-141">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="cc5cb-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-142">For example:</span></span>

- <span data-ttu-id="cc5cb-143">Вызывайте исключение <xref:System.InvalidOperationException>, если значение свойства или вызов метода не соответствуют текущему состоянию объекта.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-143">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="cc5cb-144">Порождайте исключение <xref:System.ArgumentException> или одного из предварительно определенных классов, которые являются производными от <xref:System.ArgumentException>, если передаются недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-144">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="cc5cb-145">Завершайте имена классов исключений словом `Exception`</span><span class="sxs-lookup"><span data-stu-id="cc5cb-145">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="cc5cb-146">Если требуется пользовательское исключение, присвойте ему соответствующее имя и сделайте его производным от класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-146">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="cc5cb-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-147">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="cc5cb-148">Включение трех конструкторов в пользовательские классы исключений</span><span class="sxs-lookup"><span data-stu-id="cc5cb-148">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="cc5cb-149">При создании собственных классов исключений можно использовать по меньшей мере три общих конструктора: конструктор без параметров, конструктор, принимающий строковое сообщение, и конструктор, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-149">Use at least the three common constructors when creating your own exception classes: the parameterless constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

- <span data-ttu-id="cc5cb-150"><xref:System.Exception.%23ctor>, использующий значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-150"><xref:System.Exception.%23ctor>, which uses default values.</span></span>

- <span data-ttu-id="cc5cb-151"><xref:System.Exception.%23ctor%28System.String%29>, принимающий строковое сообщение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-151"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>

- <span data-ttu-id="cc5cb-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, принимающий строковое сообщение и внутреннее исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>

<span data-ttu-id="cc5cb-153">Пример см. в статье [Практическое руководство. Создание пользовательских исключений](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="cc5cb-153">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="cc5cb-154">Обеспечение доступности данных об исключении при удаленном выполнении кода</span><span class="sxs-lookup"><span data-stu-id="cc5cb-154">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="cc5cb-155">При создании пользовательских исключений следует обеспечить доступность метаданных исключений для удаленно исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-155">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span>

<span data-ttu-id="cc5cb-156">Например, для реализаций .NET, которые поддерживают домены приложений, могут возникать исключения для этих доменов.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-156">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="cc5cb-157">Предположим, что домен приложения А создает домен приложения В, который выполняет код, вызывающий исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-157">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="cc5cb-158">Чтобы домен приложения A правильно перехватил и обработал исключение, он должен найти сборку, которая содержит исключение, порожденное доменом приложения B. Если домен приложения B порождает исключение, содержащееся в сборке в его базовой папке приложения, но не в базовой папке приложения домена A, то домен приложения A не сможет найти исключение и среда CLR породит исключение <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-158">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="cc5cb-159">Чтобы избежать такой ситуации, можно развернуть сборку, содержащую сведения об исключении, двумя способами:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-159">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="cc5cb-160">Поместите эту сборку в общую базу приложения, совместно используемую обоими доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-160">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="cc5cb-161">\- или -</span><span class="sxs-lookup"><span data-stu-id="cc5cb-161">\- or -</span></span>

- <span data-ttu-id="cc5cb-162">Если у этих доменов нет общей базы приложения, то подпишите сборку, содержащую сведения об исключении, строгим именем и разверните ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-162">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="cc5cb-163">Использование грамматически правильных сообщений об ошибке</span><span class="sxs-lookup"><span data-stu-id="cc5cb-163">Use grammatically correct error messages</span></span>

<span data-ttu-id="cc5cb-164">Составляйте понятные предложения, указывая в конце знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-164">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="cc5cb-165">Каждое предложение в строке, назначенной свойству <xref:System.Exception.Message?displayProperty=nameWithType>, должно заканчиваться точкой.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-165">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="cc5cb-166">Например, "Таблица журнала переполнена."</span><span class="sxs-lookup"><span data-stu-id="cc5cb-166">For example, "The log table has overflowed."</span></span> <span data-ttu-id="cc5cb-167">будет подходящей строкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-167">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="cc5cb-168">Включение локализованной строки сообщения в каждое исключение</span><span class="sxs-lookup"><span data-stu-id="cc5cb-168">Include a localized string message in every exception</span></span>

<span data-ttu-id="cc5cb-169">Сообщение об ошибке, показываемое пользователю, извлекается из свойства <xref:System.Exception.Message?displayProperty=nameWithType> созданного исключения, а не из имени класса исключения.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-169">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="cc5cb-170">Как правило, вы присваиваете значение свойству <xref:System.Exception.Message?displayProperty=nameWithType>, передав строку сообщения аргументу `message`[конструктора исключений](xref:System.Exception.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="cc5cb-170">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span>

<span data-ttu-id="cc5cb-171">Для локализованных приложений необходимо предоставить строку локализованного сообщения для всех исключений, которые может создавать приложение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-171">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="cc5cb-172">Используйте файлы ресурсов для предоставления локализованных сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-172">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="cc5cb-173">Сведения о локализации приложений и извлечении локализованных строк см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-173">For information on localizing applications and retrieving localized strings, see the following articles:</span></span>

- [<span data-ttu-id="cc5cb-174">Пошаговое руководство. Создание пользовательских исключений с локализованными сообщениями об исключениях</span><span class="sxs-lookup"><span data-stu-id="cc5cb-174">How to: create user-defined exceptions with localized exception messages</span></span>](how-to-create-localized-exception-messages.md)
- [<span data-ttu-id="cc5cb-175">Ресурсы в приложениях для настольных систем</span><span class="sxs-lookup"><span data-stu-id="cc5cb-175">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="cc5cb-176">Предоставление дополнительных свойств в пользовательских исключениях по мере необходимости</span><span class="sxs-lookup"><span data-stu-id="cc5cb-176">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="cc5cb-177">Дополнительные сведения (кроме строки настраиваемого сообщения) включайте в исключение только в случаях, когда в соответствии со сценарием программирования такие дополнительные сведения могут оказаться полезными.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-177">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="cc5cb-178">Например, исключение <xref:System.IO.FileNotFoundException> предоставляет свойство <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-178">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="cc5cb-179">Размещение операторов throw для удобной трассировки стека</span><span class="sxs-lookup"><span data-stu-id="cc5cb-179">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="cc5cb-180">Трассировка стека начинается в операторе, породившем исключение, и завершается оператором `catch`, перехватывающим это исключение.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-180">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="cc5cb-181">Использование методов построителя исключений</span><span class="sxs-lookup"><span data-stu-id="cc5cb-181">Use exception builder methods</span></span>

<span data-ttu-id="cc5cb-182">Обычно класс генерирует одно и то же исключение из различных мест своей реализации.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-182">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="cc5cb-183">Чтобы избежать повторения кода, используйте вспомогательные методы, создающие исключение и затем возвращающие его.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-183">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="cc5cb-184">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-184">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

<span data-ttu-id="cc5cb-185">В некоторых случаях для создания исключения лучше воспользоваться конструктором исключений.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-185">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="cc5cb-186">В качестве примера можно привести класс глобальных исключений, например <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-186">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a><span data-ttu-id="cc5cb-187">Восстановление состояния, если методы не выполняются из-за исключения</span><span class="sxs-lookup"><span data-stu-id="cc5cb-187">Restore state when methods don't complete due to exceptions</span></span>

<span data-ttu-id="cc5cb-188">Вызывающие объекты должны предполагать, что при создании исключения из метода не возникают побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-188">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="cc5cb-189">Например, если у вас есть код, который передает деньги, списывая их с одного счета и внося на другой, и при начислении средств возникает исключение, списание средств применяться не должно.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-189">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

<span data-ttu-id="cc5cb-190">Описанный выше метод непосредственно не создает исключения, однако при его написании необходимо соблюдать осторожность, чтобы при сбое операции начисления списание отменялось.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-190">The method above does not directly throw any exceptions, but must be written defensively so that if the deposit operation fails, the withdrawal is reversed.</span></span>

<span data-ttu-id="cc5cb-191">Один из способов обработки в этой ситуации заключается в перехвате всех исключений, выданных транзакцией начисления средств, и откате транзакции списания средств.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-191">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

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

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

<span data-ttu-id="cc5cb-192">В этом примере показано использование `throw` для повторного порождения исходного исключения. Это позволяет вызывающим объектам проще установить фактическую причину проблемы, не обращаясь к свойству <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="cc5cb-192">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="cc5cb-193">Альтернативным способом является выдача нового исключения с включением исходного исключения в качестве внутреннего:</span><span class="sxs-lookup"><span data-stu-id="cc5cb-193">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a><span data-ttu-id="cc5cb-194">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc5cb-194">See also</span></span>

- [<span data-ttu-id="cc5cb-195">Исключения</span><span class="sxs-lookup"><span data-stu-id="cc5cb-195">Exceptions</span></span>](index.md)
