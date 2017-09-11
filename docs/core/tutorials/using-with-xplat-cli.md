---
title: "Начало работы с .NET Core с помощью интерфейса командной строки"
description: "Пошаговое руководство, описывающее начало работы с .NET Core в Windows, Linux или macOS с помощью интерфейса командной строки (CLI) .NET Core."
keywords: ".NET Core, интерфейс командной строки"
author: cartermp
ms.author: mairaw
ms.date: 03/08/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 41632e63-d5c6-4427-a09e-51dc1116d45f
ms.translationtype: HT
ms.sourcegitcommit: 9b63485ca10fe9f6d63c7134128bbfceaede6302
ms.openlocfilehash: b853f74ea2daa60bd68502f07f243c814c8c1947
ms.contentlocale: ru-ru
ms.lasthandoff: 08/24/2017

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="d9b81-104">Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="d9b81-104">Getting started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="d9b81-105">В этом разделе показано, как приступить к разработке кроссплатформенных приложений с помощью средств интерфейса командной строки (CLI) .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9b81-105">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="d9b81-106">Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="d9b81-106">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d9b81-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d9b81-107">Prerequisites</span></span>

- <span data-ttu-id="d9b81-108">[Пакет SDK для .NET Core 1.0](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="d9b81-108">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="d9b81-109">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="d9b81-109">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="d9b81-110">Первое консольное приложение</span><span class="sxs-lookup"><span data-stu-id="d9b81-110">Hello, Console App!</span></span>

<span data-ttu-id="d9b81-111">[Просмотреть или скачать пример кода](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild) можно в репозитории dotnet/docs на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d9b81-111">You can [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild) from the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="d9b81-112">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="d9b81-112">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="d9b81-113">Откройте командную строку и создайте папку с именем *Hello*.</span><span class="sxs-lookup"><span data-stu-id="d9b81-113">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="d9b81-114">Перейдите в созданную папку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9b81-114">Navigate to the folder you created and type the following:</span></span>

```
$ dotnet new console
$ dotnet restore
$ dotnet run
```

<span data-ttu-id="d9b81-115">Вкратце рассмотрим эти команды.</span><span class="sxs-lookup"><span data-stu-id="d9b81-115">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="d9b81-116">[`dotnet new`](../tools/dotnet-new.md) создает актуальный файл проекта `Hello.csproj` с зависимостями, необходимыми для создания консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="d9b81-116">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="d9b81-117">Эта команда также создает `Program.cs` — простой файл, содержащий точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="d9b81-117">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="d9b81-118">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="d9b81-118">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]   

   <span data-ttu-id="d9b81-119">В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.</span><span class="sxs-lookup"><span data-stu-id="d9b81-119">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="d9b81-120">Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="d9b81-120">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="d9b81-121">Тег `TargetFramework` указывает, какая реализация.NET является целевой.</span><span class="sxs-lookup"><span data-stu-id="d9b81-121">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="d9b81-122">В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="d9b81-122">In an advance scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="d9b81-123">В этом руководстве рассматривается сборка только для платформы .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="d9b81-123">In this tutorial, we'll stick to building only for .NET Core 1.0.</span></span>

   <span data-ttu-id="d9b81-124">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="d9b81-124">`Program.cs`:</span></span>

   <span data-ttu-id="d9b81-125">[!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9b81-125">[!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]</span></span>   

   <span data-ttu-id="d9b81-126">Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла".</span><span class="sxs-lookup"><span data-stu-id="d9b81-126">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="d9b81-127">Пространство имен `System` содержит основные конструкции, такие как `string`, или числовые типы.</span><span class="sxs-lookup"><span data-stu-id="d9b81-127">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="d9b81-128">Затем мы определяем пространство имен с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="d9b81-128">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="d9b81-129">Вы можете сменить это имя на любое другое.</span><span class="sxs-lookup"><span data-stu-id="d9b81-129">You can change this to anything you want.</span></span> <span data-ttu-id="d9b81-130">Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="d9b81-130">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="d9b81-131">Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы.</span><span class="sxs-lookup"><span data-stu-id="d9b81-131">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="d9b81-132">В такой форме программа не использует этот массив. Единственное ее действие — вывод надписи "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d9b81-132">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="d9b81-133">в консоль.</span><span class="sxs-lookup"><span data-stu-id="d9b81-133">to the console.</span></span> <span data-ttu-id="d9b81-134">Позднее мы внесем в код изменения, использующие этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="d9b81-134">Later, we'll make changes to the code that will make use of this argument.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="d9b81-135">[`dotnet restore`](../tools/dotnet-restore.md) вызывает [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET) для восстановления дерева зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d9b81-135">[`dotnet restore`](../tools/dotnet-restore.md) calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="d9b81-136">NuGet анализирует файл *Hello.csproj*, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл *obj/project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d9b81-136">NuGet analyzes the *Hello.csproj* file, downloads the dependencies stated in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file.</span></span>  <span data-ttu-id="d9b81-137">Файл *project.assets.json* необходим для компиляции и запуска.</span><span class="sxs-lookup"><span data-stu-id="d9b81-137">The *project.assets.json* file is necessary to be able to compile and run.</span></span>
   
   <span data-ttu-id="d9b81-138">Файл *project.assets.json* содержит сохраняемую полную схему зависимостей NuGet и другие сведения, описывающие приложение.</span><span class="sxs-lookup"><span data-stu-id="d9b81-138">The *project.assets.json* file is a persisted and complete set of the graph of NuGet dependencies and other information describing an app.</span></span>  <span data-ttu-id="d9b81-139">Этот файл считывается другими средствами, такими как [`dotnet build`](../tools/dotnet-build.md) и [`dotnet run`](../tools/dotnet-run.md), что позволяет им обрабатывать исходный код с правильным набором зависимостей NuGet и разрешений привязки.</span><span class="sxs-lookup"><span data-stu-id="d9b81-139">This file is read by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), enabling them to process the source code with a correct set of NuGet dependencies and binding resolutions.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="d9b81-140">[`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="d9b81-140">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
   
    ```
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="d9b81-141">Кроме того, вы можете выполнить [`dotnet build`](../tools/dotnet-build.md), чтобы скомпилировать код, не запуская консольные приложения сборки.</span><span class="sxs-lookup"><span data-stu-id="d9b81-141">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="d9b81-142">В результате мы получаем скомпилированное приложение в виде файла DLL, которое можно выполнить с помощью `dotnet bin\Debug\netcoreapp1.0\Hello.dll` в Windows или `/` в других операционных системах.</span><span class="sxs-lookup"><span data-stu-id="d9b81-142">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp1.0\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="d9b81-143">Вы также можете указать аргументы для приложения, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d9b81-143">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="d9b81-144">В расширенном сценарии можно собрать приложение в качестве автономного набора файлов для определенной платформы, которые можно развернуть и запустить на компьютере без .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9b81-144">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="d9b81-145">Чтобы получить подробные сведения, см. статью [.NET Core Application Deployment](../deploying/index.md) (Развертывание приложений .NET Core).</span><span class="sxs-lookup"><span data-stu-id="d9b81-145">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="d9b81-146">Расширение программы</span><span class="sxs-lookup"><span data-stu-id="d9b81-146">Augmenting the program</span></span>

<span data-ttu-id="d9b81-147">Давайте немного изменим программу.</span><span class="sxs-lookup"><span data-stu-id="d9b81-147">Let's change the program a bit.</span></span> <span data-ttu-id="d9b81-148">С числами Фибоначчи интересно работать, поэтому давайте добавим следующее в дополнение к использованию аргумента для приветствия пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="d9b81-148">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="d9b81-149">Замените содержимое файла *Program.cs* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="d9b81-149">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   <span data-ttu-id="d9b81-150">[!code-csharp[Фибоначчи](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9b81-150">[!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]</span></span>   

2. <span data-ttu-id="d9b81-151">Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="d9b81-151">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="d9b81-152">Запустите программу, передав параметр в приложение:</span><span class="sxs-lookup"><span data-stu-id="d9b81-152">Run the program passing a parameter to the app:</span></span>

   ```
   $ dotnet run -- John
   Hello John!
   Fibonacci Numbers 1-15:
   1: 0
   2: 1
   3: 1
   4: 2
   5: 3
   6: 5
   7: 8
   8: 13
   9: 21
   10: 34
   11: 55
   12: 89
   13: 144
   14: 233
   15: 377
   ```

<span data-ttu-id="d9b81-153">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="d9b81-153">And that's it!</span></span>  <span data-ttu-id="d9b81-154">Вы можете расширять файл `Program.cs` по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="d9b81-154">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="d9b81-155">Работа с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="d9b81-155">Working with multiple files</span></span>

<span data-ttu-id="d9b81-156">Отдельные файлы хороши для простых одиночных программ, но при создании более сложных приложений вам, вероятно, придется использовать несколько исходных файлов в проекте. Давайте возьмем за основу предыдущий пример Фибоначчи и кэшируем некоторые значения Фибоначчи, а также добавим несколько рекурсивных функций.</span><span class="sxs-lookup"><span data-stu-id="d9b81-156">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span> 

1. <span data-ttu-id="d9b81-157">Добавьте в каталог *Hello* новый файл *FibonacciGenerator.cs* со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="d9b81-157">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   <span data-ttu-id="d9b81-158">[!code-csharp[Генератор Фибоначчи](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9b81-158">[!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]</span></span>   

2. <span data-ttu-id="d9b81-159">Измените метод `Main` в своем файле *Program.cs*, чтобы создать экземпляр класса new и вызвать его метод, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d9b81-159">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   <span data-ttu-id="d9b81-160">[!code-csharp[Новый Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9b81-160">[!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]</span></span>

3. <span data-ttu-id="d9b81-161">Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="d9b81-161">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="d9b81-162">Запустите приложение, выполнив [`dotnet run`](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="d9b81-162">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="d9b81-163">Ниже приведены выходные данные программы:</span><span class="sxs-lookup"><span data-stu-id="d9b81-163">The following shows the program output:</span></span>

   ```
   0
   1
   1
   2
   3
   5
   8
   13
   21
   34
   55
   89
   144
   233
   377
   ```

<span data-ttu-id="d9b81-164">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="d9b81-164">And that's it!</span></span> <span data-ttu-id="d9b81-165">Теперь вы можете воспользоваться изученными здесь основными концепциями, чтобы создавать собственные программы.</span><span class="sxs-lookup"><span data-stu-id="d9b81-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="d9b81-166">Заметьте, что описанные в этом учебнике команды и шаги для запуска приложения используются только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="d9b81-166">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="d9b81-167">Когда вы будете готовы развернуть приложение, рекомендуем ознакомиться с другими [стратегиями развертывания](../deploying/index.md) для приложений .NET Core и командой [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="d9b81-167">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b81-168">См. также</span><span class="sxs-lookup"><span data-stu-id="d9b81-168">See also</span></span>

[<span data-ttu-id="d9b81-169">Организация и тестирование проектов с помощью инструментов командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9b81-169">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)

