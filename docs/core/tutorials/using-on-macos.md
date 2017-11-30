---
title: "Начало работы с .NET Core в Mac OS"
description: "В этом документе приводится обзор действий и рабочего процесса для создания решения .NET Core в Visual Studio Code."
keywords: .NET, .NET Core, Mac, macOS, Visual Studio Code
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
ms.openlocfilehash: b172e5fc4fcf9dd5c1e6f268f3c046e77592ebd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-with-net-core-on-macos"></a><span data-ttu-id="88720-104">Начало работы с .NET Core в Mac OS</span><span class="sxs-lookup"><span data-stu-id="88720-104">Getting started with .NET Core on macOS</span></span>

<span data-ttu-id="88720-105">В этом документе приводится обзор действий и рабочего процесса для создания решения .NET Core для macOS.</span><span class="sxs-lookup"><span data-stu-id="88720-105">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="88720-106">Вы узнаете, как создавать проекты и модульные тесты, использовать средства отладки и включать библиотеки сторонних разработчиков с помощью [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="88720-106">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="88720-107">В этой статье используется [Visual Studio Code](http://code.visualstudio.com) для macOS.</span><span class="sxs-lookup"><span data-stu-id="88720-107">This article uses [Visual Studio Code](http://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88720-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="88720-108">Prerequisites</span></span>

<span data-ttu-id="88720-109">Установите [пакета SDK для .NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="88720-109">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="88720-110">Пакет SDK для .NET Core содержит последний выпуск платформы и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88720-110">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="88720-111">Установите [Visual Studio Code](http://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="88720-111">Install [Visual Studio Code](http://code.visualstudio.com).</span></span> <span data-ttu-id="88720-112">В ходе этой статьи вы также установите расширения Visual Studio Code, которые улучшат возможности разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88720-112">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="88720-113">Установите расширение C# для Visual Studio Code. Для этого откройте Visual Studio Code и нажмите клавишу <kbd>F1</kbd>, чтобы открыть палитру Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="88720-113">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="88720-114">Введите команду **ext install**, чтобы просмотреть список расширений.</span><span class="sxs-lookup"><span data-stu-id="88720-114">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="88720-115">Выберите расширение C#.</span><span class="sxs-lookup"><span data-stu-id="88720-115">Select the C# extension.</span></span> <span data-ttu-id="88720-116">Перезапустите Visual Studio Code, чтобы включить расширение.</span><span class="sxs-lookup"><span data-stu-id="88720-116">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="88720-117">Дополнительные сведения см. в [документации по расширению C# для Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="88720-117">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="getting-started"></a><span data-ttu-id="88720-118">Начало работы</span><span class="sxs-lookup"><span data-stu-id="88720-118">Getting started</span></span>

<span data-ttu-id="88720-119">В этом руководстве вы создадите три проекта: проект библиотеки, тесты для этого проекта библиотеки и консольное приложение, которое использует библиотеку.</span><span class="sxs-lookup"><span data-stu-id="88720-119">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="88720-120">[Просмотреть и скачать исходный код](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) для этого раздела можно в репозитории dotnet/docs на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="88720-120">You can [view or download the source](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) for this topic at the dotnet/docs repository on GitHub.</span></span> <span data-ttu-id="88720-121">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="88720-121">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="88720-122">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="88720-122">Start Visual Studio Code.</span></span> <span data-ttu-id="88720-123">Нажмите клавишу <kbd>CTRL</kbd>+<kbd>\\`</kbd> (символ обратной кавычки или обратного апострофа) или выберите **Вид > Встроенный терминал**, чтобы открыть встроенный терминал в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="88720-123">Press <kbd>Ctrl</kbd>+<kbd>\\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="88720-124">Если вы предпочитаете работать не в среде Visual Studio Code, можете открыть внешнюю оболочку в Explorer, выбрав пункт меню проводника **Открыть в командной строке** (в Mac и Linux — **Открыть в терминале**).</span><span class="sxs-lookup"><span data-stu-id="88720-124">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="88720-125">Для начала нужно создать файл решения, который выступает в качестве контейнера для одного или нескольких проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88720-125">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="88720-126">В терминале создайте папку *golden* и откройте ее.</span><span class="sxs-lookup"><span data-stu-id="88720-126">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="88720-127">Эта папка — корневой каталог вашего решения.</span><span class="sxs-lookup"><span data-stu-id="88720-127">This folder is the root of your solution.</span></span> <span data-ttu-id="88720-128">Запустите команду [`dotnet new`](../tools/dotnet-new.md), чтобы создать новое решение — *golden.sln*:</span><span class="sxs-lookup"><span data-stu-id="88720-128">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="88720-129">Из папки *golden* выполните следующую команду, чтобы создать проект библиотеки. Эта команда создает два файла *library.csproj* и *Class1.cs* в папке *library*:</span><span class="sxs-lookup"><span data-stu-id="88720-129">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="88720-130">Выполните команду [`dotnet sln`](../tools/dotnet-sln.md), чтобы добавить только что созданный проект *library.csproj* в решение:</span><span class="sxs-lookup"><span data-stu-id="88720-130">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="88720-131">Файл *library.csproj* содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="88720-131">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="88720-132">Наши библиотечные методы сериализуют и десериализуют объекты в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="88720-132">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="88720-133">Для поддержки сериализации и десериализации JSON добавьте ссылку на пакет NuGet `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="88720-133">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="88720-134">Команда `dotnet add` добавляет в проект новые элементы.</span><span class="sxs-lookup"><span data-stu-id="88720-134">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="88720-135">Чтобы добавить ссылку на пакет NuGet, выполните команду [`dotnet add package`](../tools/dotnet-add-package.md), указав имя пакета:</span><span class="sxs-lookup"><span data-stu-id="88720-135">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="88720-136">Эта команда добавляет `Newtonsoft.Json` и его зависимости в проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="88720-136">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="88720-137">Также можно изменить файл *library.csproj* вручную, добавив следующий узел:</span><span class="sxs-lookup"><span data-stu-id="88720-137">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="88720-138">Выполнение [ `dotnet restore` ](../tools/dotnet-restore.md), ([см. Примечание](#dotnet-restore-note)) который восстанавливает зависимости и создает *obj* папки *библиотеки* с тремя в нем файлов, включая *project.assets.json* файла:</span><span class="sxs-lookup"><span data-stu-id="88720-138">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="88720-139">В каталоге *library* переименуйте файл *Class1.cs* в *Thing.cs*.</span><span class="sxs-lookup"><span data-stu-id="88720-139">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="88720-140">Замените код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="88720-140">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="88720-141">Класс `Thing` содержит один открытый метод `Get`, который возвращает сумму двух чисел, но для этого преобразует сумму в строку и затем десериализует ее в целое число.</span><span class="sxs-lookup"><span data-stu-id="88720-141">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="88720-142">В нем используется ряд современных возможностей C#, таких как [`using static`директивы](../../csharp/language-reference/keywords/using-static.md), [члены, воплощающие выражения](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) и [интерполированные строки](../../csharp/language-reference/keywords/interpolated-strings.md).</span><span class="sxs-lookup"><span data-stu-id="88720-142">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [interpolated strings](../../csharp/language-reference/keywords/interpolated-strings.md).</span></span>

<span data-ttu-id="88720-143">Соберите библиотеку, выполнив команду [`dotnet build`](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="88720-143">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="88720-144">Эта команда создает файл *library.dll* в каталоге *golden/library/bin/Debug/netstandard1.4*:</span><span class="sxs-lookup"><span data-stu-id="88720-144">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="88720-145">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="88720-145">Create the test project</span></span>

<span data-ttu-id="88720-146">Создайте тестовый проект для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="88720-146">Build a test project for the library.</span></span> <span data-ttu-id="88720-147">Из папки *golden* создайте тестовый проект:</span><span class="sxs-lookup"><span data-stu-id="88720-147">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="88720-148">Добавьте тестовый проект в решение:</span><span class="sxs-lookup"><span data-stu-id="88720-148">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="88720-149">Добавьте ссылку на проект библиотеки, созданной в предыдущем разделе, чтобы компилятор мог найти и использовать проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="88720-149">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="88720-150">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="88720-150">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="88720-151">Также можно изменить файл *test-library.csproj* вручную, добавив следующий узел:</span><span class="sxs-lookup"><span data-stu-id="88720-151">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="88720-152">Теперь, когда зависимости правильно настроены, создайте тесты для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="88720-152">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="88720-153">Откройте файл *UnitTest1.cs* и замените его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="88720-153">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="88720-154">Обратите внимание, что при создании модульного теста (`Assert.NotEqual`), который завершается ошибкой, вы проверяете утверждение, что 42 не равно 19+23 (42).</span><span class="sxs-lookup"><span data-stu-id="88720-154">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="88720-155">При создании модульных тестов важно создать такое условие, при котором тест завершится с ошибкой. Это позволяет проверить его логику.</span><span class="sxs-lookup"><span data-stu-id="88720-155">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="88720-156">Из папки *golden* выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="88720-156">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="88720-157">Эти команды рекурсивно найдут все проекты для восстановления зависимостей, соберут эти проекты и активируют средство запуска тестов xUnit для запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="88720-157">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="88720-158">Первый тест, как и ожидается, завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="88720-158">The single test fails, as you expect.</span></span>

<span data-ttu-id="88720-159">Откройте файл *UnitTest1.cs* и измените проверочное утверждение с `Assert.NotEqual` на `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="88720-159">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="88720-160">Выполните следующую команду из папки *golden*, чтобы повторно запустить тест, который на этот раз завершится успешно:</span><span class="sxs-lookup"><span data-stu-id="88720-160">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="88720-161">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="88720-161">Create the console app</span></span>

<span data-ttu-id="88720-162">Консольное приложение, которое будет создано в этом разделе, зависит от проекта библиотеки, который был создан ранее, и вызывает библиотечный метод этого проекта при запуске.</span><span class="sxs-lookup"><span data-stu-id="88720-162">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="88720-163">Вы увидите, как создавать повторно используемые библиотеки для нескольких проектов с помощью этого шаблона разработки.</span><span class="sxs-lookup"><span data-stu-id="88720-163">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="88720-164">Создайте новое консольное приложение из папки *golden*:</span><span class="sxs-lookup"><span data-stu-id="88720-164">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="88720-165">Добавьте проект консольного приложения в решение:</span><span class="sxs-lookup"><span data-stu-id="88720-165">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="88720-166">Создайте зависимость от библиотеки, выполнив команду `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="88720-166">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="88720-167">Запустите `dotnet restore` ([см. Примечание](#dotnet-restore-note)) для восстановления зависимостей из трех проектов в решении.</span><span class="sxs-lookup"><span data-stu-id="88720-167">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="88720-168">Откройте файл *Program.cs* и замените содержимое метода `Main` следующей строкой:</span><span class="sxs-lookup"><span data-stu-id="88720-168">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="88720-169">Добавьте две директивы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="88720-169">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="88720-170">Выполните следующую команду `dotnet run`, чтобы запустить исполняемый файл. Значение `dotnet run` параметра `-p` указывает проект для основного приложения.</span><span class="sxs-lookup"><span data-stu-id="88720-170">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="88720-171">Приложение выводит строку "The answer is 42".</span><span class="sxs-lookup"><span data-stu-id="88720-171">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="88720-172">Отладка приложения</span><span class="sxs-lookup"><span data-stu-id="88720-172">Debug the application</span></span>

<span data-ttu-id="88720-173">Установите точку останова в инструкции `WriteLine` метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="88720-173">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="88720-174">Для этого нажмите клавишу <kbd>F9</kbd>, установив курсор в строку `WriteLine`, или щелкнув в левом поле строки, в которой вы хотите установить точку останова.</span><span class="sxs-lookup"><span data-stu-id="88720-174">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="88720-175">В поле рядом со строкой кода появится красный кружок.</span><span class="sxs-lookup"><span data-stu-id="88720-175">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="88720-176">При достижении точки останова выполнение кода приостанавливается *перед* той строкой, в которой расположена точка останова.</span><span class="sxs-lookup"><span data-stu-id="88720-176">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="88720-177">Откройте вкладку отладчика, щелкнув значок "Отладка" на панели инструментов Visual Studio Code и выбрав **Вид > Отладка** в меню или нажав клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span><span class="sxs-lookup"><span data-stu-id="88720-177">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Отладчик Visual Studio Code](./media/using-on-macos/vscodedebugger.png)

<span data-ttu-id="88720-179">Нажмите кнопку "Воспроизвести", чтобы запустить приложение в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="88720-179">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="88720-180">Приложение выполняется до точки останова, в которой оно останавливается.</span><span class="sxs-lookup"><span data-stu-id="88720-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="88720-181">Выполните метод `Get` по шагам и убедитесь в том, что переданы правильные аргументы.</span><span class="sxs-lookup"><span data-stu-id="88720-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="88720-182">Убедитесь, что ответ равен 42.</span><span class="sxs-lookup"><span data-stu-id="88720-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]