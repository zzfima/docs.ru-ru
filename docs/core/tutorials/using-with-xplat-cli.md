---
title: Начало работы с .NET Core с помощью средств интерфейса командной строки
description: Пошаговое руководство, описывающее начало работы с .NET Core в Windows, Linux или macOS с помощью интерфейса командной строки (CLI) .NET Core.
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: cf8c3ae070f4c77789dc55ba4d7888c7b15c8653
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736990"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="e6a49-103">Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="e6a49-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="e6a49-104">В этом разделе показано, как приступить к разработке кроссплатформенных приложений с помощью средств интерфейса командной строки (CLI) .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6a49-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="e6a49-105">Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6a49-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6a49-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e6a49-106">Prerequisites</span></span>

- <span data-ttu-id="e6a49-107">[Пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e6a49-107">[.NET Core SDK 2.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="e6a49-108">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="e6a49-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="e6a49-109">Первое консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e6a49-109">Hello, Console App!</span></span>

<span data-ttu-id="e6a49-110">[Просмотреть или скачать пример кода](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) можно в репозитории dotnet/samples на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="e6a49-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="e6a49-111">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e6a49-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="e6a49-112">Откройте командную строку и создайте папку с именем *Hello*.</span><span class="sxs-lookup"><span data-stu-id="e6a49-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="e6a49-113">Перейдите в созданную папку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e6a49-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="e6a49-114">Вкратце рассмотрим эти команды.</span><span class="sxs-lookup"><span data-stu-id="e6a49-114">Let's do a quick walkthrough:</span></span>

1. `dotnet new console`

   <span data-ttu-id="e6a49-115">С помощью [`dotnet new`](../tools/dotnet-new.md) создается актуальный файл проекта *Hello.csproj* с зависимостями, необходимыми для создания консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="e6a49-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="e6a49-116">Эта команда также позволяет создать *Program.cs* — простой файл, содержащий точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="e6a49-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="e6a49-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="e6a49-117">*Hello.csproj*:</span></span>

   [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="e6a49-118">В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.</span><span class="sxs-lookup"><span data-stu-id="e6a49-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   - <span data-ttu-id="e6a49-119">Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="e6a49-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   - <span data-ttu-id="e6a49-120">Тег `TargetFramework` указывает, какая реализация.NET является целевой.</span><span class="sxs-lookup"><span data-stu-id="e6a49-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="e6a49-121">В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="e6a49-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="e6a49-122">В этом руководстве рассматривается сборка только для платформы .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e6a49-122">In this tutorial, we'll stick to building only for .NET Core 2.1.</span></span>

   <span data-ttu-id="e6a49-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="e6a49-123">*Program.cs*:</span></span>

   [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="e6a49-124">Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла".</span><span class="sxs-lookup"><span data-stu-id="e6a49-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="e6a49-125">Пространство имен `System` включает класс `Console`.</span><span class="sxs-lookup"><span data-stu-id="e6a49-125">The `System` namespace includes the `Console` class.</span></span>

   <span data-ttu-id="e6a49-126">Затем мы определяем пространство имен с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="e6a49-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="e6a49-127">Вы можете сменить это имя на любое другое.</span><span class="sxs-lookup"><span data-stu-id="e6a49-127">You can change this to anything you want.</span></span> <span data-ttu-id="e6a49-128">Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="e6a49-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="e6a49-129">Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы.</span><span class="sxs-lookup"><span data-stu-id="e6a49-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="e6a49-130">В такой форме программа не использует этот массив. Единственное ее действие — вывод надписи "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="e6a49-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="e6a49-131">в консоль.</span><span class="sxs-lookup"><span data-stu-id="e6a49-131">to the console.</span></span> <span data-ttu-id="e6a49-132">Позднее мы внесем в код изменения, использующие этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="e6a49-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="e6a49-133">`dotnet new` неявно вызывает [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="e6a49-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="e6a49-134">`dotnet restore` вызывает [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET) для восстановления дерева зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e6a49-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="e6a49-135">NuGet анализирует файл *Hello.csproj*, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл *obj/project.assets.json*, который требуется для компиляции и запуска примера.</span><span class="sxs-lookup"><span data-stu-id="e6a49-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e6a49-136">Если вы используете пакет SDK для .NET Core 1.x, необходимо самому вызвать `dotnet restore` после вызова `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="e6a49-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `dotnet run`

   <span data-ttu-id="e6a49-137">[`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="e6a49-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="e6a49-138">Кроме того, вы можете выполнить [`dotnet build`](../tools/dotnet-build.md), чтобы скомпилировать код, не запуская консольные приложения сборки.</span><span class="sxs-lookup"><span data-stu-id="e6a49-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="e6a49-139">В результате мы получаем скомпилированное приложение в виде файла DLL, которое можно выполнить с помощью `dotnet bin\Debug\netcoreapp2.1\Hello.dll` в Windows или `/` в других операционных системах.</span><span class="sxs-lookup"><span data-stu-id="e6a49-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="e6a49-140">Вы также можете указать аргументы для приложения, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e6a49-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="e6a49-141">В расширенном сценарии можно собрать приложение в качестве автономного набора файлов для определенной платформы, которые можно развернуть и запустить на компьютере без .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6a49-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="e6a49-142">Чтобы получить подробные сведения, см. статью [.NET Core Application Deployment](../deploying/index.md) (Развертывание приложений .NET Core).</span><span class="sxs-lookup"><span data-stu-id="e6a49-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="e6a49-143">Расширение программы</span><span class="sxs-lookup"><span data-stu-id="e6a49-143">Augmenting the program</span></span>

<span data-ttu-id="e6a49-144">Давайте немного изменим программу.</span><span class="sxs-lookup"><span data-stu-id="e6a49-144">Let's change the program a bit.</span></span> <span data-ttu-id="e6a49-145">С числами Фибоначчи интересно работать, поэтому давайте добавим следующее в дополнение к использованию аргумента для приветствия пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="e6a49-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="e6a49-146">Замените содержимое файла *Program.cs* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="e6a49-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="e6a49-147">Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="e6a49-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="e6a49-148">Запустите программу, передав параметр в приложение:</span><span class="sxs-lookup"><span data-stu-id="e6a49-148">Run the program passing a parameter to the app:</span></span>

   ```console
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

<span data-ttu-id="e6a49-149">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="e6a49-149">And that's it!</span></span>  <span data-ttu-id="e6a49-150">Вы можете расширять файл *Program.cs* по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="e6a49-150">You can augment *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="e6a49-151">Работа с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="e6a49-151">Working with multiple files</span></span>

<span data-ttu-id="e6a49-152">Отдельные файлы хороши для простых одиночных программ, но при создании более сложных приложений, возможно, в проекте будет несколько исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="e6a49-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project.</span></span>
<span data-ttu-id="e6a49-153">Используем в качестве основы предыдущий пример, реализовав в нем кэширование значений Фибоначчи и рекурсию.</span><span class="sxs-lookup"><span data-stu-id="e6a49-153">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="e6a49-154">Добавьте в каталог *Hello* новый файл *FibonacciGenerator.cs* со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="e6a49-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="e6a49-155">Измените метод `Main` в своем файле *Program.cs*, чтобы создать экземпляр класса new и вызвать его метод, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e6a49-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="e6a49-156">Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.</span><span class="sxs-lookup"><span data-stu-id="e6a49-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="e6a49-157">Запустите приложение, выполнив [`dotnet run`](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="e6a49-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="e6a49-158">Ниже приведены выходные данные программы:</span><span class="sxs-lookup"><span data-stu-id="e6a49-158">The following shows the program output:</span></span>

   ```console
   $ dotnet run
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

## <a name="publish-your-app"></a><span data-ttu-id="e6a49-159">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="e6a49-159">Publish your app</span></span>

<span data-ttu-id="e6a49-160">Когда вы будете готовы к распространению приложения, используйте команду [`dotnet publish`](../tools/dotnet-publish.md) для создания папки _publish_ в _bin\\debug\\netcoreapp 2.1.\\publish\\_ (используйте `/` для систем, отличных от Windows).</span><span class="sxs-lookup"><span data-stu-id="e6a49-160">Once you're ready to distribute your app, use the [`dotnet publish`](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp2.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="e6a49-161">Содержимое папки _publish_ можно распространить на другие платформы, если на них установлена среда выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="e6a49-161">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

<span data-ttu-id="e6a49-162">Запустить опубликованное приложение можно с помощью команды [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="e6a49-162">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="e6a49-163">Заключение</span><span class="sxs-lookup"><span data-stu-id="e6a49-163">Conclusion</span></span>

<span data-ttu-id="e6a49-164">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="e6a49-164">And that's it!</span></span> <span data-ttu-id="e6a49-165">Теперь вы можете воспользоваться изученными здесь основными концепциями, чтобы создавать собственные программы.</span><span class="sxs-lookup"><span data-stu-id="e6a49-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6a49-166">См. также</span><span class="sxs-lookup"><span data-stu-id="e6a49-166">See also</span></span>

- [<span data-ttu-id="e6a49-167">Организация и тестирование проектов с помощью инструментов командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="e6a49-167">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="e6a49-168">Публикация приложений .NET Core с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="e6a49-168">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="e6a49-169">Подробнее о развертывании приложений</span><span class="sxs-lookup"><span data-stu-id="e6a49-169">Learn more about app deployment</span></span>](../deploying/index.md)
