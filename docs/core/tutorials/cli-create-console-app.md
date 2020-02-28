---
title: Начало работы с .NET Core с помощью средств интерфейса командной строки
description: Пошаговое руководство по использованию .NET Core в Windows, Linux или macOS с помощью .NET Core CLI.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: af1b374cd14d5070194c035024ce2328c9016646
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503540"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="781e2-103">Начало работы с .NET Core с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="781e2-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="781e2-104">В этой статье показано, как приступить к разработке приложений .NET Core для Windows, Linux и macOS с помощью .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="781e2-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="781e2-105">Если вы не знакомы с .NET Core CLI, см. сведения о [пакете SDK для .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="781e2-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="781e2-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="781e2-106">Prerequisites</span></span>

- <span data-ttu-id="781e2-107">[Пакет SDK для .NET Core 3.1](https://dotnet.microsoft.com/download) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="781e2-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="781e2-108">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="781e2-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="781e2-109">Первое консольное приложение</span><span class="sxs-lookup"><span data-stu-id="781e2-109">Hello, Console App!</span></span>

<span data-ttu-id="781e2-110">[Просмотреть или скачать пример кода](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) можно в репозитории dotnet/samples на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="781e2-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="781e2-111">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="781e2-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="781e2-112">Откройте командную строку и создайте папку с именем *Hello*.</span><span class="sxs-lookup"><span data-stu-id="781e2-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="781e2-113">Перейдите в созданную папку и введите приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="781e2-113">Navigate to the folder you created and type the following.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="781e2-114">Вкратце рассмотрим эти команды.</span><span class="sxs-lookup"><span data-stu-id="781e2-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="781e2-115">[dotnet new](../tools/dotnet-new.md) создает актуальный файл проекта *Hello.csproj* с зависимостями, необходимыми для создания консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="781e2-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="781e2-116">Эта команда также позволяет создать *Program.cs* — простой файл, содержащий точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="781e2-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>
    
    <span data-ttu-id="781e2-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="781e2-117">*Hello.csproj*:</span></span>
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    <span data-ttu-id="781e2-118">В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.</span><span class="sxs-lookup"><span data-stu-id="781e2-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>
    
    - <span data-ttu-id="781e2-119">Элемент `<OutputType>` указывает, что мы создаем исполняемый файл, то есть консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="781e2-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="781e2-120">Элемент `<TargetFramework>` указывает, какая реализация.NET является целевой.</span><span class="sxs-lookup"><span data-stu-id="781e2-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="781e2-121">В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="781e2-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="781e2-122">В этом руководстве рассматривается сборка только для платформы .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="781e2-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>
    
    <span data-ttu-id="781e2-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="781e2-123">*Program.cs*:</span></span>
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    <span data-ttu-id="781e2-124">Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла".</span><span class="sxs-lookup"><span data-stu-id="781e2-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="781e2-125">Пространство имен `System` включает класс `Console`.</span><span class="sxs-lookup"><span data-stu-id="781e2-125">The `System` namespace includes the `Console` class.</span></span>
    
    <span data-ttu-id="781e2-126">Затем мы определяем пространство имен с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="781e2-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="781e2-127">Вы можете сменить это имя на любое другое.</span><span class="sxs-lookup"><span data-stu-id="781e2-127">You can change this to anything you want.</span></span> <span data-ttu-id="781e2-128">В этом пространстве имен определяется класс с именем `Program` и методом `Main`, который принимает массив строк с именем `args`.</span><span class="sxs-lookup"><span data-stu-id="781e2-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="781e2-129">Этот массив содержит список аргументов, передаваемых при вызове программы.</span><span class="sxs-lookup"><span data-stu-id="781e2-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="781e2-130">В нашем примере массив не используется и программа просто выводит строку "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="781e2-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="781e2-131">в консоль.</span><span class="sxs-lookup"><span data-stu-id="781e2-131">to the console.</span></span> <span data-ttu-id="781e2-132">Позднее мы внесем в код изменения, использующие этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="781e2-132">Later, we'll make changes to the code that will make use of this argument.</span></span>
    
    <span data-ttu-id="781e2-133">`dotnet new` неявно вызывает [dotnet restore](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="781e2-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="781e2-134">`dotnet restore` вызывает [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET) для восстановления дерева зависимостей.</span><span class="sxs-lookup"><span data-stu-id="781e2-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="781e2-135">NuGet анализирует файл *Hello.csproj*, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл *obj/project.assets.json*, который требуется для компиляции и запуска примера.</span><span class="sxs-lookup"><span data-stu-id="781e2-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="781e2-136">[dotnet run](../tools/dotnet-run.md) вызывает [dotnet build](../tools/dotnet-build.md), чтобы проверить, выполнена ли сборка целевых объектов. Затем вызывается `dotnet <assembly.dll>` для запуска целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="781e2-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
    
    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="781e2-137">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="781e2-137">You get the following output.</span></span>

    ```console
    Hello World!
    ```
    
    <span data-ttu-id="781e2-138">Вместо этого вы можете выполнить `dotnet build`, чтобы скомпилировать код, не запуская консольные приложения сборки.</span><span class="sxs-lookup"><span data-stu-id="781e2-138">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="781e2-139">В таком случае создается DLL-файл с готовым приложением. Файлу присваивается имя проекта.</span><span class="sxs-lookup"><span data-stu-id="781e2-139">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="781e2-140">В нашем примере создается файл с именем *Hello.dll*.</span><span class="sxs-lookup"><span data-stu-id="781e2-140">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="781e2-141">Это приложение можно выполнить с помощью `dotnet bin\Debug\netcoreapp3.1\Hello.dll` в ОС Windows (или `/` в системах, отличных от Windows).</span><span class="sxs-lookup"><span data-stu-id="781e2-141">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>
    
    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    <span data-ttu-id="781e2-142">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="781e2-142">You get the following output.</span></span>

    ```console
    Hello World!
    ```
    
    <span data-ttu-id="781e2-143">При компиляции этого приложения создается исполняемый файл, формат которого зависит от операционной системы, а также `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="781e2-143">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="781e2-144">В Windows это будет `Hello.exe`, а в Linux или macOS — `hello`.</span><span class="sxs-lookup"><span data-stu-id="781e2-144">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="781e2-145">Для приведенного выше примера файлу будет присвоено имя `Hello.exe` или `Hello`.</span><span class="sxs-lookup"><span data-stu-id="781e2-145">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="781e2-146">Этот исполняемый файл можно запускать напрямую.</span><span class="sxs-lookup"><span data-stu-id="781e2-146">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="781e2-147">Изменение программы</span><span class="sxs-lookup"><span data-stu-id="781e2-147">Modify the program</span></span>

<span data-ttu-id="781e2-148">Давайте немного изменим программу.</span><span class="sxs-lookup"><span data-stu-id="781e2-148">Let's change the program a bit.</span></span> <span data-ttu-id="781e2-149">С числами Фибоначчи интересно работать. Поэтому давайте добавим их в программу, а также применим аргумент для приветствия пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="781e2-149">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="781e2-150">Замените содержимое файла *Program.cs* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="781e2-150">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="781e2-151">Выполните [dotnet build](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="781e2-151">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="781e2-152">Запустите программу, передав параметр в приложение.</span><span class="sxs-lookup"><span data-stu-id="781e2-152">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="781e2-153">Когда вы запускаете приложение с помощью команды `dotnet`, добавьте в конце `--`.</span><span class="sxs-lookup"><span data-stu-id="781e2-153">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="781e2-154">Все, что находится справа от `--`, будет передано в приложение в виде параметра.</span><span class="sxs-lookup"><span data-stu-id="781e2-154">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="781e2-155">В приведенном ниже примере в приложение передается значение `John`.</span><span class="sxs-lookup"><span data-stu-id="781e2-155">In the following example, the value `John` is passed to the app.</span></span>

    ```dotnetcli
    dotnet run -- John
    ```

    <span data-ttu-id="781e2-156">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="781e2-156">You get the following output.</span></span>

    ```console
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

<span data-ttu-id="781e2-157">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="781e2-157">And that's it!</span></span> <span data-ttu-id="781e2-158">Вы можете изменять *Program.cs* по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="781e2-158">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="781e2-159">Работа с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="781e2-159">Working with multiple files</span></span>

<span data-ttu-id="781e2-160">Отдельные файлы удобны для простых одиночных программ. Но при создании более сложных приложений, возможно, в проекте будет несколько файлов кода.</span><span class="sxs-lookup"><span data-stu-id="781e2-160">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="781e2-161">Используем в качестве основы предыдущий пример, реализовав в нем кэширование значений Фибоначчи и рекурсию.</span><span class="sxs-lookup"><span data-stu-id="781e2-161">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="781e2-162">Добавьте в каталог *Hello* новый файл *FibonacciGenerator.cs* со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="781e2-162">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="781e2-163">Измените метод `Main` в своем файле *Program.cs*, чтобы создать экземпляр класса new и вызвать его метод, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="781e2-163">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="781e2-164">Выполните [dotnet build](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="781e2-164">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="781e2-165">Запустите приложение, выполнив [dotnet run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="781e2-165">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="781e2-166">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="781e2-166">You get the following output.</span></span>

    ```console
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

## <a name="publish-your-app"></a><span data-ttu-id="781e2-167">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="781e2-167">Publish your app</span></span>

<span data-ttu-id="781e2-168">Когда все будет готово к распределению приложения, используйте команду [dotnet publish](../tools/dotnet-publish.md) для создания папки _publish_ по адресу _bin\\debug\\netcoreapp3.1\\publish\\_ (используйте `/` для систем, отличных от Windows).</span><span class="sxs-lookup"><span data-stu-id="781e2-168">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="781e2-169">Содержимое папки _publish_ можно распространить на другие платформы, если на них установлена среда выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="781e2-169">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```dotnetcli
dotnet publish
```

<span data-ttu-id="781e2-170">Вы получите результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="781e2-170">You get output similar to the following.</span></span>

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="781e2-171">Выходные данные могут отличаться от представленных выше из-за другого значения текущей папки и (или) операционной системы. Но в остальном данные будут такими же.</span><span class="sxs-lookup"><span data-stu-id="781e2-171">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="781e2-172">Запустить опубликованное приложение можно с помощью команды [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="781e2-172">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

<span data-ttu-id="781e2-173">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="781e2-173">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="781e2-174">Как уже упоминалось в начале статьи, создается исполняемый файл, формат которого зависит от операционной системы, а также `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="781e2-174">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="781e2-175">В Windows это будет `Hello.exe`, а в Linux или macOS — `hello`.</span><span class="sxs-lookup"><span data-stu-id="781e2-175">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="781e2-176">Для приведенного выше примера файлу будет присвоено имя `Hello.exe` или `Hello`.</span><span class="sxs-lookup"><span data-stu-id="781e2-176">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="781e2-177">Опубликованный исполняемый файл можно запускать напрямую.</span><span class="sxs-lookup"><span data-stu-id="781e2-177">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="781e2-178">Заключение</span><span class="sxs-lookup"><span data-stu-id="781e2-178">Conclusion</span></span>

<span data-ttu-id="781e2-179">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="781e2-179">And that's it!</span></span> <span data-ttu-id="781e2-180">Теперь вы можете воспользоваться изученными здесь основными концепциями, чтобы создавать собственные программы.</span><span class="sxs-lookup"><span data-stu-id="781e2-180">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="781e2-181">См. также</span><span class="sxs-lookup"><span data-stu-id="781e2-181">See also</span></span>

- [<span data-ttu-id="781e2-182">Организация и тестирование проектов с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="781e2-182">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="781e2-183">Публикация приложений .NET Core с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="781e2-183">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="781e2-184">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="781e2-184">.NET Core application deployment</span></span>](../deploying/index.md)
