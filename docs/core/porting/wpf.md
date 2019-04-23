---
title: Портирование приложения WPF в .NET Core 3.0
description: В этой статье объясняется, как перенести приложение Windows Presentation Foundation из .NET Framework в .NET Core 3.0 для Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342210"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="f75eb-103">Практическое руководство. Портирование классического приложения WPF в .NET Core</span><span class="sxs-lookup"><span data-stu-id="f75eb-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="f75eb-104">В этой статье объясняется, как перенести классическое приложение, созданное на основе Windows Presentation Foundation, из .NET Framework в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="f75eb-105">В пакет SDK для .NET Core 3.0 включена поддержка приложений WPF.</span><span class="sxs-lookup"><span data-stu-id="f75eb-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="f75eb-106">Windows Presentation Foundation — это платформа, которая по-прежнему поддерживается и функционирует только в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="f75eb-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="f75eb-107">В этом примере для создания проекта и управления им используется CLI пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="f75eb-108">В этой статье применяются различные имена для обозначения типов файлов, используемых для переноса.</span><span class="sxs-lookup"><span data-stu-id="f75eb-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="f75eb-109">При переносе вашего проекта файлы будут называться иначе, поэтому попытайтесь мысленно сопоставить их с именами из этой таблицы:</span><span class="sxs-lookup"><span data-stu-id="f75eb-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="f75eb-110">Файл</span><span class="sxs-lookup"><span data-stu-id="f75eb-110">File</span></span> | <span data-ttu-id="f75eb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f75eb-111">Description</span></span> |
| ---- | ----------- |
| **<span data-ttu-id="f75eb-112">MyApps.sln</span><span class="sxs-lookup"><span data-stu-id="f75eb-112">MyApps.sln</span></span>** | <span data-ttu-id="f75eb-113">Имя файла решения.</span><span class="sxs-lookup"><span data-stu-id="f75eb-113">The name of the solution file.</span></span> |
| **<span data-ttu-id="f75eb-114">MyWPF.csproj</span><span class="sxs-lookup"><span data-stu-id="f75eb-114">MyWPF.csproj</span></span>** | <span data-ttu-id="f75eb-115">Имя проекта WPF в .NET Framework, который нужно перенести.</span><span class="sxs-lookup"><span data-stu-id="f75eb-115">The name of the .NET Framework WPF project to port.</span></span> |
| **<span data-ttu-id="f75eb-116">MyWPFCore.csproj</span><span class="sxs-lookup"><span data-stu-id="f75eb-116">MyWPFCore.csproj</span></span>** | <span data-ttu-id="f75eb-117">Имя создаваемого проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-117">The name of the new .NET Core project you create.</span></span> |
| **<span data-ttu-id="f75eb-118">MyAppCore.exe</span><span class="sxs-lookup"><span data-stu-id="f75eb-118">MyAppCore.exe</span></span>** | <span data-ttu-id="f75eb-119">Исполняемый файл WPF-приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-119">The .NET Core WPF app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="f75eb-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f75eb-120">Prerequisites</span></span>

- <span data-ttu-id="f75eb-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) для выполнения конструкторских задач.</span><span class="sxs-lookup"><span data-stu-id="f75eb-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="f75eb-122">Установите следующие рабочие нагрузки Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f75eb-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="f75eb-123">Разработка классических приложений .NET</span><span class="sxs-lookup"><span data-stu-id="f75eb-123">.NET desktop development</span></span>
  - <span data-ttu-id="f75eb-124">разработка кроссплатформенных приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="f75eb-124">.NET cross-platform development</span></span>

- <span data-ttu-id="f75eb-125">Функционирующий проект WPF в решении, сборка и запуск которого выполняется без ошибок.</span><span class="sxs-lookup"><span data-stu-id="f75eb-125">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="f75eb-126">Код проекта должен быть написан на C#.</span><span class="sxs-lookup"><span data-stu-id="f75eb-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="f75eb-127">Установите последнюю предварительную версию [.NET Core 3.0](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="f75eb-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="f75eb-128">**Visual Studio 2017** не поддерживает проекты .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="f75eb-129">**Visual Studio 2019** поддерживает проекты .NET Core 3.0, но пока не поддерживает визуальный конструктор для проектов WPF в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-129">**Visual Studio 2019** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 WPF projects.</span></span> <span data-ttu-id="f75eb-130">Чтобы использовать визуальный конструктор, необходимо, чтобы решение проекта WPF в .NET имело общие файлы с проектом .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-130">To use the visual designer, you must have a .NET WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="f75eb-131">Consider</span><span class="sxs-lookup"><span data-stu-id="f75eb-131">Consider</span></span>

<span data-ttu-id="f75eb-132">При переносе приложения WPF из .NET Framework необходимо учесть ряд аспектов.</span><span class="sxs-lookup"><span data-stu-id="f75eb-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="f75eb-133">Удостоверьтесь, что ваше приложение подходит для переноса.</span><span class="sxs-lookup"><span data-stu-id="f75eb-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="f75eb-134">Воспользуйтесь [анализатором переносимости .NET](../../standard/analyzers/portability-analyzer.md), чтобы выяснить, можно ли перенести проект в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="f75eb-135">Если у проекта есть проблемы с .NET Core 3.0, анализатор поможет их обнаружить.</span><span class="sxs-lookup"><span data-stu-id="f75eb-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="f75eb-136">Вы используете другую версию WPF.</span><span class="sxs-lookup"><span data-stu-id="f75eb-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="f75eb-137">После выпуска .NET Core 3.0 предварительной версии 1 исходный код WPF был размещен в свободном доступе на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="f75eb-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="f75eb-138">Код .NET Core WPF является вилкой от базы кода .NET Framework WPF.</span><span class="sxs-lookup"><span data-stu-id="f75eb-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="f75eb-139">Возможно, в используемой вами версии есть некоторые отличия и приложение не удастся перенести.</span><span class="sxs-lookup"><span data-stu-id="f75eb-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="f75eb-140">[Пакет обеспечения совместимости Windows][compat-pack] может помочь с переносом.</span><span class="sxs-lookup"><span data-stu-id="f75eb-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="f75eb-141">Некоторые API, доступные в .NET Framework, недоступны в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="f75eb-142">[Пакет обеспечения совместимости Windows][compat-pack] поддерживает многие из этих API и может обеспечить WPF-приложению совместимость с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="f75eb-143">Обновите пакеты NuGet, используемые в проекте.</span><span class="sxs-lookup"><span data-stu-id="f75eb-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="f75eb-144">Рекомендуется обновить пакеты NuGet до последней версии перед переносом.</span><span class="sxs-lookup"><span data-stu-id="f75eb-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="f75eb-145">Если ваше приложение ссылается на пакеты NuGet, обновите их до последней версии.</span><span class="sxs-lookup"><span data-stu-id="f75eb-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="f75eb-146">Убедитесь, что сборка приложения выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="f75eb-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="f75eb-147">Если после обновления возникают ошибки пакетов, установите предыдущую версию пакетов, которая не нарушает работу вашего кода.</span><span class="sxs-lookup"><span data-stu-id="f75eb-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="f75eb-148">Visual Studio 2019 пока не поддерживает конструктор WPF для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f75eb-148">Visual Studio 2019 doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="f75eb-149">Вам необходимо сохранить существующий файл проекта WPF для .NET Framework, если вы хотите использовать конструктор WPF в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f75eb-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="f75eb-150">Создание проекта пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f75eb-150">Create a new SDK project</span></span>

<span data-ttu-id="f75eb-151">Проект .NET Core 3.0 необходимо создать в другом каталоге, а не в том, где находится проект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="f75eb-152">Если разместить проекты в одном каталоге, могут возникнуть конфликты с файлами, создаваемыми в каталоге **obj**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="f75eb-153">В этом примере мы создадим каталог с именем **MyWPFAppCore** в каталоге **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="f75eb-154">Далее необходимо создать проект **MyWPFCore.csproj** в каталоге **MyWPFAppCore**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="f75eb-155">Можно создать этот файл вручную с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="f75eb-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="f75eb-156">Вставьте следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="f75eb-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f75eb-157">Если вы не хотите вручную создавать файл проекта, можно воспользоваться Visual Studio или пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="f75eb-158">Но необходимо удалить все остальные файлы, созданные с помощью шаблона проекта, за исключением файла проекта.</span><span class="sxs-lookup"><span data-stu-id="f75eb-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="f75eb-159">Чтобы использовать пакет SDK, выполните следующую команду из каталога **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="f75eb-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="f75eb-160">После создания **MyWPFCore.csproj** структура каталогов должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f75eb-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="f75eb-161">С помощью Visual Studio или .NET Core CLI проект **MyWPFCore.csproj** необходимо добавить в файл **MyApps.sln** из каталога **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="f75eb-162">Устранение ошибки со сведениями о сборке</span><span class="sxs-lookup"><span data-stu-id="f75eb-162">Fix assembly info generation</span></span>

<span data-ttu-id="f75eb-163">Проекты Windows Presentation Foundation, созданные с помощью .NET Framework, содержат файл `AssemblyInfo.cs` с атрибутами сборки, такими как версия создаваемой сборки.</span><span class="sxs-lookup"><span data-stu-id="f75eb-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="f75eb-164">В проектах, созданных с помощью пакета SDK, эти сведения создаются автоматически на основе файла проекта.</span><span class="sxs-lookup"><span data-stu-id="f75eb-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="f75eb-165">Наличие двух типов файлов со сведениями о сборке приводит к конфликту.</span><span class="sxs-lookup"><span data-stu-id="f75eb-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="f75eb-166">Чтобы устранить эту проблему, нужно отключить автоматическое создание такого файла, и тогда в проекте будет использоваться существующий файл `AssemblyInfo.cs`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="f75eb-167">В главный узел `<PropertyGroup>` необходимо добавить три параметра.</span><span class="sxs-lookup"><span data-stu-id="f75eb-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- **<span data-ttu-id="f75eb-168">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="f75eb-168">GenerateAssemblyInfo</span></span>**\
<span data-ttu-id="f75eb-169">Если задать этому свойству значение `false`, атрибуты сборки создаваться не будут.</span><span class="sxs-lookup"><span data-stu-id="f75eb-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="f75eb-170">Это позволит избежать конфликта с существующим файлом `AssemblyInfo.cs` из проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- **<span data-ttu-id="f75eb-171">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="f75eb-171">AssemblyName</span></span>**\
<span data-ttu-id="f75eb-172">Значением этого свойства является выходной двоичный файл, создаваемый при сборке.</span><span class="sxs-lookup"><span data-stu-id="f75eb-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="f75eb-173">К имени не требуется добавлять расширение.</span><span class="sxs-lookup"><span data-stu-id="f75eb-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="f75eb-174">Например, если задать `MyCoreApp`, будет создан файл `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- **<span data-ttu-id="f75eb-175">RootNamespace</span><span class="sxs-lookup"><span data-stu-id="f75eb-175">RootNamespace</span></span>**\
<span data-ttu-id="f75eb-176">Это пространство имен по умолчанию, используемое в проекте.</span><span class="sxs-lookup"><span data-stu-id="f75eb-176">The default namespace used by your project.</span></span> <span data-ttu-id="f75eb-177">Оно должно соответствовать пространству имен по умолчанию проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="f75eb-178">Добавьте эти три элемента в узел `<PropertyGroup>` файла `MyWPFCore.csproj`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="f75eb-179">Добавление исходного кода</span><span class="sxs-lookup"><span data-stu-id="f75eb-179">Add source code</span></span>
<span data-ttu-id="f75eb-180">Сейчас проект **MyWPFCore.csproj** не может компилировать код.</span><span class="sxs-lookup"><span data-stu-id="f75eb-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="f75eb-181">По умолчанию проекты .NET Core автоматически добавляют весь исходный код в текущий каталог и все дочерние каталоги.</span><span class="sxs-lookup"><span data-stu-id="f75eb-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="f75eb-182">Необходимо настроить проект так, чтобы добавлять код из проекта .NET Framework, используя относительный путь.</span><span class="sxs-lookup"><span data-stu-id="f75eb-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="f75eb-183">Если в вашем проекте .NET Framework используются **RESX**-файлы для окон и элементов управления, их также необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="f75eb-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="f75eb-184">Первый узел `<ItemGroup>`, который необходимо добавить в проект, включает файл **App.xaml**, представляющий конфигурацию запуска и ресурсы, используемые приложением.</span><span class="sxs-lookup"><span data-stu-id="f75eb-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="f75eb-185">Файл **App.xaml** также сопровождает соответствующий файл **App.xaml.cs**, но он будет автоматически включаться в другом `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="f75eb-186">Затем добавьте в проект указанный ниже узел `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="f75eb-187">Каждая инструкция содержит стандартную маску файла, охватывающую дочерние каталоги.</span><span class="sxs-lookup"><span data-stu-id="f75eb-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="f75eb-188">Он включает в себя исходный код для проекта, все файлы параметров и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f75eb-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="f75eb-189">Каталог **Obj** явным образом исключен.</span><span class="sxs-lookup"><span data-stu-id="f75eb-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="f75eb-190">Далее включите другой узел `<ItemGroup>`, содержащий запись `<Page>` для каждого **XAML**-файла в проекте, за исключением **App.xaml**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="f75eb-191">Они содержат описания всех окон, страниц и ресурсов, которые находятся в формате **XAML**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="f75eb-192">Здесь невозможно использовать маски; следует добавить запись для каждого файла и указать используемый `<Generator>`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="f75eb-193">Добавление пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="f75eb-193">Add NuGet packages</span></span>

<span data-ttu-id="f75eb-194">Добавьте в проект .NET Core все пакеты NuGet, на которые ссылается проект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="f75eb-195">В вашем WPF-приложении для .NET Framework, скорее всего, есть файл **packages.config**, содержащий список всех пакетов NuGet, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="f75eb-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="f75eb-196">Этот список поможет вам определить, какие пакеты NuGet нужно добавить в проект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="f75eb-197">Например, если проект .NET Framework ссылается на пакет `MahApps.Metro` в NuGet, добавьте его в проект с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f75eb-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="f75eb-198">Ссылку можно также добавить с помощью .NET Core CLI из каталога **SolutionFolder**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="f75eb-199">Приведенная выше команда добавляет следующие ссылку на пакеты NuGet в проект **MyWPFCore.csproj**.</span><span class="sxs-lookup"><span data-stu-id="f75eb-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="f75eb-200">Проблемы со сборкой</span><span class="sxs-lookup"><span data-stu-id="f75eb-200">Problems compiling</span></span>

<span data-ttu-id="f75eb-201">Если возникают проблемы при сборке проектов, причина может быть в том, что вы используете некоторые API только для Windows, которые доступны в .NET Framework, но недоступны в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="f75eb-202">Попробуйте добавить в свой проект такой пакет NuGet, как [пакет обеспечения совместимости Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="f75eb-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="f75eb-203">Этот пакет выполняется только в среде Windows и добавляет около 20 000 API Windows в проекты .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f75eb-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="f75eb-204">Предыдущая команда добавляет следующую ссылку в проект **MyWPFCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="f75eb-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="f75eb-205">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="f75eb-205">WPF Designer</span></span>

<span data-ttu-id="f75eb-206">Как упоминалось выше, Visual Studio 2019 поддерживает конструктор WPF только в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-206">As detailed in this article, Visual Studio 2019 only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="f75eb-207">Создав параллельный проект .NET Core, можно проверить его работу в .NET Core, используя при этом конструктор форм в проекте .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="f75eb-208">В файле решения будут присутствовать оба проекта — NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="f75eb-209">Добавляйте и создавайте формы и элементы управления в проекте .NET Framework, а стандартные маски файлов, добавленные нами в проекты .NET Core, позволят автоматически добавлять новые или измененные файлы в проекты .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="f75eb-210">Когда в Visual Studio 2019 будет добавлена поддержка конструктора WPF, можно будет скопировать и вставить содержимое файла проекта .NET Core в файл проекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f75eb-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="f75eb-211">Затем можно удалить стандартные маски файлов, добавленные с помощью элементов `<Source>` и `<EmbeddedResource>`.</span><span class="sxs-lookup"><span data-stu-id="f75eb-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="f75eb-212">Исправьте пути ссылок проекта, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="f75eb-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="f75eb-213">Это позволит полноценно преобразовать проект .NET Framework в проект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="f75eb-214">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f75eb-214">Next steps</span></span>

* <span data-ttu-id="f75eb-215">Дополнительные сведения о [пакете обеспечения совместимости Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="f75eb-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="f75eb-216">[Видео о переносе](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) проекта WPF из .NET Framework в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f75eb-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
