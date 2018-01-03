---
title: "Новые возможности .NET Core 2.0"
description: "Дополнительные сведения о новых возможностях .NET Core."
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 749f0502b5c80ed3d6b81d2036e7591e3f1fe08a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="2f1cd-104">Новые возможности .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f1cd-104">What's new in .NET Core</span></span>

<span data-ttu-id="2f1cd-105">В .NET Core 2.0 представлены следующие улучшения и новые возможности:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- <span data-ttu-id="2f1cd-106">[инструментарий](#tooling);</span><span class="sxs-lookup"><span data-stu-id="2f1cd-106">[Tooling](#tooling)</span></span>
- <span data-ttu-id="2f1cd-107">[языковая поддержка](#language-support);</span><span class="sxs-lookup"><span data-stu-id="2f1cd-107">[Language support](#language-support)</span></span>
- <span data-ttu-id="2f1cd-108">[улучшения платформы](#platform-improvements);</span><span class="sxs-lookup"><span data-stu-id="2f1cd-108">[Platform improvements](#platform-improvements)</span></span>
- <span data-ttu-id="2f1cd-109">[изменения API](#api-changes-and-library-support);</span><span class="sxs-lookup"><span data-stu-id="2f1cd-109">[API changes](#api-changes-and-library-support)</span></span>
- <span data-ttu-id="2f1cd-110">[интеграция Visual Studio](#visual-studio-integration);</span><span class="sxs-lookup"><span data-stu-id="2f1cd-110">[Visual Studio integration](#visual-studio-integration)</span></span>
- <span data-ttu-id="2f1cd-111">[усовершенствования документации](#documentation-improvements).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-111">[Documentation improvements](#documentation-improvements)</span></span>

## <a name="tooling"></a><span data-ttu-id="2f1cd-112">Инструментарий</span><span class="sxs-lookup"><span data-stu-id="2f1cd-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="2f1cd-113">Явное выполнение команды dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2f1cd-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="2f1cd-114">В предыдущих версиях .NET Core сразу после создания проекта с помощью команды [dotnet new](../tools/dotnet-new.md), а также после добавления новой зависимости в проект требовалось выполнять команду [dotnet restore](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2f1cd-115">Вы также можете отключить автоматический вызов команды `dotnet restore`. Для этого передайте параметр `--no-restore` команде `new`, `run`, `build`, `publish`, `pack` и `test`.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-115">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="2f1cd-116">Изменение целевой платформы на .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f1cd-116">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="2f1cd-117">Если установлен пакет SDK для .NET Core 2.0, для проектов, предназначенных для .NET Core 1.x, можно изменить целевую платформу на .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-117">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="2f1cd-118">Чтобы изменить целевую платформу на .NET Core 2.0, измените файл проекта. Для этого измените значение элемента `<TargetFramework>` или `<TargetFrameworks>` (при наличии нескольких целевых платформ в файле проекта) с 1.x на 2.0:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-118">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="2f1cd-119">Кроме того, можно также выполнить перенацеливание с библиотек .NET Standard на .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-119">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="2f1cd-120">Дополнительные сведения о переносе проекта в .NET Core 2.0 см. в статье [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Переход с ASP.NET Core 1.x на ASP.NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-120">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="2f1cd-121">Языковая поддержка</span><span class="sxs-lookup"><span data-stu-id="2f1cd-121">Language support</span></span>

<span data-ttu-id="2f1cd-122">Помимо поддержки C# и F # .NET Core 2.0 также поддерживает Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-122">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="2f1cd-123">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f1cd-123">Visual Basic</span></span>

<span data-ttu-id="2f1cd-124">.NET Core версии 2.0 теперь поддерживает Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-124">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="2f1cd-125">С помощью Visual Basic можно создать следующие типы проектов:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-125">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="2f1cd-126">консольные приложения .NET Core;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-126">.NET Core console apps</span></span>
- <span data-ttu-id="2f1cd-127">библиотеки классов .NET Core;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-127">.NET Core class libraries</span></span>
- <span data-ttu-id="2f1cd-128">библиотеки классов .NET Standard;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-128">.NET Standard class libraries</span></span>
- <span data-ttu-id="2f1cd-129">проекты модульных тестов .NET Core;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-129">.NET Core unit test projects</span></span>
- <span data-ttu-id="2f1cd-130">тестовые проекты xUnit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-130">.NET Core xUnit test projects</span></span>

<span data-ttu-id="2f1cd-131">Например, для создания приложения Visual Basic Hello World в командной строке сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-131">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="2f1cd-132">Откройте окно консоли, создайте каталог для проекта и выберите его в качестве текущего.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-132">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="2f1cd-133">Введите команду `dotnet new console -lang vb`.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-133">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="2f1cd-134">Команда создает файл проекта с расширением `.vbproj`, а также файл исходного кода Visual Basic *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-134">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="2f1cd-135">Этот файл содержит исходный код для записи строки Hello World!</span><span class="sxs-lookup"><span data-stu-id="2f1cd-135">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="2f1cd-136">в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-136">to the console window.</span></span>

1.  <span data-ttu-id="2f1cd-137">Введите команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-137">Enter the command `dotnet run`.</span></span> <span data-ttu-id="2f1cd-138">[Средства интерфейса командной строки .NET Core](../tools/index.md) автоматически компилируют и выполняют приложение, которое выводит сообщение Hello World!</span><span class="sxs-lookup"><span data-stu-id="2f1cd-138">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="2f1cd-139">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-139">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="2f1cd-140">Поддержка C# 7.1</span><span class="sxs-lookup"><span data-stu-id="2f1cd-140">Support for C# 7.1</span></span>

<span data-ttu-id="2f1cd-141">.NET Core 2.0 поддерживает C# 7.1, в котором реализованы новые возможности, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-141">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="2f1cd-142">Метод `Main`, точку входа приложения можно пометить с помощью ключевого слова [async](../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-142">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="2f1cd-143">Выводимые имена кортежей.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-143">Inferred tuple names.</span></span>
- <span data-ttu-id="2f1cd-144">Стандартные выражения.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-144">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="2f1cd-145">Улучшения платформы</span><span class="sxs-lookup"><span data-stu-id="2f1cd-145">Platform improvements</span></span>

<span data-ttu-id="2f1cd-146">В .NET Core 2.0 представлены возможности, упрощающие установку платформы .NET Core и ее использование в поддерживаемых операционных системах.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-146">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="2f1cd-147">Единая реализация .NET Core для Linux</span><span class="sxs-lookup"><span data-stu-id="2f1cd-147">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="2f1cd-148">.NET Core 2.0 предлагает единую реализацию Linux, которую можно использовать в нескольких дистрибутивах Linux.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-148">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="2f1cd-149">Для .NET Core 1.x требовалось, чтобы вы загрузили реализацию Linux для конкретного дистрибутива.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-149">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="2f1cd-150">Кроме того, предусмотрена возможность разработки приложений, предназначенных исключительно для ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-150">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="2f1cd-151">В .NET Core 1.x требовалось выбирать целевую среду для каждого дистрибутива Linux отдельно.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-151">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="2f1cd-152">Поддержка библиотек шифрования Apple</span><span class="sxs-lookup"><span data-stu-id="2f1cd-152">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="2f1cd-153">В .NET Core 1.x на macOS требовалась библиотека шифрования для набора средств OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-153">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="2f1cd-154">.NET Core 2.0 использует библиотеки шифрования Apple и не требует OpenSSL, поэтому больше не нужно устанавливать это решение.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-154">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="2f1cd-155">Изменения в API и поддержка библиотек</span><span class="sxs-lookup"><span data-stu-id="2f1cd-155">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="2f1cd-156">Поддержка .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="2f1cd-156">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="2f1cd-157">.NET Standard определяет набор интерфейсов API с несколькими версиями, которые должны быть доступны в реализациях .NET, соответствующие версии Standard.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-157">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="2f1cd-158">Решение .NET Standard ориентировано на разработчиков библиотек.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-158">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="2f1cd-159">Оно предоставляет функции библиотеки, предназначенной для версии .NET Standard в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-159">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="2f1cd-160">.NET Core 1.x поддерживает .NET Standard версии 1.6, .NET Core 2.0 поддерживает последнюю версию, .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-160">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="2f1cd-161">Дополнительные сведения см. в статье [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-161">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="2f1cd-162">.NET Standard 2.0 содержит более 20 000 интерфейсов API, доступных в .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-162">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="2f1cd-163">Такое разнообразие является результатом включения в .NET Standard интерфейсов API, стандартных для .NET Framework и Xamarin.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-163">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="2f1cd-164">Библиотеки классов .NET Standard 2.0 также могут ссылаться на библиотеки классов .NET Framework, при условии, что они вызывают API-интерфейсы, которые есть в .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-164">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="2f1cd-165">Повторная компиляция библиотек .NET Framework не требуется.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-165">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="2f1cd-166">Список интерфейсов API, добавленных в .NET Standard с момента выхода последней версии, .NET Standard 1.6, см. в сравнительном документе [.NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-166">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="2f1cd-167">Увеличение количества компонентов</span><span class="sxs-lookup"><span data-stu-id="2f1cd-167">Expanded surface area</span></span>

<span data-ttu-id="2f1cd-168">Общее количество API-интерфейсов, доступных в .NET Core 2.0, удвоилось по сравнению с .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-168">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="2f1cd-169">[Пакет обеспечения совместимости Windows](../porting/windows-compat-pack.md) существенно упрощает перенос из .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-169">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="2f1cd-170">Поддержка библиотек .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f1cd-170">Support for .NET Framework libraries</span></span>

<span data-ttu-id="2f1cd-171">Код .NET Core может ссылаться на имеющиеся библиотеки .NET Framework, включая имеющиеся пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-171">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="2f1cd-172">Обратите внимание, что библиотеки должны использовать интерфейсы API из .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-172">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="2f1cd-173">интеграция Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2f1cd-173">Visual Studio integration</span></span>

<span data-ttu-id="2f1cd-174">В Visual Studio 2017 версии 15.3 (в некоторых случаях, в Visual Studio для Mac) внесены значительные улучшения для разработчиков .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-174">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="2f1cd-175">Изменение целевой платформы приложений .NET Core и библиотек .NET Standard</span><span class="sxs-lookup"><span data-stu-id="2f1cd-175">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="2f1cd-176">Если установлен пакет SDK для .NET Core 2.0, можно изменить целевую платформу проектов .NET Core 1.x на .NET Core 2.0, а библиотек .NET Standard 1.x — на .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-176">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="2f1cd-177">Чтобы изменить целевую платформу проекта в Visual Studio, в диалоговом окне свойств проекта откройте вкладку **Приложение** и измените значение **целевой платформы** на **.NET Core 2.0** или **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-177">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="2f1cd-178">Ее также можно изменить, щелкнув проект правой кнопкой мыши и выбрав пункты **Изменить \*CSPROJ-файл**.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-178">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="2f1cd-179">Дополнительные сведения см. в разделе [Инструментарий](#tooling) выше.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-179">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="2f1cd-180">Поддержка динамического модульного тестирования для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f1cd-180">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="2f1cd-181">При изменении кода функция Live Unit Testing автоматически запускает все затронутые модульные тесты в фоновом режиме и отображает результаты и объем протестированного кода в активном состоянии в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-181">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="2f1cd-182">Теперь .NET Core 2.0 поддерживает функцию Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-182">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="2f1cd-183">Ранее функция Live Unit Testing была доступна только для приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-183">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="2f1cd-184">Дополнительные сведения см. в статье [Функция Live Unit Testing в Visual Studio 2017](/visualstudio/test/live-unit-testing) и [Часто задаваемые вопросы о функции Live Unit Testing](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-184">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="2f1cd-185">Улучшенная поддержка нескольких целевых платформ</span><span class="sxs-lookup"><span data-stu-id="2f1cd-185">Better support for multiple target frameworks</span></span>

<span data-ttu-id="2f1cd-186">При создании проекта для различных целевых платформ теперь целевую платформу можно выбрать в меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-186">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="2f1cd-187">На следующем рисунке показано, что целевой платформой проекта SCD1 является 64-разрядная Mac OS X 10.11 (`osx.10.11-x64`) и 64-разрядная Windows 10 и Windows Server 2016 (`win10-x64`).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-187">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="2f1cd-188">Целевую платформу можно выбрать, прежде чем нажать кнопку проекта (в этом случае — для выполнения отладочной сборки).</span><span class="sxs-lookup"><span data-stu-id="2f1cd-188">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Выбор целевой платформы при создании проекта](media/multitarget.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="2f1cd-190">Поддержка параллельного выполнения для пакетов SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f1cd-190">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="2f1cd-191">Теперь пакет SDK для .NET Core можно установить отдельно от Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-191">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="2f1cd-192">Таким образом в одной версии Visual Studio можно создавать проекты, предназначенные для разных версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-192">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="2f1cd-193">Ранее Visual Studio и пакет SDK для .NET Core были тесно связаны. Конкретная версия пакета SDK использовалась для конкретной версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-193">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="2f1cd-194">Усовершенствования документации</span><span class="sxs-lookup"><span data-stu-id="2f1cd-194">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="2f1cd-195">Архитектура приложений .NET</span><span class="sxs-lookup"><span data-stu-id="2f1cd-195">.NET Application Architecture</span></span>

<span data-ttu-id="2f1cd-196">Благодаря [архитектуре приложений .NET](https://www.microsoft.com/net/learn/architecture) вы получаете доступ к набору электронных книг, в которых представлены инструкции, рекомендации и примеры приложений при использовании .NET для сборки:</span><span class="sxs-lookup"><span data-stu-id="2f1cd-196">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="2f1cd-197">микрослужбы и контейнеры Docker;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-197">Microservices and Docker containers.</span></span>
- <span data-ttu-id="2f1cd-198">веб-приложения с ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-198">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="2f1cd-199">мобильные приложения с Xamarin;</span><span class="sxs-lookup"><span data-stu-id="2f1cd-199">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="2f1cd-200">приложения, развертываемые в облаке с помощью Azure.</span><span class="sxs-lookup"><span data-stu-id="2f1cd-200">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f1cd-201">См. также</span><span class="sxs-lookup"><span data-stu-id="2f1cd-201">See also</span></span>
 <span data-ttu-id="2f1cd-202">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Новые возможности ASP.NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="2f1cd-202">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)</span></span>
