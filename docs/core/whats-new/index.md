---
title: "Новые возможности .NET Core 2.0"
description: "Дополнительные сведения о новых возможностях .NET Core."
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: b47d4c74a01b99d743b69328c201096bc8d89794
ms.openlocfilehash: e43f72ebd26c34636c239d8ac9f749d52d3f60a0
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="6424c-104">Новые возможности .NET Core</span><span class="sxs-lookup"><span data-stu-id="6424c-104">What's new in .NET Core</span></span>

<span data-ttu-id="6424c-105">В .NET Core 2.0 представлены следующие улучшения и новые возможности:</span><span class="sxs-lookup"><span data-stu-id="6424c-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- <span data-ttu-id="6424c-106">[инструментарий](#tooling);</span><span class="sxs-lookup"><span data-stu-id="6424c-106">[Tooling](#tooling)</span></span>
- <span data-ttu-id="6424c-107">[языковая поддержка](#language-support);</span><span class="sxs-lookup"><span data-stu-id="6424c-107">[Language support](#language-support)</span></span>
- <span data-ttu-id="6424c-108">[улучшения платформы](#platform-improvements);</span><span class="sxs-lookup"><span data-stu-id="6424c-108">[Platform improvements](#platform-improvements)</span></span>
- <span data-ttu-id="6424c-109">[изменения API](#api-changes-and-library-support);</span><span class="sxs-lookup"><span data-stu-id="6424c-109">[API changes](#api-changes-and-library-support)</span></span>
- <span data-ttu-id="6424c-110">[интеграция Visual Studio](#visual-studio-integration);</span><span class="sxs-lookup"><span data-stu-id="6424c-110">[Visual Studio integration](#visual-studio-integration)</span></span>
- <span data-ttu-id="6424c-111">[усовершенствования документации](#documentation-improvements).</span><span class="sxs-lookup"><span data-stu-id="6424c-111">[Documentation improvements](#documentation-improvements)</span></span> 

## <a name="tooling"></a><span data-ttu-id="6424c-112">Инструментарий</span><span class="sxs-lookup"><span data-stu-id="6424c-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="6424c-113">Явное выполнение команды dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6424c-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="6424c-114">В предыдущих версиях .NET Core сразу после создания проекта с помощью команды [dotnet new](../tools/dotnet-new.md), а также после добавления новой зависимости в проект требовалось выполнять команду [dotnet restore](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="6424c-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span> <span data-ttu-id="6424c-115">В .NET Core 2.0 команда `dotnet restore` выполняется неявно при выполнении команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="6424c-115">In .NET Core 2.0, `dotnet restore` runs implicitly when the `dotnet new` command executes.</span></span> <span data-ttu-id="6424c-116">Она также выполняется неявно, если нужно обновить зависимости при выполнении других команд, таких как `run`, `build` и `publish`.</span><span class="sxs-lookup"><span data-stu-id="6424c-116">It also runs implicitly if dependencies need to be updated when other commands, such as the `run`, `build`, and `publish` commands, execute.</span></span>

<span data-ttu-id="6424c-117">Вы также можете отключить автоматический вызов команды `dotnet restore`. Для этого передайте параметр `--no-restore` команде `new`, `run`, `build`, `publish`, `pack` и `test`.</span><span class="sxs-lookup"><span data-stu-id="6424c-117">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="6424c-118">Изменение целевой платформы на .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6424c-118">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="6424c-119">Если установлен пакет SDK для .NET Core 2.0, для проектов, предназначенных для .NET Core 1.x, можно изменить целевую платформу на .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="6424c-119">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span> 

<span data-ttu-id="6424c-120">Чтобы изменить целевую платформу на .NET Core 2.0, измените файл проекта. Для этого измените значение элемента `<TargetFramework>` или `<TargetFrameworks>` (при наличии нескольких целевых платформ в файле проекта) с 1.x на 2.0:</span><span class="sxs-lookup"><span data-stu-id="6424c-120">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="6424c-121">Кроме того, можно также выполнить перенацеливание с библиотек .NET Standard на .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="6424c-121">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="6424c-122">Дополнительные сведения о переносе проекта в .NET Core 2.0 см. в статье [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Переход с ASP.NET Core 1.x на ASP.NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="6424c-122">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="6424c-123">Языковая поддержка</span><span class="sxs-lookup"><span data-stu-id="6424c-123">Language support</span></span>

<span data-ttu-id="6424c-124">Помимо поддержки C# и F # .NET Core 2.0 также поддерживает Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6424c-124">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="6424c-125">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6424c-125">Visual Basic</span></span>

<span data-ttu-id="6424c-126">.NET Core версии 2.0 теперь поддерживает Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="6424c-126">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="6424c-127">С помощью Visual Basic можно создать следующие типы проектов:</span><span class="sxs-lookup"><span data-stu-id="6424c-127">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="6424c-128">консольные приложения .NET Core;</span><span class="sxs-lookup"><span data-stu-id="6424c-128">.NET Core console apps</span></span>
- <span data-ttu-id="6424c-129">библиотеки классов .NET Core;</span><span class="sxs-lookup"><span data-stu-id="6424c-129">.NET Core class libraries</span></span>
- <span data-ttu-id="6424c-130">библиотеки классов .NET Standard;</span><span class="sxs-lookup"><span data-stu-id="6424c-130">.NET Standard class libraries</span></span>
- <span data-ttu-id="6424c-131">проекты модульных тестов .NET Core;</span><span class="sxs-lookup"><span data-stu-id="6424c-131">.NET Core unit test projects</span></span>
- <span data-ttu-id="6424c-132">тестовые проекты xUnit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6424c-132">.NET Core xUnit test projects</span></span> 

<span data-ttu-id="6424c-133">Например, для создания приложения Visual Basic Hello World в командной строке сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6424c-133">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="6424c-134">Откройте окно консоли, создайте каталог для проекта и выберите его в качестве текущего.</span><span class="sxs-lookup"><span data-stu-id="6424c-134">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="6424c-135">Введите команду `dotnet new console -lang vb`.</span><span class="sxs-lookup"><span data-stu-id="6424c-135">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="6424c-136">Команда создает файл проекта с расширением `.vbproj`, а также файл исходного кода Visual Basic *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="6424c-136">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="6424c-137">Этот файл содержит исходный код для записи строки Hello World!</span><span class="sxs-lookup"><span data-stu-id="6424c-137">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="6424c-138">в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="6424c-138">to the console window.</span></span>
  
1.  <span data-ttu-id="6424c-139">Введите команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="6424c-139">Enter the command `dotnet run`.</span></span> <span data-ttu-id="6424c-140">[Средства интерфейса командной строки .NET Core](../tools/index.md) автоматически компилируют и выполняют приложение, которое выводит сообщение Hello World!</span><span class="sxs-lookup"><span data-stu-id="6424c-140">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="6424c-141">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="6424c-141">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="6424c-142">Поддержка C# 7.1</span><span class="sxs-lookup"><span data-stu-id="6424c-142">Support for C# 7.1</span></span>

<span data-ttu-id="6424c-143">.NET Core 2.0 поддерживает C# 7.1, в котором реализованы новые возможности, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="6424c-143">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="6424c-144">Метод `Main`, точку входа приложения можно пометить с помощью ключевого слова [async](../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="6424c-144">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="6424c-145">Выводимые имена кортежей.</span><span class="sxs-lookup"><span data-stu-id="6424c-145">Inferred tuple names.</span></span>
- <span data-ttu-id="6424c-146">Стандартные выражения.</span><span class="sxs-lookup"><span data-stu-id="6424c-146">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="6424c-147">Улучшения платформы</span><span class="sxs-lookup"><span data-stu-id="6424c-147">Platform improvements</span></span>

<span data-ttu-id="6424c-148">В .NET Core 2.0 представлены возможности, упрощающие установку платформы .NET Core и ее использование в поддерживаемых операционных системах.</span><span class="sxs-lookup"><span data-stu-id="6424c-148">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="6424c-149">Единая реализация .NET Core для Linux</span><span class="sxs-lookup"><span data-stu-id="6424c-149">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="6424c-150">.NET Core 2.0 предлагает единую реализацию Linux, которую можно использовать в нескольких дистрибутивах Linux.</span><span class="sxs-lookup"><span data-stu-id="6424c-150">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="6424c-151">Для .NET Core 1.x требовалось, чтобы вы загрузили реализацию Linux для конкретного дистрибутива.</span><span class="sxs-lookup"><span data-stu-id="6424c-151">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="6424c-152">Кроме того, предусмотрена возможность разработки приложений, предназначенных исключительно для ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="6424c-152">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="6424c-153">В .NET Core 1.x требовалось выбирать целевую среду для каждого дистрибутива Linux отдельно.</span><span class="sxs-lookup"><span data-stu-id="6424c-153">.NET Core 1.x required that you target each Linux distribution separately.</span></span> 

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="6424c-154">Поддержка библиотек шифрования Apple</span><span class="sxs-lookup"><span data-stu-id="6424c-154">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="6424c-155">В .NET Core 1.x на macOS требовалась библиотека шифрования для набора средств OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="6424c-155">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="6424c-156">.NET Core 2.0 использует библиотеки шифрования Apple и не требует OpenSSL, поэтому больше не нужно устанавливать это решение.</span><span class="sxs-lookup"><span data-stu-id="6424c-156">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span> 

## <a name="api-changes-and-library-support"></a><span data-ttu-id="6424c-157">Изменения в API и поддержка библиотек</span><span class="sxs-lookup"><span data-stu-id="6424c-157">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="6424c-158">Поддержка .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="6424c-158">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="6424c-159">.NET Standard определяет набор интерфейсов API с несколькими версиями, которые должны быть доступны в реализациях .NET, соответствующие версии Standard.</span><span class="sxs-lookup"><span data-stu-id="6424c-159">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="6424c-160">Решение .NET Standard ориентировано на разработчиков библиотек.</span><span class="sxs-lookup"><span data-stu-id="6424c-160">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="6424c-161">Оно предоставляет функции библиотеки, предназначенной для версии .NET Standard в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="6424c-161">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="6424c-162">.NET Core 1.x поддерживает .NET Standard версии 1.6, .NET Core 2.0 поддерживает последнюю версию, .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6424c-162">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="6424c-163">Дополнительные сведения см. в статье [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="6424c-163">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="6424c-164">.NET Standard 2.0 содержит более 20 000 интерфейсов API, доступных в .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="6424c-164">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="6424c-165">Такое разнообразие является результатом включения в .NET Standard интерфейсов API, стандартных для .NET Framework и Xamarin.</span><span class="sxs-lookup"><span data-stu-id="6424c-165">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="6424c-166">Библиотеки классов .NET Standard 2.0 также могут ссылаться на библиотеки классов .NET Framework, при условии, что они вызывают API-интерфейсы, которые есть в .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6424c-166">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="6424c-167">Повторная компиляция библиотек .NET Framework не требуется.</span><span class="sxs-lookup"><span data-stu-id="6424c-167">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="6424c-168">Список интерфейсов API, добавленных в .NET Standard с момента выхода последней версии, .NET Standard 1.6, см. в сравнительном документе [.NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="6424c-168">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="6424c-169">Увеличение количества компонентов</span><span class="sxs-lookup"><span data-stu-id="6424c-169">Expanded surface area</span></span>

<span data-ttu-id="6424c-170">Общее количество API-интерфейсов, доступных в .NET Core 2.0, удвоилось по сравнению с .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="6424c-170">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span> 

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="6424c-171">Поддержка библиотек .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6424c-171">Support for .NET Framework libraries</span></span>

<span data-ttu-id="6424c-172">Код .NET Core может ссылаться на имеющиеся библиотеки .NET Framework, включая имеющиеся пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="6424c-172">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="6424c-173">Обратите внимание, что библиотеки должны использовать интерфейсы API из .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6424c-173">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="6424c-174">интеграция Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6424c-174">Visual Studio integration</span></span>

<span data-ttu-id="6424c-175">В Visual Studio 2017 версии 15.3 (в некоторых случаях, в Visual Studio для Mac) внесены значительные улучшения для разработчиков .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6424c-175">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="6424c-176">Изменение целевой платформы приложений .NET Core и библиотек .NET Standard</span><span class="sxs-lookup"><span data-stu-id="6424c-176">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="6424c-177">Если установлен пакет SDK для .NET Core 2.0, можно изменить целевую платформу проектов .NET Core 1.x на .NET Core 2.0, а библиотек .NET Standard 1.x — на .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6424c-177">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span> 

<span data-ttu-id="6424c-178">Чтобы изменить целевую платформу проекта в Visual Studio, в диалоговом окне свойств проекта откройте вкладку **Приложение** и измените значение **целевой платформы** на **.NET Core 2.0** или **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="6424c-178">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="6424c-179">Ее также можно изменить, щелкнув проект правой кнопкой мыши и выбрав пункты **Изменить \*CSPROJ-файл**.</span><span class="sxs-lookup"><span data-stu-id="6424c-179">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="6424c-180">Дополнительные сведения см. в разделе [Инструментарий](#tooling) выше.</span><span class="sxs-lookup"><span data-stu-id="6424c-180">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="6424c-181">Поддержка динамического модульного тестирования для .NET Core</span><span class="sxs-lookup"><span data-stu-id="6424c-181">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="6424c-182">При изменении кода функция Live Unit Testing автоматически запускает все затронутые модульные тесты в фоновом режиме и отображает результаты и объем протестированного кода в активном состоянии в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6424c-182">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="6424c-183">Теперь .NET Core 2.0 поддерживает функцию Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="6424c-183">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="6424c-184">Ранее функция Live Unit Testing была доступна только для приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6424c-184">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span> 

<span data-ttu-id="6424c-185">Дополнительные сведения см. в статье [Функция Live Unit Testing в Visual Studio 2017](/visualstudio/test/live-unit-testing) и [Часто задаваемые вопросы о функции Live Unit Testing](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="6424c-185">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="6424c-186">Улучшенная поддержка нескольких целевых платформ</span><span class="sxs-lookup"><span data-stu-id="6424c-186">Better support for multiple target frameworks</span></span>

<span data-ttu-id="6424c-187">При создании проекта для различных целевых платформ теперь целевую платформу можно выбрать в меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="6424c-187">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="6424c-188">На следующем рисунке показано, что целевой платформой проекта SCD1 является 64-разрядная Mac OS X 10.11 (`osx.10.11-x64`) и 64-разрядная Windows 10 и Windows Server 2016 (`win10-x64`).</span><span class="sxs-lookup"><span data-stu-id="6424c-188">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="6424c-189">Целевую платформу можно выбрать, прежде чем нажать кнопку проекта (в этом случае — для выполнения отладочной сборки).</span><span class="sxs-lookup"><span data-stu-id="6424c-189">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Выбор целевой платформы при создании проекта](media/multitarget.png) 

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="6424c-191">Поддержка параллельного выполнения для пакетов SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="6424c-191">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="6424c-192">Теперь пакет SDK для .NET Core можно установить отдельно от Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6424c-192">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="6424c-193">Таким образом в одной версии Visual Studio можно создавать проекты, предназначенные для разных версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6424c-193">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="6424c-194">Ранее Visual Studio и пакет SDK для .NET Core были тесно связаны. Конкретная версия пакета SDK использовалась для конкретной версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6424c-194">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="6424c-195">Усовершенствования документации</span><span class="sxs-lookup"><span data-stu-id="6424c-195">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="6424c-196">Архитектура приложений .NET</span><span class="sxs-lookup"><span data-stu-id="6424c-196">.NET Application Architecture</span></span>

<span data-ttu-id="6424c-197">Благодаря [архитектуре приложений .NET](https://www.microsoft.com/net/learn/architecture) вы получаете доступ к набору электронных книг, в которых представлены инструкции, рекомендации и примеры приложений при использовании .NET для сборки:</span><span class="sxs-lookup"><span data-stu-id="6424c-197">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of eBooks that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="6424c-198">микрослужбы и контейнеры Docker;</span><span class="sxs-lookup"><span data-stu-id="6424c-198">Microservices and Docker containers.</span></span>
- <span data-ttu-id="6424c-199">веб-приложения с ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="6424c-199">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="6424c-200">мобильные приложения с Xamarin;</span><span class="sxs-lookup"><span data-stu-id="6424c-200">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="6424c-201">приложения, развертываемые в облаке с помощью Azure.</span><span class="sxs-lookup"><span data-stu-id="6424c-201">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="6424c-202">См. также</span><span class="sxs-lookup"><span data-stu-id="6424c-202">See also</span></span>
 <span data-ttu-id="6424c-203">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Новые возможности ASP.NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="6424c-203">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)</span></span>

