---
title: Консольное приложение
description: Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.
ms.date: 03/06/2017
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: dfd8124eb79690286e5cd876de57394a4d741328
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058403"
---
# <a name="console-application"></a><span data-ttu-id="2ef6e-103">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="2ef6e-103">Console Application</span></span>

<span data-ttu-id="2ef6e-104">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="2ef6e-105">Вы познакомитесь со следующими аспектами:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-105">You’ll learn:</span></span>

- <span data-ttu-id="2ef6e-106">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="2ef6e-106">The basics of the .NET Core Command Line Interface (CLI)</span></span>
- <span data-ttu-id="2ef6e-107">структура консольного приложения C#;</span><span class="sxs-lookup"><span data-stu-id="2ef6e-107">The structure of a C# Console Application</span></span>
- <span data-ttu-id="2ef6e-108">консольный ввод-вывод;</span><span class="sxs-lookup"><span data-stu-id="2ef6e-108">Console I/O</span></span>
- <span data-ttu-id="2ef6e-109">основные сведения об интерфейсах API файлового ввода-вывода в .NET;</span><span class="sxs-lookup"><span data-stu-id="2ef6e-109">The basics of File I/O APIs in .NET</span></span>
- <span data-ttu-id="2ef6e-110">основные сведениях об асинхронном программировании задач в .NET.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-110">The basics of the Task-based Asynchronous Programming in .NET</span></span>

<span data-ttu-id="2ef6e-111">Вам предстоит создать приложение, которое считывает текстовый файл и выводит его содержимое в консоль.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-111">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="2ef6e-112">Вывод в консоль осуществляется с такой скоростью, которая позволяет читать текст вслух.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-112">The output to the console is paced to match reading it aloud.</span></span> <span data-ttu-id="2ef6e-113">Скорость можно будет увеличивать или уменьшать клавишами "<" (меньше) и ">".</span><span class="sxs-lookup"><span data-stu-id="2ef6e-113">You can speed up or slow down the pace by pressing the ‘<’ (less than) or ‘>’ (greater than) keys.</span></span>

<span data-ttu-id="2ef6e-114">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-114">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="2ef6e-115">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-115">Let’s build them one by one.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ef6e-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2ef6e-116">Prerequisites</span></span>

<span data-ttu-id="2ef6e-117">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-117">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="2ef6e-118">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-118">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="2ef6e-119">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-119">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="2ef6e-120">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-120">You’ll need to install your favorite code editor.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="2ef6e-121">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="2ef6e-121">Create the Application</span></span>

<span data-ttu-id="2ef6e-122">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-122">The first step is to create a new application.</span></span> <span data-ttu-id="2ef6e-123">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-123">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="2ef6e-124">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-124">Make that the current directory.</span></span> <span data-ttu-id="2ef6e-125">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-125">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="2ef6e-126">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-126">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="2ef6e-127">Прежде чем вносить изменения в это приложение, давайте разберем процедуру его запуска.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-127">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="2ef6e-128">Когда вы создадите приложение, наберите в командной строке команду `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-128">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="2ef6e-129">Она запускает процесс восстановления из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-129">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="2ef6e-130">NuGet представляет собой диспетчер пакетов для .NET.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-130">NuGet is a .NET package manager.</span></span> <span data-ttu-id="2ef6e-131">Эта команда загружает все отсутствующие зависимости для проекта.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-131">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="2ef6e-132">Поскольку мы имеем дело с новым проектом, для него пока не существует зависимостей, поэтому при первом запуске будет загружена только платформа .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-132">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="2ef6e-133">После этого первого запуска команду `dotnet restore` нужно будет запускать только после добавления новых зависимых пакетов или при обновлении версий используемых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-133">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2ef6e-134">Когда завершится восстановление пакетов, запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-134">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="2ef6e-135">Эта команда запускает подсистему сборки и создает исполняемый файл приложения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-135">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="2ef6e-136">Теперь можно выполнить команду `dotnet run`, которая запустит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-136">Finally, you execute `dotnet run` to run your application.</span></span>

<span data-ttu-id="2ef6e-137">Весь код простого приложения Hello World размещается в файле Program.cs.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-137">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="2ef6e-138">Откройте этот файл в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-138">Open that file with your favorite text editor.</span></span> <span data-ttu-id="2ef6e-139">Сейчас мы внесем в него первые изменения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-139">We’re about to make our first changes.</span></span>
<span data-ttu-id="2ef6e-140">В верхней части файла вы видите инструкцию using:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-140">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="2ef6e-141">Эта инструкция указывает компилятору, что в области действия находятся все типы из пространства имен `System`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-141">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="2ef6e-142">Как и другие объектно ориентированные языки, с которыми вы могли работать ранее, C# использует пространства имен для организации типов.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-142">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="2ef6e-143">В нашей программе Hello World все точно так же.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-143">This Hello World program is no different.</span></span> <span data-ttu-id="2ef6e-144">Как вы видите, программа заключена в пространство имен, имя которого соответствует имени текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-144">You can see that the program is enclosed in the namespace with the name based on the name of the current directory.</span></span> <span data-ttu-id="2ef6e-145">В этом учебнике давайте изменим имя на `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-145">For this tutorial, let's change the name of the namespace to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="2ef6e-146">Чтение и вывод файла</span><span class="sxs-lookup"><span data-stu-id="2ef6e-146">Reading and Echoing the File</span></span>

<span data-ttu-id="2ef6e-147">Первая функция, которую мы добавим, будет считывать данные из текстового файла и выводить полученный текст в консоль.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-147">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="2ef6e-148">Сначала нам нужно добавить текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-148">First, let’s add a text file.</span></span> <span data-ttu-id="2ef6e-149">Скопируйте в каталог проекта файл [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) из репозитория GitHub для этого [примера](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-149">Copy the [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="2ef6e-150">Он будет источником текста для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-150">This will serve as the script for your application.</span></span> <span data-ttu-id="2ef6e-151">Чтобы скачать пример приложения для этого раздела, воспользуйтесь инструкциями в разделе [Примеры и руководства](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-151">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="2ef6e-152">Теперь добавьте в класс `Program` (он расположен сразу за методом `Main`) следующий метод:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-152">Next, add the following method in your `Program` class (right below the `Main` method):</span></span>

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

<span data-ttu-id="2ef6e-153">Этот метод использует типы из двух новых пространств имен.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-153">This method uses types from two new namespaces.</span></span> <span data-ttu-id="2ef6e-154">Чтобы такая программа успешно скомпилировалась, нужно добавить в начало файла следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-154">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="2ef6e-155">Интерфейс <xref:System.Collections.Generic.IEnumerable%601> определен в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-155">The <xref:System.Collections.Generic.IEnumerable%601> interface is defined in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="2ef6e-156">Класс <xref:System.IO.File> определен в пространстве имен <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-156">The <xref:System.IO.File> class is defined in the <xref:System.IO> namespace.</span></span>

<span data-ttu-id="2ef6e-157">Этот метод является специальным типом *метода перечислителя* C#.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-157">This method is a special type of C# method called an *Iterator method*.</span></span> <span data-ttu-id="2ef6e-158">Метод перечислителя возвращает последовательности, для которых применяется отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-158">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="2ef6e-159">Это означает, что каждый элемент в последовательности создается только в тот момент, когда к нему выполняется обращение в коде обработки последовательности.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-159">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="2ef6e-160">Методы перечислителя содержат один или несколько операторов [`yield return`](../language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-160">Enumerator methods are methods that contain one or more [`yield return`](../language-reference/keywords/yield.md) statements.</span></span> <span data-ttu-id="2ef6e-161">Возвращаемый методом `ReadFrom` объект содержит код для создания каждого элемента последовательности.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-161">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="2ef6e-162">В нашем примере он читает следующую строку текста из исходного файла и возвращает эту строку.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-162">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="2ef6e-163">Каждый раз, когда вызывающий код запрашивает следующий элемент из последовательности, код считывает из файла и возвращает следующую строку текста.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-163">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="2ef6e-164">Когда файл закончится, последовательность сообщает, что в ней больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-164">When the file is completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="2ef6e-165">Здесь используются еще два элемента синтаксиса C#, которые могут быть для вас новыми.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-165">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="2ef6e-166">Оператор [`using`](../language-reference/keywords/using-statement.md) в этом методе управляет освобождением ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-166">The [`using`](../language-reference/keywords/using-statement.md) statement in this method manages resource cleanup.</span></span> <span data-ttu-id="2ef6e-167">Переменная, которая инициализируется в инструкции `using` (в нашем примере это `reader`) должна реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-167">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="2ef6e-168">Этот интерфейс определяет единственный метод (`Dispose`), который вызывается для освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-168">That interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="2ef6e-169">Компилятор создает такой вызов, когда выполнение кода достигает закрывающей скобки инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-169">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="2ef6e-170">Созданный компилятором код гарантирует освобождение ресурса даже в том случае, если в блоке кода, определенном инструкцией using, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-170">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="2ef6e-171">Переменная `reader` определена с ключевым словом `var`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-171">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="2ef6e-172">Ключевое слово [`var`](../language-reference/keywords/var.md) определяет *неявно типизированную локальную переменную*.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-172">[`var`](../language-reference/keywords/var.md) defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="2ef6e-173">Это означает, что тип переменной определяется во время компиляции по типу объекта, присвоенного этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-173">That means the type of the variable is determined by the compile-time type of the object assigned to the variable.</span></span> <span data-ttu-id="2ef6e-174">Здесь это возвращаемое значение метода <xref:System.IO.File.OpenText(System.String)>, то есть объект <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-174">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>

<span data-ttu-id="2ef6e-175">Теперь давайте создадим в методе `Main` код для чтения файла:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-175">Now, let’s fill in the code to read the file in the `Main` method:</span></span>

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

<span data-ttu-id="2ef6e-176">Запустите программу командой `dotnet run` и убедитесь в том, что все текстовые строки выводятся в консоль.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-176">Run the program (using `dotnet run`) and you can see every line printed out to the console.</span></span>

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="2ef6e-177">Добавление задержек и форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="2ef6e-177">Adding Delays and Formatting output</span></span>

<span data-ttu-id="2ef6e-178">Сейчас данные отображаются слишком быстро для чтения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-178">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="2ef6e-179">Поэтому нам нужно добавить задержку в процесс вывода.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-179">Now you need to add the delays in the output.</span></span> <span data-ttu-id="2ef6e-180">Для этого вы создадите несложный код, выполняющий асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-180">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="2ef6e-181">Но первые наши действия будут нарушать стандартные рекомендации.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-181">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="2ef6e-182">Эти нарушения мы укажем в комментариях при создании кода, а затем заменим этот код в последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-182">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="2ef6e-183">В этом разделе описаны два действия.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-183">There are two steps to this section.</span></span> <span data-ttu-id="2ef6e-184">Во-первых, обновите метод итератора, чтобы он возвращал не всю строку целиком, а каждое слово отдельно.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-184">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="2ef6e-185">Для этого внесите такие изменения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-185">That’s done with these modifications.</span></span> <span data-ttu-id="2ef6e-186">Замените инструкцию `yield return line;` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-186">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="2ef6e-187">Теперь следует изменить код обработки строк файла, добавив задержку после вывода каждого слова.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-187">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="2ef6e-188">Замените инструкцию `Console.WriteLine(line)` в методе `Main` на такой блок кода:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-188">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

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

<span data-ttu-id="2ef6e-189">Класс <xref:System.Threading.Tasks.Task> находится в пространства имен <xref:System.Threading.Tasks>, поэтому эту инструкцию `using` нужно добавить в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-189">The <xref:System.Threading.Tasks.Task> class is in the <xref:System.Threading.Tasks> namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="2ef6e-190">Запустите пример и проверьте выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-190">Run the sample, and check the output.</span></span> <span data-ttu-id="2ef6e-191">Теперь слова появляются по одному и с задержками по 200 мс.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-191">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="2ef6e-192">Но пока с выводом сохраняются некоторые проблемы, поскольку в исходном текстовом файле есть несколько строк длиной более 80 символов, и они выводятся без перевода строки.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-192">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="2ef6e-193">Это не очень удобно читать с прокруткой.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-193">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="2ef6e-194">Но эту проблему легко исправить.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-194">That’s easy to fix.</span></span> <span data-ttu-id="2ef6e-195">Вам нужно лишь отслеживать длину каждой строки и создавать перевод строки каждый раз, когда эта длина достигает определенного порога.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-195">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="2ef6e-196">После объявления `words` в методе `ReadFrom` объявите локальную переменную для хранения длины строки:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-196">Declare a local variable after the declaration of `words` in the `ReadFrom` method that holds the line length:</span></span>

```csharp
var lineLength = 0;
```

<span data-ttu-id="2ef6e-197">Теперь добавьте следующий код после инструкции `yield return word + " ";` (перед закрывающей фигурной скобкой):</span><span class="sxs-lookup"><span data-stu-id="2ef6e-197">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

<span data-ttu-id="2ef6e-198">Запустите пример, и теперь вы сможете читать текст вслух в заданном темпе.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-198">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="2ef6e-199">Асинхронные задачи</span><span class="sxs-lookup"><span data-stu-id="2ef6e-199">Async Tasks</span></span>

<span data-ttu-id="2ef6e-200">И на последнем этапе мы добавим код, который позволяет выполнять две асинхронные задачи, одна из которых — вывод текста, а вторая — ожидание ввода от пользователя для ускорения, замедления или прекращения вывода текста.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-200">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display, or stop the text display altogether.</span></span> <span data-ttu-id="2ef6e-201">Этот этап разделяется на несколько шагов, по завершении которых вы получите все необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-201">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="2ef6e-202">Первым шагом является создание асинхронной задачи (<xref:System.Threading.Tasks.Task>), которая возвращает метод с тем кодом, который вы создали ранее для чтения и отображения файла.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-202">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="2ef6e-203">Добавьте следующий метод в класс `Program`. Этот текст основан на тексте метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-203">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

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

<span data-ttu-id="2ef6e-204">Но вы можете заметить два изменения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-204">You’ll notice two changes.</span></span> <span data-ttu-id="2ef6e-205">Во-первых, в тексте нет вызова <xref:System.Threading.Tasks.Task.Wait>, который в синхронном режиме ожидает завершения задачи. Вместо него в этой версии используется ключевое слово `await`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-205">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="2ef6e-206">Чтобы это работало, в сигнатуру метода нужно добавить модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-206">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="2ef6e-207">Этот метод возвращает `Task`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-207">This method returns a `Task`.</span></span> <span data-ttu-id="2ef6e-208">Обратите внимание, что здесь нет инструкции для возвращения объекта `Task`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-208">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="2ef6e-209">Вместо этого объект `Task` создается в коде, который компилятор предоставляет в точке использования оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-209">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="2ef6e-210">Представьте, что метод завершает выполнение при достижении `await`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-210">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="2ef6e-211">Он возвращает `Task` в знак того, что работа еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-211">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="2ef6e-212">Метод возобновит свою работу, когда завершится ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-212">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="2ef6e-213">Когда работа метода завершится, это будет отражено в возвращаемом объекте `Task`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-213">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="2ef6e-214">Вызывающий код может отслеживать состояние полученного `Task`, чтобы определить момент завершения метода.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-214">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="2ef6e-215">Теперь наш новый метод можно вызвать из метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-215">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="2ef6e-216">Здесь, в методе `Main`, код синхронно ожидает завершения.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-216">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="2ef6e-217">Всегда, когда это возможно, следует использовать оператор `await` вместо синхронного ожидания.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-217">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="2ef6e-218">Но в методе `Main` консольного приложения запрещено использовать оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-218">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="2ef6e-219">В противном случае приложение завершит работу раньше, чем выполнит все свои задачи.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-219">That would result in the application exiting before all tasks have completed.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef6e-220">При использовании C# 7.1 или более поздней версии консольные приложения можно создавать с помощью [метода `async` `Main`](../whats-new/csharp-7-1.md#async-main).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-220">If you use C# 7.1 or later, you can create console applications with [`async` `Main` method](../whats-new/csharp-7-1.md#async-main).</span></span>

<span data-ttu-id="2ef6e-221">Теперь следует создать второй асинхронный метод, который позволяет считывать данные ввода из консоли и реагировать на клавиши "<" (меньше), ">" (больше) и "X" или "x".</span><span class="sxs-lookup"><span data-stu-id="2ef6e-221">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ (less than), ‘>’ (greater than) and ‘X’ or ‘x’ keys.</span></span> <span data-ttu-id="2ef6e-222">Для выполнения этой задачи добавьте такой метод:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-222">Here’s the method you add for that task:</span></span>

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
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
            {
                break;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="2ef6e-223">Здесь создается лямбда-выражение, представляющее делегат <xref:System.Action>, который считывает нажатие клавиши из консоли и изменяет локальную переменную с длительностью задержки в том случае, если пользователь нажал клавишу "<" (меньше) или ">" (больше).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-223">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ (less than) or ‘>’ (greater than) keys.</span></span> <span data-ttu-id="2ef6e-224">Выполнение метода делегата можно завершить, нажав клавишу "X" или "x". Таким образом пользователь может в любой момент прекратить отображение текста.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-224">The delegate method finishes when user presses the ‘X’ or ‘x’  keys, which allow the user to stop the text display at any time.</span></span>
<span data-ttu-id="2ef6e-225">Этот метод использует метод <xref:System.Console.ReadKey>, чтобы блокировать выполнение и ожидать нажатия клавиши.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-225">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="2ef6e-226">Чтобы завершить создание этой функции, нам нужна новая инструкция `async Task`, которая вернет метод, запускающий обе задачи (`GetInput` и `ShowTeleprompter`) и управляющий обменом данными между этими задачами.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-226">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>

<span data-ttu-id="2ef6e-227">Пришло время создать класс, который может обрабатывать совместное использование данных двумя задачами.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-227">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="2ef6e-228">Этот класс содержит два открытых свойства: delay (задержка) и флаг `Done`, который означает, что файл прочитан полностью:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-228">This class contains two public properties: the delay, and a flag `Done` to indicate that the file has been completely read:</span></span>

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

<span data-ttu-id="2ef6e-229">Поместите этот класс в отдельный новый файл и заключите в пространство имен `TeleprompterConsole`, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-229">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="2ef6e-230">Также следует добавить оператор `using static`, чтобы можно было ссылаться на методы `Min` и `Max` без указания имени внешнего класса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-230">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` methods without the enclosing class or namespace names.</span></span> <span data-ttu-id="2ef6e-231">Оператор [`using static`](../language-reference/keywords/using-static.md) импортирует методы из одного класса.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-231">A [`using static`](../language-reference/keywords/using-static.md) statement imports the methods from one class.</span></span> <span data-ttu-id="2ef6e-232">В этом она отличается от использованной ранее инструкции `using`, которая импортирует все классы из пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-232">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="2ef6e-233">Еще одна новая для вас функция языка — это оператор [`lock`](../language-reference/keywords/lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-233">The other language feature that’s new is the [`lock`](../language-reference/keywords/lock-statement.md) statement.</span></span> <span data-ttu-id="2ef6e-234">Она гарантирует, что в этом коде в любой момент может выполняться только один поток.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-234">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="2ef6e-235">Если любой из потоков выполняет заблокированный раздел, все остальные потоки должны ожидать, пока он не выйдет из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-235">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="2ef6e-236">Инструкция `lock` использует объект, который защищает заблокированный раздел.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-236">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="2ef6e-237">Этот класс соответствует стандартному принципу блокировки частного объекта в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-237">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="2ef6e-238">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput` для использования нового объекта `config`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-238">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="2ef6e-239">И еще одна инструкция `Task`, которая возвращает метод `async`, запускающий обе задачи и завершающий работу после окончания первой задачи:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-239">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="2ef6e-240">Новым методом здесь является <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-240">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="2ef6e-241">Этот метод создает задачу (`Task`), которая завершается сразу, как только завершится любая из задач в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-241">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="2ef6e-242">Теперь вам нужно обновить методы `ShowTeleprompter` и `GetInput`, чтобы они использовали объект `config` для задержки:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-242">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
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
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
                config.SetDone();
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="2ef6e-243">Новая версия метода `ShowTeleprompter` вызывает новый метод из класса `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-243">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="2ef6e-244">Сейчас нужно изменить метод `Main`, чтобы вместо `ShowTeleprompter` он вызывал `RunTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-244">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a><span data-ttu-id="2ef6e-245">Заключение</span><span class="sxs-lookup"><span data-stu-id="2ef6e-245">Conclusion</span></span>

<span data-ttu-id="2ef6e-246">В этом учебнике мы продемонстрировали вам ряд функций языка C# и библиотек .NET Core, связанных с работой в консольных приложениях.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-246">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="2ef6e-247">На основе полученных знаний вы сможете развивать свои представления о языке и представленных здесь классах.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-247">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="2ef6e-248">Вы увидели базовые примеры использования файлового и консольного ввода-вывода, асинхронного программирования на основе задач с блокировкой и без блокировки. Вы получили информацию о языке C#, структуре программ на C#, а также об интерфейсе командной строки и средствах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-248">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task-based asynchronous programming, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>

<span data-ttu-id="2ef6e-249">Дополнительные сведения о файловом вводе-выводе см. в статье [Файловый и потоковый ввод-вывод](../../standard/io/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-249">For more information about File I/O, see the [File and Stream I/O](../../standard/io/index.md) topic.</span></span> <span data-ttu-id="2ef6e-250">Дополнительные сведения о модели асинхронного программирования, используемой в учебнике, см. в статьях [Асинхронное программирование на основе задач](../..//standard/parallel-programming/task-based-asynchronous-programming.md) и [Асинхронное программирование](../async.md).</span><span class="sxs-lookup"><span data-stu-id="2ef6e-250">For more information about asynchronous programming model used in this tutorial, see the [Task-based Asynchronous Programming](../..//standard/parallel-programming/task-based-asynchronous-programming.md) topic and the [Asynchronous programming](../async.md) topic.</span></span>
