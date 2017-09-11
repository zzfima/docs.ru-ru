---
title: "Общие шаблоны делегатов"
description: "Сведения об общих шаблонах, позволяющих использовать делегаты в коде и избежать возникновения сильных взаимозависимостей между компонентами."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83214800fb997e9274cacfd1bae85ab07c4515a2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="common-patterns-for-delegates"></a><span data-ttu-id="25586-104">Общие шаблоны делегатов</span><span class="sxs-lookup"><span data-stu-id="25586-104">Common Patterns for Delegates</span></span>

[<span data-ttu-id="25586-105">Назад</span><span class="sxs-lookup"><span data-stu-id="25586-105">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="25586-106">Делегаты предоставляют механизм, который обеспечивает проектирование программного обеспечения с минимальной взаимозависимостью между компонентами.</span><span class="sxs-lookup"><span data-stu-id="25586-106">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="25586-107">Отличным примером такого проектирования является LINQ.</span><span class="sxs-lookup"><span data-stu-id="25586-107">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="25586-108">В модели выражений запросов LINQ делегаты применяются для обеспечения всех возможностей.</span><span class="sxs-lookup"><span data-stu-id="25586-108">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="25586-109">Рассмотрим простой пример.</span><span class="sxs-lookup"><span data-stu-id="25586-109">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="25586-110">В нем из последовательности чисел отфильтровываются только числа со значением меньше 10.</span><span class="sxs-lookup"><span data-stu-id="25586-110">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="25586-111">Метод `Where` использует делегат, который определяет, какие элементы последовательности проходят через фильтр.</span><span class="sxs-lookup"><span data-stu-id="25586-111">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="25586-112">При создании запроса LINQ вы предоставляете реализацию делегата для этой цели.</span><span class="sxs-lookup"><span data-stu-id="25586-112">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="25586-113">Прототип метода Where имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="25586-113">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<in TSource> (IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="25586-114">Этот пример актуален для всех методов, которые относятся к LINQ.</span><span class="sxs-lookup"><span data-stu-id="25586-114">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="25586-115">Все они используют делегаты для управления определенными запросами.</span><span class="sxs-lookup"><span data-stu-id="25586-115">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="25586-116">Этот конструктивный шаблон API очень эффективен, что делает его важным для изучения и понимания.</span><span class="sxs-lookup"><span data-stu-id="25586-116">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="25586-117">Из этого примера видно, что делегаты почти не требуют взаимозависимости между компонентами.</span><span class="sxs-lookup"><span data-stu-id="25586-117">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="25586-118">Не нужно создавать класс, производный от некоторого базового класса.</span><span class="sxs-lookup"><span data-stu-id="25586-118">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="25586-119">Не нужно реализовывать определенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="25586-119">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="25586-120">Единственным требованием является предоставление реализации одного метода, на основе которого решается поставленная задача.</span><span class="sxs-lookup"><span data-stu-id="25586-120">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="25586-121">Создание собственных компонентов с помощью делегатов</span><span class="sxs-lookup"><span data-stu-id="25586-121">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="25586-122">Давайте продолжим пример, создав компонент с помощью модели, основанной на делегатах.</span><span class="sxs-lookup"><span data-stu-id="25586-122">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="25586-123">Определим компонент, который можно использовать для сообщений журнала в большой системе.</span><span class="sxs-lookup"><span data-stu-id="25586-123">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="25586-124">Компоненты библиотеки можно использовать во множестве разных сред на различных платформах.</span><span class="sxs-lookup"><span data-stu-id="25586-124">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="25586-125">В компонентах, управляющих журналами, много общих черт.</span><span class="sxs-lookup"><span data-stu-id="25586-125">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="25586-126">Они должны принимать сообщения от любого компонента системы.</span><span class="sxs-lookup"><span data-stu-id="25586-126">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="25586-127">Эти сообщения имеют разные приоритеты, которыми управляет основной компонент.</span><span class="sxs-lookup"><span data-stu-id="25586-127">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="25586-128">В окончательной архивной форме сообщений должны быть метки времени.</span><span class="sxs-lookup"><span data-stu-id="25586-128">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="25586-129">В более сложных сценариях может потребоваться фильтровать сообщения по исходному компоненту.</span><span class="sxs-lookup"><span data-stu-id="25586-129">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="25586-130">Часто будет меняться один аспект: куда записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="25586-130">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="25586-131">В некоторых средах они могут записываться в консоль ошибок.</span><span class="sxs-lookup"><span data-stu-id="25586-131">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="25586-132">В других — в файл.</span><span class="sxs-lookup"><span data-stu-id="25586-132">In others, a file.</span></span> <span data-ttu-id="25586-133">К иным вариантам относятся хранилище базы данных, журналы событий ОС или иные хранилища документов.</span><span class="sxs-lookup"><span data-stu-id="25586-133">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="25586-134">В некоторых ситуациях могут использоваться сочетания назначений вывода.</span><span class="sxs-lookup"><span data-stu-id="25586-134">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="25586-135">Например, сообщения могут записываться в консоль и в файл.</span><span class="sxs-lookup"><span data-stu-id="25586-135">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="25586-136">Модель на основе делегатов обеспечивает высокую гибкость и упрощает поддержку механизмов хранения, добавляемых в будущем.</span><span class="sxs-lookup"><span data-stu-id="25586-136">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="25586-137">В рамках этой модели основным компонентом журнала может быть невиртуальный и даже запечатанный класс.</span><span class="sxs-lookup"><span data-stu-id="25586-137">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="25586-138">Вы можете подключать любой набор делегатов для записи сообщений на различные носители данных.</span><span class="sxs-lookup"><span data-stu-id="25586-138">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="25586-139">Встроенная поддержка делегатов многоадресной рассылки позволяет легко реализовывать сценарии, в которых сообщения должны записываться в несколько расположений (в файл и консоль).</span><span class="sxs-lookup"><span data-stu-id="25586-139">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="25586-140">Первая реализация</span><span class="sxs-lookup"><span data-stu-id="25586-140">A First Implementation</span></span>

<span data-ttu-id="25586-141">Начнем с малого: начальная реализация будет принимать новые сообщения и записывать их с помощью любого подключенного делегата.</span><span class="sxs-lookup"><span data-stu-id="25586-141">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="25586-142">Можно начать с одного делегата, который записывает сообщения в консоль.</span><span class="sxs-lookup"><span data-stu-id="25586-142">You can start with one delegate that writes messages to the console.</span></span>

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(string msg)
    {
        WriteMessage(msg);
    }
}
```

<span data-ttu-id="25586-143">Приведенный выше статический класс содержит только самое необходимое для работы.</span><span class="sxs-lookup"><span data-stu-id="25586-143">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="25586-144">Нам нужно создать единственную реализацию метода, который записывает сообщения в консоль.</span><span class="sxs-lookup"><span data-stu-id="25586-144">We need to write the single implementation for the method that writes messages to the console:</span></span> 

```csharp
public static void LogToConsole(string message)
{
    Console.Error.WriteLine(message);
}
```

<span data-ttu-id="25586-145">Наконец, необходимо подключить делегат к делегату WriteMessage, объявленному в средстве ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-145">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

```csharp
Logger.WriteMessage += LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="25586-146">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="25586-146">Practices</span></span>

<span data-ttu-id="25586-147">Наш пример пока очень прост, но все же он демонстрирует некоторые важные моменты, касающиеся проектирования с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="25586-147">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="25586-148">Использование типов делегатов, определенных в Core Framework, упрощает пользователям работу с делегатами.</span><span class="sxs-lookup"><span data-stu-id="25586-148">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="25586-149">Вам не нужно определять новые типы, а разработчикам, использующим вашу библиотеку, не нужно изучать новые специальные типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="25586-149">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="25586-150">Применяются минимально необходимые, но при этом максимально гибкие интерфейсы: чтобы создать компонент для вывода данных журнала, необходимо написать всего один метод.</span><span class="sxs-lookup"><span data-stu-id="25586-150">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="25586-151">Это может быть статический метод или метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="25586-151">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="25586-152">Он может иметь любой уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="25586-152">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="25586-153">Форматирование выхода</span><span class="sxs-lookup"><span data-stu-id="25586-153">Formatting Output</span></span>

<span data-ttu-id="25586-154">Давайте немного улучшим первую версию, а затем приступим к созданию других механизмов ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-154">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="25586-155">Затем добавим в метод `LogMessage()` несколько аргументов, чтобы класс журнала создавал более структурированные сообщения.</span><span class="sxs-lookup"><span data-stu-id="25586-155">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

```csharp
// Logger implementation two
public enum Severity
{
    Verbose,
    Trace,
    Information,
    Warning,
    Error,
    Critical
}

public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```

<span data-ttu-id="25586-156">Далее используем аргумент `Severity` для фильтрации сообщений, отправляемых в место вывода журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-156">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static Severity LogLevel {get;set;} = Severity.Warning;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        if (s < LogLevel)
            return;
            
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```
## <a name="practices"></a><span data-ttu-id="25586-157">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="25586-157">Practices</span></span>

<span data-ttu-id="25586-158">Вы добавили новые функции в инфраструктуру ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="25586-158">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="25586-159">Так как компонент logger очень слабо связан с любым из механизмов вывода, эти функции можно добавлять без влияния на код, в котором реализуется делегат logger.</span><span class="sxs-lookup"><span data-stu-id="25586-159">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="25586-160">По мере расширения кода вы увидите дополнительные примеры того, как такая слабая взаимосвязь обеспечивает большую гибкость в плане обновления компонентов сайта без внесения изменений в другие его части.</span><span class="sxs-lookup"><span data-stu-id="25586-160">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="25586-161">На самом деле в более крупном приложении классы вывода данных журнала могут находиться в другой сборке и даже не требовать повторной сборки.</span><span class="sxs-lookup"><span data-stu-id="25586-161">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="25586-162">Создание второго модуля вывода</span><span class="sxs-lookup"><span data-stu-id="25586-162">Building a Second Output Engine</span></span>

<span data-ttu-id="25586-163">Работа над компонентом журнала продвигается.</span><span class="sxs-lookup"><span data-stu-id="25586-163">The Log component is coming along well.</span></span> <span data-ttu-id="25586-164">Давайте добавим еще один модуль вывода, который записывает сообщения в файл.</span><span class="sxs-lookup"><span data-stu-id="25586-164">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="25586-165">Для этого потребуется немного больше усилий.</span><span class="sxs-lookup"><span data-stu-id="25586-165">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="25586-166">Это будет класс, который инкапсулирует файловые операции и обеспечивает закрытие файла после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="25586-166">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="25586-167">Благодаря этому все данные будут окончательно записываться на диск после создания каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="25586-167">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="25586-168">Вот это средство ведения журнала на основе файла:</span><span class="sxs-lookup"><span data-stu-id="25586-168">Here is that file based logger:</span></span>

```csharp
public class FileLogger
{
    private readonly string logPath;
    public FileLogger(string path)
    {
        logPath = path;
        Logger.WriteMessage += LogMessage;
    }
    
    public void DetachLog() => Logger.WriteMessage -= LogMessage;

    // make sure this can't throw.
    private void LogMessage(string msg)
    {
        try {
            using (var log = File.AppendText(logPath))
            {
                log.WriteLine(msg);
                log.Flush();
            }
        } catch (Exception e)
        {
            // Hmm. Not sure what to do.
            // Logging is failing...
        }
    }
}
```

<span data-ttu-id="25586-169">После создания этого класса можно создать его экземпляр, и он подключит свой метод LogMessage к компоненту Logger:</span><span class="sxs-lookup"><span data-stu-id="25586-169">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

```csharp
var file = new FileLogger("log.txt");
```

<span data-ttu-id="25586-170">Эти два метода не являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="25586-170">These two are not mutually exclusive.</span></span> <span data-ttu-id="25586-171">Вы можете подключить оба метода ведения журнала, чтобы сообщения создавались как в консоли, так и в файле.</span><span class="sxs-lookup"><span data-stu-id="25586-171">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="25586-172">Позднее вы можете удалить один из делегатов даже в том же приложении без каких-либо проблем для системы.</span><span class="sxs-lookup"><span data-stu-id="25586-172">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="25586-173">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="25586-173">Practices</span></span>

<span data-ttu-id="25586-174">Итак, вы добавили второй обработчик вывода для подсистемы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-174">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="25586-175">Ему требуется немного больший объем инфраструктуры для правильной поддержки файловой системы.</span><span class="sxs-lookup"><span data-stu-id="25586-175">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="25586-176">Делегат представляет собой метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="25586-176">The delegate is an instance method.</span></span> <span data-ttu-id="25586-177">Кроме того, это закрытый метод.</span><span class="sxs-lookup"><span data-stu-id="25586-177">It's also a private method.</span></span>
<span data-ttu-id="25586-178">В более высоком уровне доступности нет необходимости, так как инфраструктура делегатов может подключать делегаты.</span><span class="sxs-lookup"><span data-stu-id="25586-178">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="25586-179">Во-вторых, модель на основе делегатов предоставляет несколько методов вывода без дополнительного кода.</span><span class="sxs-lookup"><span data-stu-id="25586-179">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="25586-180">Вам не нужно создавать дополнительную инфраструктуру для поддержки нескольких методов вывода.</span><span class="sxs-lookup"><span data-stu-id="25586-180">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="25586-181">Они просто добавляются в список вызова.</span><span class="sxs-lookup"><span data-stu-id="25586-181">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="25586-182">Обратите особое внимание на код в методе вывода данных журнала в файл.</span><span class="sxs-lookup"><span data-stu-id="25586-182">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="25586-183">Он написан так, что не создает никаких исключений.</span><span class="sxs-lookup"><span data-stu-id="25586-183">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="25586-184">Хотя это не является строго обязательным, зачастую это более удобно.</span><span class="sxs-lookup"><span data-stu-id="25586-184">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="25586-185">Если какой-либо из методов делегата создает исключение, остальные делегаты в списке вызова не будут вызваны.</span><span class="sxs-lookup"><span data-stu-id="25586-185">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="25586-186">Наконец, отметим, что компонент записи данных журнала в файл должен управлять своими ресурсами, открывая и закрывая файл для каждого сообщения журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-186">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="25586-187">Вы можете оставить файл открытым и реализовать интерфейс IDisposable для закрытия файла по завершении операции.</span><span class="sxs-lookup"><span data-stu-id="25586-187">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="25586-188">У каждого метода свои плюсы и минусы.</span><span class="sxs-lookup"><span data-stu-id="25586-188">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="25586-189">В обоих случаях несколько усиливается взаимозависимость между классами.</span><span class="sxs-lookup"><span data-stu-id="25586-189">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="25586-190">Для поддержки каждого из сценариев в код класса Logger не нужно вносить никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="25586-190">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="25586-191">Обработка пустых делегатов</span><span class="sxs-lookup"><span data-stu-id="25586-191">Handling Null Delegates</span></span>

<span data-ttu-id="25586-192">Наконец, давайте изменим метод LogMessage так, чтобы он был эффективен в случаях, когда механизм вывода не выбран.</span><span class="sxs-lookup"><span data-stu-id="25586-192">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="25586-193">Текущая реализация вызывает исключение `NullReferenceException`, когда к делегату `WriteMessage` не подключен список вызова.</span><span class="sxs-lookup"><span data-stu-id="25586-193">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="25586-194">Однако предпочтительнее может быть автоматическое продолжение выполнения в случае, если методы не подключены.</span><span class="sxs-lookup"><span data-stu-id="25586-194">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="25586-195">Такое поведение легко реализовать с помощью условного оператора null в сочетании с методом `Delegate.Invoke()`.</span><span class="sxs-lookup"><span data-stu-id="25586-195">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="25586-196">Условный оператор null (`?.`) замыкается, если левый операнд (в данном случае `WriteMessage`) имеет значение null, что означает, что попытки записать сообщение не предпринимаются.</span><span class="sxs-lookup"><span data-stu-id="25586-196">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="25586-197">Метод `Invoke()` не указан в документации по `System.Delegate` или `System.MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="25586-197">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="25586-198">Компилятор создает типобезопасный метод `Invoke` для любого объявленного типа делегата.</span><span class="sxs-lookup"><span data-stu-id="25586-198">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="25586-199">В этом примере это означает, что метод `Invoke` принимает один аргумент `string` и имеет тип возвращаемого значения void.</span><span class="sxs-lookup"><span data-stu-id="25586-199">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="25586-200">Сводка рекомендаций</span><span class="sxs-lookup"><span data-stu-id="25586-200">Summary of Practices</span></span>

<span data-ttu-id="25586-201">Вы ознакомились с простейшим компонентом журнала, который можно расширять с помощью других модулей записи и иных функций.</span><span class="sxs-lookup"><span data-stu-id="25586-201">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="25586-202">Благодаря использованию делегатов при проектировании эти компоненты оказываются слабо взаимосвязанными.</span><span class="sxs-lookup"><span data-stu-id="25586-202">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="25586-203">Преимуществ несколько.</span><span class="sxs-lookup"><span data-stu-id="25586-203">This provides several advantages.</span></span> <span data-ttu-id="25586-204">Очень легко создавать новые механизмы вывода и подключать их к системе.</span><span class="sxs-lookup"><span data-stu-id="25586-204">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="25586-205">Этим механизмам требуется только один метод, который записывает сообщение журнала.</span><span class="sxs-lookup"><span data-stu-id="25586-205">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="25586-206">Такая модель очень устойчива при добавлении новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="25586-206">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="25586-207">Обязательным требованием для каждого модуля записи является реализация одного метода.</span><span class="sxs-lookup"><span data-stu-id="25586-207">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="25586-208">Это может быть статический метод или метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="25586-208">That method could be a static or instance method.</span></span> <span data-ttu-id="25586-209">Он может быть открытым, закрытым или иметь любой иной допустимый уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="25586-209">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="25586-210">В класс Logger можно вносить любое количество улучшений и изменений без серьезной модификации.</span><span class="sxs-lookup"><span data-stu-id="25586-210">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="25586-211">Открытый интерфейс API, как и любой другой класс, нельзя модифицировать без риска внесения существенных изменений.</span><span class="sxs-lookup"><span data-stu-id="25586-211">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="25586-212">Но так как взаимосвязь между средством ведения журнала и модулями вывода осуществляется только посредством делегата, другие типы (например, интерфейсы или базовые классы) не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="25586-212">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="25586-213">Взаимосвязь минимальна.</span><span class="sxs-lookup"><span data-stu-id="25586-213">The coupling is as small as possible.</span></span>

[<span data-ttu-id="25586-214">Далее</span><span class="sxs-lookup"><span data-stu-id="25586-214">Next</span></span>](events-overview.md)

