---
title: Консольное приложение
description: Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: dba6125dd359a47115b0f363a081dc000ce29e6a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="console-application"></a><span data-ttu-id="fd8ec-104">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="fd8ec-104">Console Application</span></span>

<span data-ttu-id="fd8ec-105">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="fd8ec-106">Вы познакомитесь со следующими аспектами:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-106">You’ll learn:</span></span>

- <span data-ttu-id="fd8ec-107">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="fd8ec-107">The basics of the .NET Core Command Line Interface (CLI)</span></span>
- <span data-ttu-id="fd8ec-108">структура консольного приложения C#;</span><span class="sxs-lookup"><span data-stu-id="fd8ec-108">The structure of a C# Console Application</span></span>
- <span data-ttu-id="fd8ec-109">консольный ввод-вывод;</span><span class="sxs-lookup"><span data-stu-id="fd8ec-109">Console I/O</span></span>
- <span data-ttu-id="fd8ec-110">основные сведения об интерфейсах API файлового ввода-вывода в .NET;</span><span class="sxs-lookup"><span data-stu-id="fd8ec-110">The basics of File I/O APIs in .NET</span></span>
- <span data-ttu-id="fd8ec-111">основные сведениях об асинхронном программировании задач в .NET.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-111">The basics of the Task-based Asynchronous Programming in .NET</span></span>

<span data-ttu-id="fd8ec-112">Вам предстоит создать приложение, которое считывает текстовый файл и выводит его содержимое в консоль.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-112">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="fd8ec-113">Вывод в консоль осуществляется с такой скоростью, которая позволяет читать текст вслух.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-113">The output to the console is paced to match reading it aloud.</span></span> <span data-ttu-id="fd8ec-114">Скорость можно будет увеличивать или уменьшать клавишами "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="fd8ec-114">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="fd8ec-115">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-115">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="fd8ec-116">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-116">Let’s build them one by one.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd8ec-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fd8ec-117">Prerequisites</span></span>

<span data-ttu-id="fd8ec-118">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-118">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="fd8ec-119">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-119">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="fd8ec-120">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-120">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="fd8ec-121">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-121">You’ll need to install your favorite code editor.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="fd8ec-122">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="fd8ec-122">Create the Application</span></span>

<span data-ttu-id="fd8ec-123">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-123">The first step is to create a new application.</span></span> <span data-ttu-id="fd8ec-124">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-124">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="fd8ec-125">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-125">Make that the current directory.</span></span> <span data-ttu-id="fd8ec-126">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-126">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="fd8ec-127">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-127">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="fd8ec-128">Прежде чем вносить изменения в это приложение, давайте разберем процедуру его запуска.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-128">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="fd8ec-129">Когда вы создадите приложение, наберите в командной строке команду `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-129">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="fd8ec-130">Она запускает процесс восстановления из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-130">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="fd8ec-131">NuGet представляет собой диспетчер пакетов для .NET.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-131">NuGet is a .NET package manager.</span></span> <span data-ttu-id="fd8ec-132">Эта команда загружает все отсутствующие зависимости для проекта.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-132">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="fd8ec-133">Поскольку мы имеем дело с новым проектом, для него пока не существует зависимостей, поэтому при первом запуске будет загружена только платформа .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-133">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="fd8ec-134">После этого первого запуска команду `dotnet restore` нужно будет запускать только после добавления новых зависимых пакетов или при обновлении версий используемых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-134">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="fd8ec-135">Когда завершится восстановление пакетов, запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-135">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="fd8ec-136">Эта команда запускает подсистему сборки и создает исполняемый файл приложения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-136">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="fd8ec-137">Теперь можно выполнить команду `dotnet run`, которая запустит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-137">Finally, you execute `dotnet run` to run your application.</span></span>

<span data-ttu-id="fd8ec-138">Весь код простого приложения Hello World размещается в файле Program.cs.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-138">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="fd8ec-139">Откройте этот файл в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-139">Open that file with your favorite text editor.</span></span> <span data-ttu-id="fd8ec-140">Сейчас мы внесем в него первые изменения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-140">We’re about to make our first changes.</span></span>
<span data-ttu-id="fd8ec-141">В верхней части файла вы видите инструкцию using:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-141">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="fd8ec-142">Эта инструкция указывает компилятору, что в области действия находятся все типы из пространства имен `System`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-142">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="fd8ec-143">Как и другие объектно ориентированные языки, с которыми вы могли работать ранее, C# использует пространства имен для организации типов.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-143">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="fd8ec-144">В нашей программе Hello World все точно так же.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-144">This Hello World program is no different.</span></span> <span data-ttu-id="fd8ec-145">Как вы видите, программа заключена в пространство имен, имя которого соответствует имени текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-145">You can see that the program is enclosed in the namespace with the name based on the name of the current directory.</span></span> <span data-ttu-id="fd8ec-146">В этом учебнике давайте изменим имя на `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-146">For this tutorial, let's change the name of the namespace to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="fd8ec-147">Чтение и вывод файла</span><span class="sxs-lookup"><span data-stu-id="fd8ec-147">Reading and Echoing the File</span></span>

<span data-ttu-id="fd8ec-148">Первая функция, которую мы добавим, будет считывать данные из текстового файла и выводить полученный текст в консоль.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-148">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="fd8ec-149">Сначала нам нужно добавить текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-149">First, let’s add a text file.</span></span> <span data-ttu-id="fd8ec-150">Скопируйте в каталог проекта файл [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) из репозитория GitHub для этого [примера](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-150">Copy the [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="fd8ec-151">Он будет источником текста для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-151">This will serve as the script for your application.</span></span> <span data-ttu-id="fd8ec-152">Чтобы скачать пример приложения для этого раздела, воспользуйтесь инструкциями в разделе [Примеры и руководства](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-152">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="fd8ec-153">Теперь добавьте в класс `Program` (он расположен сразу за методом `Main`) следующий метод:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-153">Next, add the following method in your `Program` class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="fd8ec-154">Этот метод использует типы из двух новых пространств имен.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-154">This method uses types from two new namespaces.</span></span> <span data-ttu-id="fd8ec-155">Чтобы такая программа успешно скомпилировалась, нужно добавить в начало файла следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-155">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="fd8ec-156">Интерфейс <xref:System.Collections.Generic.IEnumerable%601> определен в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-156">The <xref:System.Collections.Generic.IEnumerable%601> interface is defined in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="fd8ec-157">Класс <xref:System.IO.File> определен в пространстве имен <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-157">The <xref:System.IO.File> class is defined in the <xref:System.IO> namespace.</span></span>

<span data-ttu-id="fd8ec-158">Этот метод является специальным типом *метода перечислителя* C#.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-158">This method is a special type of C# method called an *Iterator method*.</span></span> <span data-ttu-id="fd8ec-159">Метод перечислителя возвращает последовательности, для которых применяется отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-159">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="fd8ec-160">Это означает, что каждый элемент в последовательности создается только в тот момент, когда к нему выполняется обращение в коде обработки последовательности.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-160">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="fd8ec-161">Методы перечислителя содержат один или несколько операторов [`yield return`](../language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-161">Enumerator methods are methods that contain one or more [`yield return`](../language-reference/keywords/yield.md) statements.</span></span> <span data-ttu-id="fd8ec-162">Возвращаемый методом `ReadFrom` объект содержит код для создания каждого элемента последовательности.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-162">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="fd8ec-163">В нашем примере он читает следующую строку текста из исходного файла и возвращает эту строку.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-163">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="fd8ec-164">Каждый раз, когда вызывающий код запрашивает следующий элемент из последовательности, код считывает из файла и возвращает следующую строку текста.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-164">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="fd8ec-165">Когда файл закончится, последовательность сообщает, что в ней больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-165">When the file is completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="fd8ec-166">Здесь используются еще два элемента синтаксиса C#, которые могут быть для вас новыми.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-166">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="fd8ec-167">Оператор [`using`](../language-reference/keywords/using-statement.md) в этом методе управляет освобождением ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-167">The [`using`](../language-reference/keywords/using-statement.md) statement in this method manages resource cleanup.</span></span> <span data-ttu-id="fd8ec-168">Переменная, которая инициализируется в инструкции `using` (в нашем примере это `reader`) должна реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-168">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="fd8ec-169">Этот интерфейс определяет единственный метод (`Dispose`), который вызывается для освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-169">That interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="fd8ec-170">Компилятор создает такой вызов, когда выполнение кода достигает закрывающей скобки инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-170">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="fd8ec-171">Созданный компилятором код гарантирует освобождение ресурса даже в том случае, если в блоке кода, определенном инструкцией using, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-171">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="fd8ec-172">Переменная `reader` определена с ключевым словом `var`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-172">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="fd8ec-173">Ключевое слово [`var`](../language-reference/keywords/var.md) определяет *неявно типизированную локальную переменную*.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-173">[`var`](../language-reference/keywords/var.md) defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="fd8ec-174">Это означает, что тип переменной определяется во время компиляции по типу объекта, присвоенного этой переменной.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-174">That means the type of the variable is determined by the compile-time type of the object assigned to the variable.</span></span> <span data-ttu-id="fd8ec-175">Здесь это возвращаемое значение метода <xref:System.IO.File.OpenText(System.String)>, то есть объект <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-175">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>

<span data-ttu-id="fd8ec-176">Теперь давайте создадим в методе `Main` код для чтения файла:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-176">Now, let’s fill in the code to read the file in the `Main` method:</span></span>

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

<span data-ttu-id="fd8ec-177">Запустите программу командой `dotnet run` и убедитесь в том, что все текстовые строки выводятся в консоль.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-177">Run the program (using `dotnet run`) and you can see every line printed out to the console.</span></span>

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="fd8ec-178">Добавление задержек и форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="fd8ec-178">Adding Delays and Formatting output</span></span>

<span data-ttu-id="fd8ec-179">Сейчас данные отображаются слишком быстро для чтения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-179">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="fd8ec-180">Поэтому нам нужно добавить задержку в процесс вывода.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-180">Now you need to add the delays in the output.</span></span> <span data-ttu-id="fd8ec-181">Для этого вы создадите несложный код, выполняющий асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-181">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="fd8ec-182">Но первые наши действия будут нарушать стандартные рекомендации.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-182">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="fd8ec-183">Эти нарушения мы укажем в комментариях при создании кода, а затем заменим этот код в последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-183">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="fd8ec-184">В этом разделе описаны два действия.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-184">There are two steps to this section.</span></span> <span data-ttu-id="fd8ec-185">Во-первых, обновите метод итератора, чтобы он возвращал не всю строку целиком, а каждое слово отдельно.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-185">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="fd8ec-186">Для этого внесите такие изменения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-186">That’s done with these modifications.</span></span> <span data-ttu-id="fd8ec-187">Замените инструкцию `yield return line;` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-187">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="fd8ec-188">Теперь следует изменить код обработки строк файла, добавив задержку после вывода каждого слова.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-188">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="fd8ec-189">Замените инструкцию `Console.WriteLine(line)` в методе `Main` на такой блок кода:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-189">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="fd8ec-190">Класс <xref:System.Threading.Tasks.Task> находится в пространства имен <xref:System.Threading.Tasks>, поэтому эту инструкцию `using` нужно добавить в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-190">The <xref:System.Threading.Tasks.Task> class is in the <xref:System.Threading.Tasks> namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="fd8ec-191">Запустите пример и проверьте выходные данные.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-191">Run the sample, and check the output.</span></span> <span data-ttu-id="fd8ec-192">Теперь слова появляются по одному и с задержками по 200 мс.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-192">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="fd8ec-193">Но пока с выводом сохраняются некоторые проблемы, поскольку в исходном текстовом файле есть несколько строк длиной более 80 символов, и они выводятся без перевода строки.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-193">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="fd8ec-194">Это не очень удобно читать с прокруткой.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-194">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="fd8ec-195">Но эту проблему легко исправить.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-195">That’s easy to fix.</span></span> <span data-ttu-id="fd8ec-196">Вам нужно лишь отслеживать длину каждой строки и создавать перевод строки каждый раз, когда эта длина достигает определенного порога.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-196">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="fd8ec-197">После объявления `words` в методе `ReadFrom` объявите локальную переменную для хранения длины строки:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-197">Declare a local variable after the declaration of `words` in the `ReadFrom` method that holds the line length:</span></span>

```csharp
var lineLength = 0;
```

<span data-ttu-id="fd8ec-198">Теперь добавьте следующий код после инструкции `yield return word + " ";` (перед закрывающей фигурной скобкой):</span><span class="sxs-lookup"><span data-stu-id="fd8ec-198">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

<span data-ttu-id="fd8ec-199">Запустите пример, и теперь вы сможете читать текст вслух в заданном темпе.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-199">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="fd8ec-200">Асинхронные задачи</span><span class="sxs-lookup"><span data-stu-id="fd8ec-200">Async Tasks</span></span>

<span data-ttu-id="fd8ec-201">И на последнем этапе мы добавим код, который будет выполнять две асинхронные задачи, одна из которых осуществляет вывод текста, а вторая ожидает ввод от пользователя для ускорения или замедления вывода текста.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-201">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="fd8ec-202">Этот этап разделяется на несколько шагов, по завершении которых вы получите все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-202">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="fd8ec-203">Первым шагом является создание асинхронной задачи (<xref:System.Threading.Tasks.Task>), которая возвращает метод с тем кодом, который вы создали ранее для чтения и отображения файла.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-203">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="fd8ec-204">Добавьте следующий метод в класс `Program`. Этот текст основан на тексте метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-204">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="fd8ec-205">Но вы можете заметить два изменения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-205">You’ll notice two changes.</span></span> <span data-ttu-id="fd8ec-206">Во-первых, в тексте нет вызова <xref:System.Threading.Tasks.Task.Wait>, который в синхронном режиме ожидает завершения задачи. Вместо него в этой версии используется ключевое слово `await`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-206">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="fd8ec-207">Чтобы это работало, в сигнатуру метода нужно добавить модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-207">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="fd8ec-208">Этот метод возвращает `Task`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-208">This method returns a `Task`.</span></span> <span data-ttu-id="fd8ec-209">Обратите внимание, что здесь нет инструкции для возвращения объекта `Task`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-209">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="fd8ec-210">Вместо этого объект `Task` создается в коде, который компилятор предоставляет в точке использования оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-210">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="fd8ec-211">Представьте, что метод завершает выполнение при достижении `await`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-211">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="fd8ec-212">Он возвращает `Task` в знак того, что работа еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-212">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="fd8ec-213">Метод возобновит свою работу, когда завершится ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-213">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="fd8ec-214">Когда работа метода завершится, это будет отражено в возвращаемом объекте `Task`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-214">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="fd8ec-215">Вызывающий код может отслеживать состояние полученного `Task`, чтобы определить момент завершения метода.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-215">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="fd8ec-216">Теперь наш новый метод можно вызвать из метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-216">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="fd8ec-217">Здесь, в методе `Main`, код синхронно ожидает завершения.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-217">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="fd8ec-218">Всегда, когда это возможно, следует использовать оператор `await` вместо синхронного ожидания.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-218">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="fd8ec-219">Но в методе `Main` консольного приложения запрещено использовать оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-219">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="fd8ec-220">В противном случае приложение завершит работу раньше, чем выполнит все свои задачи.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-220">That would result in the application exiting before all tasks have completed.</span></span>

> [!NOTE]
> <span data-ttu-id="fd8ec-221">При использовании C# 7.1 или более поздней версии консольные приложения можно создавать с помощью [метода `async` `Main`](../whats-new/csharp-7-1.md#async-main).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-221">If you use C# 7.1 or later, you can create console applications with [`async` `Main` method](../whats-new/csharp-7-1.md#async-main).</span></span>

<span data-ttu-id="fd8ec-222">Теперь следует создать второй асинхронный метод, который будет читать ввод из консоли и реагировать на клавиши "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="fd8ec-222">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="fd8ec-223">Для выполнения этой задачи добавьте такой метод:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-223">Here’s the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="fd8ec-224">Здесь создается лямбда-выражение, представляющее делегат <xref:System.Action>, который считывает нажатие клавиши из консоли и изменяет локальную переменную с длительностью задержки в том случае, если пользователь нажал клавишу "<" или ">".</span><span class="sxs-lookup"><span data-stu-id="fd8ec-224">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="fd8ec-225">Этот метод использует метод <xref:System.Console.ReadKey>, чтобы блокировать выполнение и ожидать нажатия клавиши.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-225">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="fd8ec-226">Чтобы завершить создание этой функции, нам нужна новая инструкция `async Task`, которая вернет метод, запускающий обе задачи (`GetInput` и `ShowTeleprompter`) и управляющий обменом данными между этими задачами.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-226">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>

<span data-ttu-id="fd8ec-227">Пришло время создать класс, который может обрабатывать совместное использование данных двумя задачами.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-227">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="fd8ec-228">Этот класс содержит два открытых свойства: delay (задержка) и флаг `Done`, который означает, что файл прочитан полностью:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-228">This class contains two public properties: the delay, and a flag `Done` to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

<span data-ttu-id="fd8ec-229">Поместите этот класс в отдельный новый файл и заключите в пространство имен `TeleprompterConsole`, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-229">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="fd8ec-230">Также следует добавить оператор `using static`, чтобы можно было ссылаться на методы `Min` и `Max` без указания имени внешнего класса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-230">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` methods without the enclosing class or namespace names.</span></span> <span data-ttu-id="fd8ec-231">Оператор [`using static`](../language-reference/keywords/using-static.md) импортирует методы из одного класса.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-231">A [`using static`](../language-reference/keywords/using-static.md) statement imports the methods from one class.</span></span> <span data-ttu-id="fd8ec-232">В этом она отличается от использованной ранее инструкции `using`, которая импортирует все классы из пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-232">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="fd8ec-233">Еще одна новая для вас функция языка — это оператор [`lock`](../language-reference/keywords/lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-233">The other language feature that’s new is the [`lock`](../language-reference/keywords/lock-statement.md) statement.</span></span> <span data-ttu-id="fd8ec-234">Она гарантирует, что в этом коде в любой момент может выполняться только один поток.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-234">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="fd8ec-235">Если любой из потоков выполняет заблокированный раздел, все остальные потоки должны ожидать, пока он не выйдет из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-235">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="fd8ec-236">Инструкция `lock` использует объект, который защищает заблокированный раздел.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-236">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="fd8ec-237">Этот класс соответствует стандартному принципу блокировки частного объекта в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-237">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="fd8ec-238">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput` для использования нового объекта `config`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-238">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="fd8ec-239">И еще одна инструкция `Task`, которая возвращает метод `async`, запускающий обе задачи и завершающий работу после окончания первой задачи:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-239">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="fd8ec-240">Новым методом здесь является <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-240">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="fd8ec-241">Этот метод создает задачу (`Task`), которая завершается сразу, как только завершится любая из задач в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-241">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="fd8ec-242">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput`, чтобы они использовали объект `config` для задержки:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-242">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="fd8ec-243">Новая версия метода `ShowTeleprompter` вызывает новый метод из класса `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-243">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="fd8ec-244">Сейчас нужно изменить метод `Main`, чтобы вместо `ShowTeleprompter` он вызывал `RunTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="fd8ec-244">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a><span data-ttu-id="fd8ec-245">Заключение</span><span class="sxs-lookup"><span data-stu-id="fd8ec-245">Conclusion</span></span>

<span data-ttu-id="fd8ec-246">В этом учебнике мы продемонстрировали вам ряд функций языка C# и библиотек .NET Core, связанных с работой в консольных приложениях.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-246">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="fd8ec-247">На основе полученных знаний вы сможете развивать свои представления о языке и представленных здесь классах.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-247">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="fd8ec-248">Вы увидели базовые примеры использования файлового и консольного ввода-вывода, асинхронного программирования на основе задач с блокировкой и без блокировки. Вы получили информацию о языке C#, структуре программ на C#, а также об интерфейсе командной строки и средствах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd8ec-248">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task-based asynchronous programming, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>

<span data-ttu-id="fd8ec-249">Дополнительные сведения о файловом вводе-выводе см. в статье [Файловый и потоковый ввод-вывод](../../standard/io/index.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-249">For more information about File I/O, see the [File and Stream I/O](../../standard/io/index.md) topic.</span></span> <span data-ttu-id="fd8ec-250">Дополнительные сведения о модели асинхронного программирования, используемой в учебнике, см. в статьях [Асинхронное программирование на основе задач](../..//standard/parallel-programming/task-based-asynchronous-programming.md) и [Асинхронное программирование](../async.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ec-250">For more information about asynchronous programming model used in this tutorial, see the [Task-based Asynchronous Programming](../..//standard/parallel-programming/task-based-asynchronous-programming.md) topic and the [Asynchronous programming](../async.md) topic.</span></span>
