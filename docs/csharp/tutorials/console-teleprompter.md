---
title: "Консольное приложение"
description: "Это руководство раскроет для вас некоторые возможности .NET Core и языка C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.translationtype: Human Translation
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 360e93af03e00547116d1af1816c2b9b29524881
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="console-application"></a><span data-ttu-id="931ab-104">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="931ab-104">Console Application</span></span>

## <a name="introduction"></a><span data-ttu-id="931ab-105">Вступление</span><span class="sxs-lookup"><span data-stu-id="931ab-105">Introduction</span></span>
<span data-ttu-id="931ab-106">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="931ab-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="931ab-107">Вы познакомитесь со следующими аспектами:</span><span class="sxs-lookup"><span data-stu-id="931ab-107">You’ll learn:</span></span>
*   <span data-ttu-id="931ab-108">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="931ab-108">The basics of the .NET Core Command Line Interface (CLI)</span></span>
*   <span data-ttu-id="931ab-109">структура консольного приложения C#;</span><span class="sxs-lookup"><span data-stu-id="931ab-109">The structure of a C# Console Application</span></span>
*   <span data-ttu-id="931ab-110">консольный ввод-вывод;</span><span class="sxs-lookup"><span data-stu-id="931ab-110">Console I/O</span></span>
*   <span data-ttu-id="931ab-111">основные сведения об интерфейсах API файлового ввода-вывода в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="931ab-111">The basics of File I/O APIs in .NET Core</span></span>
*   <span data-ttu-id="931ab-112">основные сведениях о модели асинхронного программирования задач в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="931ab-112">The basics of the Task Asynchronous Programming Model in .NET Core</span></span>

<span data-ttu-id="931ab-113">Вам предстоит создать приложение, которое считывает текстовый файл и выводит его содержимое в консоль.</span><span class="sxs-lookup"><span data-stu-id="931ab-113">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="931ab-114">Вывод в консоль будет осуществляться с такой скоростью, которая позволяет читать текст вслух.</span><span class="sxs-lookup"><span data-stu-id="931ab-114">The output to the console will be paced to match reading it aloud.</span></span> <span data-ttu-id="931ab-115">Скорость можно будет увеличивать или уменьшать клавишами "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="931ab-115">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="931ab-116">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="931ab-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="931ab-117">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="931ab-117">Let’s build them one by one.</span></span> 
## <a name="prerequisites"></a><span data-ttu-id="931ab-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="931ab-118">Prerequisites</span></span>
<span data-ttu-id="931ab-119">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="931ab-119">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="931ab-120">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="931ab-120">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="931ab-121">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="931ab-121">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="931ab-122">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="931ab-122">You’ll need to install your favorite code editor.</span></span> 
## <a name="create-the-application"></a><span data-ttu-id="931ab-123">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="931ab-123">Create the Application</span></span>
<span data-ttu-id="931ab-124">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="931ab-124">The first step is to create a new application.</span></span> <span data-ttu-id="931ab-125">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="931ab-125">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="931ab-126">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="931ab-126">Make that the current directory.</span></span> <span data-ttu-id="931ab-127">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="931ab-127">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="931ab-128">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="931ab-128">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="931ab-129">Прежде чем вносить изменения в это приложение, давайте разберем процедуру его запуска.</span><span class="sxs-lookup"><span data-stu-id="931ab-129">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="931ab-130">Когда вы создадите приложение, наберите в командной строке команду `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="931ab-130">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="931ab-131">Она запускает процесс восстановления из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="931ab-131">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="931ab-132">NuGet представляет собой диспетчер пакетов для .NET.</span><span class="sxs-lookup"><span data-stu-id="931ab-132">NuGet is a .NET package manager.</span></span> <span data-ttu-id="931ab-133">Эта команда загружает все отсутствующие зависимости для проекта.</span><span class="sxs-lookup"><span data-stu-id="931ab-133">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="931ab-134">Поскольку мы имеем дело с новым проектом, для него пока не существует зависимостей, поэтому при первом запуске будет загружена только платформа .NET Core.</span><span class="sxs-lookup"><span data-stu-id="931ab-134">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="931ab-135">После этого первого запуска команду `dotnet restore` нужно будет запускать только после добавления новых зависимых пакетов или при обновлении версий используемых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="931ab-135">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span> <span data-ttu-id="931ab-136">Этот процесс также создает файл блокировки проекта (project.lock.json) в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="931ab-136">This process also creates the project lock file (project.lock.json) in your project directory.</span></span> <span data-ttu-id="931ab-137">Этот файл помогает управлять зависимостями проекта.</span><span class="sxs-lookup"><span data-stu-id="931ab-137">This file helps to manage the project dependencies.</span></span> <span data-ttu-id="931ab-138">Он указывает локальное расположение всех зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="931ab-138">It contains the local location of all the project dependencies.</span></span> <span data-ttu-id="931ab-139">Этот файл не обязательно помещать в систему управления версиями. Он будет автоматически создан при выполнении команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="931ab-139">You do not need to put the file in source control; it will be generated when you run `dotnet restore`.</span></span> 

<span data-ttu-id="931ab-140">Когда завершится восстановление пакетов, запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="931ab-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="931ab-141">Эта команда запускает подсистему сборки и создает исполняемый файл приложения.</span><span class="sxs-lookup"><span data-stu-id="931ab-141">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="931ab-142">Теперь можно выполнить команду `dotnet run`, которая запустит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="931ab-142">Finally, you execute `dotnet run` to run your application.</span></span>  

<span data-ttu-id="931ab-143">Весь код простого приложения Hello World размещается в файле Program.cs.</span><span class="sxs-lookup"><span data-stu-id="931ab-143">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="931ab-144">Откройте этот файл в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="931ab-144">Open that file with your favorite text editor.</span></span> <span data-ttu-id="931ab-145">Сейчас мы внесем в него первые изменения.</span><span class="sxs-lookup"><span data-stu-id="931ab-145">We’re about to make our first changes.</span></span>
<span data-ttu-id="931ab-146">В верхней части файла вы видите инструкцию using:</span><span class="sxs-lookup"><span data-stu-id="931ab-146">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="931ab-147">Эта инструкция указывает компилятору, что в области действия находятся все типы из пространства имен `System`.</span><span class="sxs-lookup"><span data-stu-id="931ab-147">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="931ab-148">Как и другие объектно ориентированные языки, с которыми вы могли работать ранее, C# использует пространства имен для организации типов.</span><span class="sxs-lookup"><span data-stu-id="931ab-148">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="931ab-149">В нашей программе Hello World все точно так же.</span><span class="sxs-lookup"><span data-stu-id="931ab-149">This hello world program is no different.</span></span> <span data-ttu-id="931ab-150">Как вы видите, программа заключена в пространство имен `ConsoleApplication`.</span><span class="sxs-lookup"><span data-stu-id="931ab-150">You can see that the program is enclosed in the `ConsoleApplication` namespace.</span></span> <span data-ttu-id="931ab-151">Это не очень понятное имя, давайте изменим его на `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="931ab-151">That’s not a very descriptive name, so change it to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="931ab-152">Чтение и вывод файла</span><span class="sxs-lookup"><span data-stu-id="931ab-152">Reading and Echoing the File</span></span>
<span data-ttu-id="931ab-153">Первая функция, которую мы добавим, будет считывать данные из текстового файла и выводить полученный текст в консоль.</span><span class="sxs-lookup"><span data-stu-id="931ab-153">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="931ab-154">Сначала нам нужно добавить текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="931ab-154">First, let’s add a text file.</span></span> <span data-ttu-id="931ab-155">Скопируйте в каталог проекта файл [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) из репозитория GitHub для этого [примера](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter).</span><span class="sxs-lookup"><span data-stu-id="931ab-155">Copy the [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="931ab-156">Он будет источником текста для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="931ab-156">This will serve as the script for your application.</span></span> <span data-ttu-id="931ab-157">Чтобы скачать пример приложения для этого раздела, воспользуйтесь инструкциями в разделе [Примеры и руководства](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="931ab-157">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="931ab-158">Теперь добавьте в класс Program (он расположен сразу за методом `Main`) следующий метод:</span><span class="sxs-lookup"><span data-stu-id="931ab-158">Next, add the following method in your Program class (right below the `Main` method):</span></span>

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

<span data-ttu-id="931ab-159">Этот метод использует типы из двух новых пространств имен.</span><span class="sxs-lookup"><span data-stu-id="931ab-159">This method uses types from two new namespaces.</span></span> <span data-ttu-id="931ab-160">Чтобы такая программа успешно скомпилировалась, нужно добавить в начало файла следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="931ab-160">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="931ab-161">Интерфейс `IEnumerable<T>` определен в пространстве имен `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="931ab-161">The `IEnumerable<T>` interface is defined in the `System.Collections.Generic` namespace.</span></span> <span data-ttu-id="931ab-162">Класс @System.IO.File определен в пространстве имен `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="931ab-162">The @System.IO.File class is defined in the `System.IO` namespace.</span></span>

<span data-ttu-id="931ab-163">Этот метод является специализированным подтипом стандартного *метода перечислителя* C#.</span><span class="sxs-lookup"><span data-stu-id="931ab-163">This method is a special type of C# method called an *Enumerator method*.</span></span> <span data-ttu-id="931ab-164">Метод перечислителя возвращает последовательности, для которых применяется отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="931ab-164">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="931ab-165">Это означает, что каждый элемент в последовательности создается только в тот момент, когда к нему выполняется обращение в коде обработки последовательности.</span><span class="sxs-lookup"><span data-stu-id="931ab-165">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="931ab-166">Методы перечислителя содержат одну или несколько инструкций `yield return`.</span><span class="sxs-lookup"><span data-stu-id="931ab-166">Enumerator methods are methods that contain one or more `yield return` statements.</span></span> <span data-ttu-id="931ab-167">Возвращаемый методом `ReadFrom` объект содержит код для создания каждого элемента последовательности.</span><span class="sxs-lookup"><span data-stu-id="931ab-167">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="931ab-168">В нашем примере он читает следующую строку текста из исходного файла и возвращает эту строку.</span><span class="sxs-lookup"><span data-stu-id="931ab-168">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="931ab-169">Каждый раз, когда вызывающий код запрашивает следующий элемент из последовательности, код считывает из файла и возвращает следующую строку текста.</span><span class="sxs-lookup"><span data-stu-id="931ab-169">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="931ab-170">Когда файл закончится, последовательность сообщает, что в ней больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="931ab-170">When the file has been completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="931ab-171">Здесь используются еще два элемента синтаксиса C#, которые могут быть для вас новыми.</span><span class="sxs-lookup"><span data-stu-id="931ab-171">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="931ab-172">Инструкция `using` в этом методе управляет освобождением ресурсов.</span><span class="sxs-lookup"><span data-stu-id="931ab-172">The `using` statement in this method manages resource cleanup.</span></span> <span data-ttu-id="931ab-173">Переменная, которая инициализируется в инструкции `using` (в нашем примере это `reader`) должна реализовывать интерфейс `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="931ab-173">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the `IDisposable` interface.</span></span> <span data-ttu-id="931ab-174">Интерфейс @System.IDisposable определяет единственный метод (`Dispose`), который вызывается для освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="931ab-174">The @System.IDisposable interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="931ab-175">Компилятор создает такой вызов, когда выполнение кода достигает закрывающей скобки инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="931ab-175">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="931ab-176">Созданный компилятором код гарантирует освобождение ресурса даже в том случае, если в блоке кода, определенном инструкцией using, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="931ab-176">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="931ab-177">Переменная `reader` определена с ключевым словом `var`.</span><span class="sxs-lookup"><span data-stu-id="931ab-177">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="931ab-178">Ключевое слово `var` определяет *неявно типизированную локальную переменную*.</span><span class="sxs-lookup"><span data-stu-id="931ab-178">`var` defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="931ab-179">Это означает, что тип переменной определяется во время компиляции по типу объекта, присвоенного этой переменной.</span><span class="sxs-lookup"><span data-stu-id="931ab-179">That means the type of the variable is determined by the compile time type of the object assigned to the variable.</span></span> <span data-ttu-id="931ab-180">Здесь в переменной сохраняется объект @System.IO.StreamReader, возвращаемый методом @System.IO.File.OpenText.</span><span class="sxs-lookup"><span data-stu-id="931ab-180">Here, that is the return value from @System.IO.File.OpenText, which is a @System.IO.StreamReader object.</span></span>
 
<span data-ttu-id="931ab-181">Теперь давайте создадим в методе `Main` код для чтения файла:</span><span class="sxs-lookup"><span data-stu-id="931ab-181">Now, let’s fill in the code to read the file in the `Main` method:</span></span> 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

<span data-ttu-id="931ab-182">Запустите программу командой `dotnet run` и убедитесь, что все текстовые строки выводятся в консоль.</span><span class="sxs-lookup"><span data-stu-id="931ab-182">Run the program (using `dotnet run` and you can see every line printed out to the console).</span></span>  

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="931ab-183">Добавление задержек и форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="931ab-183">Adding Delays and Formatting output</span></span>
<span data-ttu-id="931ab-184">Сейчас данные отображаются слишком быстро для чтения.</span><span class="sxs-lookup"><span data-stu-id="931ab-184">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="931ab-185">Поэтому нам нужно добавить задержку в процесс вывода.</span><span class="sxs-lookup"><span data-stu-id="931ab-185">Now you need to add the delays in the output.</span></span> <span data-ttu-id="931ab-186">Для этого вы создадите несложный код, выполняющий асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="931ab-186">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="931ab-187">Но первые наши действия будут нарушать стандартные рекомендации.</span><span class="sxs-lookup"><span data-stu-id="931ab-187">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="931ab-188">Эти нарушения мы укажем в комментариях при создании кода, а затем заменим этот код в последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="931ab-188">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="931ab-189">В этом разделе описаны два действия.</span><span class="sxs-lookup"><span data-stu-id="931ab-189">There are two steps to this section.</span></span> <span data-ttu-id="931ab-190">Во-первых, обновите метод итератора, чтобы он возвращал не всю строку целиком, а каждое слово отдельно.</span><span class="sxs-lookup"><span data-stu-id="931ab-190">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="931ab-191">Для этого внесите такие изменения.</span><span class="sxs-lookup"><span data-stu-id="931ab-191">That’s done with these modifications.</span></span> <span data-ttu-id="931ab-192">Замените инструкцию `yield return line;` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="931ab-192">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="931ab-193">Теперь следует изменить код обработки строк файла, добавив задержку после вывода каждого слова.</span><span class="sxs-lookup"><span data-stu-id="931ab-193">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="931ab-194">Замените инструкцию `Console.WriteLine(line)` в методе `Main` на такой блок кода:</span><span class="sxs-lookup"><span data-stu-id="931ab-194">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

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

<span data-ttu-id="931ab-195">Класс `Task` находится в пространства имен `System.Threading.Tasks`, поэтому эту инструкцию `using` нужно добавить в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="931ab-195">The `Task` class is in the `System.Threading.Tasks` namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="931ab-196">Запустите пример и проверьте выходные данные.</span><span class="sxs-lookup"><span data-stu-id="931ab-196">Run the sample, and check the output.</span></span> <span data-ttu-id="931ab-197">Теперь слова появляются по одному и с задержками по 200 мс.</span><span class="sxs-lookup"><span data-stu-id="931ab-197">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="931ab-198">Но пока с выводом сохраняются некоторые проблемы, поскольку в исходном текстовом файле есть несколько строк длиной более 80 символов, и они выводятся без перевода строки.</span><span class="sxs-lookup"><span data-stu-id="931ab-198">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="931ab-199">Это не очень удобно читать с прокруткой.</span><span class="sxs-lookup"><span data-stu-id="931ab-199">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="931ab-200">Но эту проблему легко исправить.</span><span class="sxs-lookup"><span data-stu-id="931ab-200">That’s easy to fix.</span></span> <span data-ttu-id="931ab-201">Вам нужно лишь отслеживать длину каждой строки и создавать перевод строки каждый раз, когда эта длина достигает определенного порога.</span><span class="sxs-lookup"><span data-stu-id="931ab-201">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="931ab-202">После объявления `words` объявите локальную переменную для хранения длины строки.</span><span class="sxs-lookup"><span data-stu-id="931ab-202">Declare a local variable after the declaration of `words` that holds the line length:</span></span>

```csharp
var lineLength = 0;
```
 
<span data-ttu-id="931ab-203">Теперь добавьте следующий код после инструкции `yield return word + " ";` (перед закрывающей фигурной скобкой):</span><span class="sxs-lookup"><span data-stu-id="931ab-203">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
<span data-ttu-id="931ab-204">Запустите пример, и теперь вы сможете читать текст вслух в заданном темпе.</span><span class="sxs-lookup"><span data-stu-id="931ab-204">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="931ab-205">Асинхронные задачи</span><span class="sxs-lookup"><span data-stu-id="931ab-205">Async Tasks</span></span>
<span data-ttu-id="931ab-206">И на последнем этапе мы добавим код, который будет выполнять две асинхронные задачи, одна из которых осуществляет вывод текста, а вторая ожидает ввод от пользователя для ускорения или замедления вывода текста.</span><span class="sxs-lookup"><span data-stu-id="931ab-206">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="931ab-207">Этот этап разделяется на несколько шагов, по завершении которых вы получите все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="931ab-207">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="931ab-208">Первым шагом является создание асинхронной задачи (@System.Threading.Tasks.Task), которая возвращает метод с тем кодом, который вы создали ранее для чтения и отображения файла.</span><span class="sxs-lookup"><span data-stu-id="931ab-208">The first step is to create an asynchronous @System.Threading.Tasks.Task returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="931ab-209">Добавьте следующий метод в класс `Program`. Этот текст основан на тексте метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="931ab-209">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="931ab-210">Но вы можете заметить два изменения.</span><span class="sxs-lookup"><span data-stu-id="931ab-210">You’ll notice two changes.</span></span> <span data-ttu-id="931ab-211">Во-первых, в тексте нет вызова @System.Threading.Tasks.Task.Wait, который в синхронном режиме ожидает завершения задачи. Вместо него в этой версии используется ключевое слово `await`.</span><span class="sxs-lookup"><span data-stu-id="931ab-211">First, in the body of the method, instead of calling @System.Threading.Tasks.Task.Wait to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="931ab-212">Чтобы это работало, в сигнатуру метода нужно добавить модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="931ab-212">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="931ab-213">Этот метод возвращает `Task`.</span><span class="sxs-lookup"><span data-stu-id="931ab-213">This method returns a `Task`.</span></span> <span data-ttu-id="931ab-214">Обратите внимание, что здесь нет инструкции для возвращения объекта `Task`.</span><span class="sxs-lookup"><span data-stu-id="931ab-214">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="931ab-215">Вместо этого объект `Task` создается в коде, который компилятор предоставляет в точке использования оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="931ab-215">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="931ab-216">Представьте, что метод завершает выполнение при достижении `await`.</span><span class="sxs-lookup"><span data-stu-id="931ab-216">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="931ab-217">Он возвращает `Task` в знак того, что работа еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="931ab-217">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="931ab-218">Метод возобновит свою работу, когда завершится ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="931ab-218">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="931ab-219">Когда работа метода завершится, это будет отражено в возвращаемом объекте `Task`.</span><span class="sxs-lookup"><span data-stu-id="931ab-219">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="931ab-220">Вызывающий код может отслеживать состояние полученного `Task`, чтобы определить момент завершения метода.</span><span class="sxs-lookup"><span data-stu-id="931ab-220">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="931ab-221">Теперь наш новый метод можно вызвать из метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="931ab-221">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="931ab-222">Здесь, в методе `Main`, код синхронно ожидает завершения.</span><span class="sxs-lookup"><span data-stu-id="931ab-222">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="931ab-223">Всегда, когда это возможно, следует использовать оператор `await` вместо синхронного ожидания.</span><span class="sxs-lookup"><span data-stu-id="931ab-223">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="931ab-224">Но в методе `Main` консольного приложения запрещено использовать оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="931ab-224">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="931ab-225">В противном случае приложение завершит работу раньше, чем выполнит все свои задачи.</span><span class="sxs-lookup"><span data-stu-id="931ab-225">That would result in the application exiting before all tasks have completed.</span></span>

<span data-ttu-id="931ab-226">Теперь следует создать второй асинхронный метод, который будет читать ввод из консоли и реагировать на клавиши "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="931ab-226">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="931ab-227">Для выполнения этой задачи добавьте такой метод:</span><span class="sxs-lookup"><span data-stu-id="931ab-227">Here’s the method you add for that task:</span></span>

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

<span data-ttu-id="931ab-228">Здесь создается лямбда-выражение, представляющее делегат @System.Action, который считывает нажатие клавиши из консоли и изменяет локальную переменную с длительностью задержки в том случае, если пользователь нажал клавишу "<" или ">".</span><span class="sxs-lookup"><span data-stu-id="931ab-228">This creates a lambda expression to represent an @System.Action delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="931ab-229">Этот метод использует метод @System.Console.ReadKey, чтобы блокировать выполнение и ожидать нажатия клавиши.</span><span class="sxs-lookup"><span data-stu-id="931ab-229">This method uses @System.Console.ReadKey to block and wait for the user to press a key.</span></span>

<span data-ttu-id="931ab-230">Чтобы завершить создание этой функции, нам нужна новая инструкция `async Task`, которая вернет метод, запускающий обе задачи (`GetInput` и `ShowTeleprompter`) и управляющий обменом данными между этими задачами.</span><span class="sxs-lookup"><span data-stu-id="931ab-230">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>
 
<span data-ttu-id="931ab-231">Пришло время создать класс, который может обрабатывать совместное использование данных двумя задачами.</span><span class="sxs-lookup"><span data-stu-id="931ab-231">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="931ab-232">Этот класс содержит два открытых свойства: delay (задержка) и flag (флаг), который обозначает, что файл прочитан полностью:</span><span class="sxs-lookup"><span data-stu-id="931ab-232">This class contains two public properties: the delay, and a flag to indicate that the file has been completely read:</span></span>

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
    }
}
```

<span data-ttu-id="931ab-233">Поместите этот класс в отдельный новый файл и заключите в пространство имен `TeleprompterConsole`, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="931ab-233">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="931ab-234">Также следует добавить инструкцию `using static`, чтобы использовать ссылки на методы `Min` и `Max` без указания имени внешнего класса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="931ab-234">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` method without the enclosing class or namespace names.</span></span> <span data-ttu-id="931ab-235">Инструкция `using static` импортирует все методы из одного класса.</span><span class="sxs-lookup"><span data-stu-id="931ab-235">A `using static` statement imports the methods from one class.</span></span> <span data-ttu-id="931ab-236">В этом она отличается от использованной ранее инструкции `using`, которая импортирует все классы из пространства имен.</span><span class="sxs-lookup"><span data-stu-id="931ab-236">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="931ab-237">Еще одна новая для вас функция языка — это инструкция `lock`.</span><span class="sxs-lookup"><span data-stu-id="931ab-237">The other language feature that’s new is the `lock` statement.</span></span> <span data-ttu-id="931ab-238">Она гарантирует, что в этом коде в любой момент может выполняться только один поток.</span><span class="sxs-lookup"><span data-stu-id="931ab-238">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="931ab-239">Если любой из потоков выполняет заблокированный раздел, все остальные потоки должны ожидать, пока он не выйдет из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="931ab-239">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="931ab-240">Инструкция `lock` использует объект, который защищает заблокированный раздел.</span><span class="sxs-lookup"><span data-stu-id="931ab-240">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="931ab-241">Этот класс соответствует стандартному принципу блокировки частного объекта в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="931ab-241">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="931ab-242">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput` для использования нового объекта `config`.</span><span class="sxs-lookup"><span data-stu-id="931ab-242">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="931ab-243">И еще одна инструкция `Task`, которая возвращает метод `async`, запускающий обе задачи и завершающий работу после окончания первой задачи:</span><span class="sxs-lookup"><span data-stu-id="931ab-243">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="931ab-244">Здесь мы используем вызов нового метода @System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[]).</span><span class="sxs-lookup"><span data-stu-id="931ab-244">The one new method here is the @System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[]) call.</span></span> <span data-ttu-id="931ab-245">Этот метод создает задачу (`Task`), которая завершается сразу, как только завершится любая из задач в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="931ab-245">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="931ab-246">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput`, чтобы они использовали объект `config` для задержки:</span><span class="sxs-lookup"><span data-stu-id="931ab-246">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

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

<span data-ttu-id="931ab-247">Новая версия метода `ShowTeleprompter` вызывает новый метод из класса `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="931ab-247">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="931ab-248">Сейчас нужно изменить метод `Main`, чтобы вместо `ShowTeleprompter` он вызывал `RunTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="931ab-248">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

<span data-ttu-id="931ab-249">И наконец, добавьте в класс `TelePrompterConfig` метод `SetDone` и свойство `Done`:</span><span class="sxs-lookup"><span data-stu-id="931ab-249">To finish, you'll need to add the `SetDone` method, and the `Done` property to the `TelePrompterConfig` class:</span></span>

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

## <a name="conclusion"></a><span data-ttu-id="931ab-250">Заключение</span><span class="sxs-lookup"><span data-stu-id="931ab-250">Conclusion</span></span>
<span data-ttu-id="931ab-251">В этом учебнике мы продемонстрировали вам ряд функций языка C# и библиотек .NET Core, связанных с работой в консольных приложениях.</span><span class="sxs-lookup"><span data-stu-id="931ab-251">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="931ab-252">На основе полученных знаний вы сможете развивать свои представления о языке и представленных здесь классах.</span><span class="sxs-lookup"><span data-stu-id="931ab-252">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="931ab-253">Вы увидели базовые примеры использования файлового и консольного ввода-вывода, асинхронного программирования на основе задач с блокировкой и без блокировки. Вы получили информацию о языке C#, структуре программ на C#, а также об интерфейсе командной строки и средствах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="931ab-253">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task based Asynchronous programming model, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>
 

