---
title: Новые возможности .NET Core 3.0
description: Дополнительные сведения о новых возможностях .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 6e85c2c3e796ae59a13f944bd4913e4b7316c56a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397827"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="50627-103">Новые возможности .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="50627-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="50627-104">В этой статье описываются новые возможности в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="50627-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="50627-105">Одно из основных усовершенствований — это поддержка классических приложений Windows (только Windows).</span><span class="sxs-lookup"><span data-stu-id="50627-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="50627-106">С помощью пакета SDK для .NET Core 3.0 под названием Windows Desktop можно переносить приложения Windows Forms и Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="50627-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="50627-107">Следует уточнить, что компонент Windows Desktop поддерживается и включен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="50627-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="50627-108">Дополнительные сведения см. далее в этой статье, в разделе [Рабочий стол Windows](#windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="50627-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="50627-109">В .NET Core 3.0 добавлена поддержка C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="50627-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="50627-110">Настоятельно рекомендуется использовать [Visual Studio 2019 версии 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) или более поздней, [Visual Studio для Mac 8.3](/visualstudio/mac/install-preview) или более поздней или [Visual Studio Code](https://code.visualstudio.com/) с последним **расширением C#** .</span><span class="sxs-lookup"><span data-stu-id="50627-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="50627-111">[Скачайте .NET Core 3.0 и начните работу](https://aka.ms/netcore3download) прямо сейчас в Windows, macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="50627-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="50627-112">Дополнительные сведения см. в [объявлении о выпуске .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="50627-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="50627-113">Релиз-кандидат 1 .NET Core считался корпорацией Майкрософт готовым к эксплуатации и полностью поддерживался.</span><span class="sxs-lookup"><span data-stu-id="50627-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="50627-114">Если вы используете предварительную версию, необходимо перейти на версию RTM, чтобы продолжать получать поддержку.</span><span class="sxs-lookup"><span data-stu-id="50627-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="50627-115">Улучшения C# 8.0</span><span class="sxs-lookup"><span data-stu-id="50627-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="50627-116">В этот выпуск также входит версия C# 8.0, в которой появились [ссылочные типы, допускающие значение NULL](../../csharp/tutorials/nullable-reference-types.md), [асинхронные потоки](../../csharp/tutorials/generate-consume-asynchronous-stream.md) и [другие возможности](../../csharp/tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="50627-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="50627-117">Дополнительные сведения о функциях C# 8.0 см. в разделе [Новые возможности C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="50627-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="50627-118">Добавлены улучшения языка для поддержки следующих функций API:</span><span class="sxs-lookup"><span data-stu-id="50627-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="50627-119">Диапазоны и индексы</span><span class="sxs-lookup"><span data-stu-id="50627-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="50627-120">Асинхронные потоки</span><span class="sxs-lookup"><span data-stu-id="50627-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="50627-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="50627-121">.NET Standard 2.1</span></span>

<span data-ttu-id="50627-122">.NET Core 3.0 реализует **.NET Standard 2.1**.</span><span class="sxs-lookup"><span data-stu-id="50627-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="50627-123">При этом шаблон `dotnet new classlib` по умолчанию создает проект, который по-прежнему предназначен для **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="50627-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="50627-124">Чтобы создать проект для **.NET Standard 2.1**, откройте файл проекта и измените значение свойства `TargetFramework` на `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="50627-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="50627-125">Если вы используете Visual Studio, у вас должна быть версия [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), так как Visual Studio 2017 не поддерживает **.NET Standard 2.1** или **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="50627-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="50627-126">Компиляция и развертывание</span><span class="sxs-lookup"><span data-stu-id="50627-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="50627-127">Исполняемые файлы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="50627-127">Default executables</span></span>

<span data-ttu-id="50627-128">.NET Core теперь по умолчанию собирает [исполняемые файлы, зависимые от среды выполнения](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="50627-128">.NET Core now builds [runtime-dependent executables](../deploying/index.md#publish-runtime-dependent) by default.</span></span> <span data-ttu-id="50627-129">Такое поведение ново для приложений, которые используют глобально установленную версию .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50627-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="50627-130">Раньше исполняемые файлы создавались только в [автономных развертываниях](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="50627-130">Previously, only [self-contained deployments](../deploying/index.md#publish-self-contained) would produce an executable.</span></span>

<span data-ttu-id="50627-131">Во время выполнения команды `dotnet build` или `dotnet publish` создается исполняемый файл (называемый **appHost**), который соответствует среде и платформе используемого пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="50627-131">During `dotnet build` or `dotnet publish`, an executable (known as the **appHost**) is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="50627-132">Предполагается, что с этими исполняемыми файлами можно выполнять те же действия, что и с другими исполняемыми файлами в машинном коде, например:</span><span class="sxs-lookup"><span data-stu-id="50627-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="50627-133">исполняемый файл можно дважды щелкнуть;</span><span class="sxs-lookup"><span data-stu-id="50627-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="50627-134">приложение можно запустить из командной строки напрямую, например `myapp.exe` в Windows и `./myapp` в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="50627-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="macos-apphost-and-notarization"></a><span data-ttu-id="50627-135">Файл appHost в macOS и заверение</span><span class="sxs-lookup"><span data-stu-id="50627-135">macOS appHost and notarization</span></span>

<span data-ttu-id="50627-136">*Только macOS*</span><span class="sxs-lookup"><span data-stu-id="50627-136">*macOS only*</span></span>

<span data-ttu-id="50627-137">Начиная с заверенного пакета SDK для .NET Core 3.0 для macOS параметр, отвечающий за создание исполняемого файла по умолчанию (называемого appHost), отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50627-137">Starting with the notarized .NET Core SDK 3.0 for macOS, the setting to produce a default executable (known as the appHost) is disabled by default.</span></span> <span data-ttu-id="50627-138">Дополнительные сведения см. в статье [Заверение macOS Catalina и влияние на скачиваемые файлы и проекты .NET Core](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="50627-138">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="50627-139">Если параметр appHost включен, .NET Core создает собственный исполняемый файл Mach-O, когда вы выполняете сборку или публикацию.</span><span class="sxs-lookup"><span data-stu-id="50627-139">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="50627-140">Приложение выполняется в контексте appHost при запуске из исходного кода с помощью команды `dotnet run` или путем непосредственного запуска исполняемого файла Mach-O.</span><span class="sxs-lookup"><span data-stu-id="50627-140">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="50627-141">Без appHost пользователь может запустить приложение, [зависящее от среды выполнения](../deploying/index.md#publish-runtime-dependent), только одним способом — с помощью команды `dotnet <filename.dll>`.</span><span class="sxs-lookup"><span data-stu-id="50627-141">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="50627-142">AppHost всегда создается при публикации приложения в [автономном виде](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="50627-142">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="50627-143">Можно либо настроить appHost на уровне проекта, либо переключить использование appHost для определенной команды `dotnet` с помощью параметра `-p:UseAppHost`:</span><span class="sxs-lookup"><span data-stu-id="50627-143">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="50627-144">Файл проекта</span><span class="sxs-lookup"><span data-stu-id="50627-144">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="50627-145">Параметр командной строки</span><span class="sxs-lookup"><span data-stu-id="50627-145">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="50627-146">Дополнительные сведения о параметре `UseAppHost` см. в разделе [Свойства MSBuild для Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="50627-146">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="50627-147">Однофайловые исполняемые файлы</span><span class="sxs-lookup"><span data-stu-id="50627-147">Single-file executables</span></span>

<span data-ttu-id="50627-148">Команда `dotnet publish` поддерживает упаковку приложения в однофайловый исполняемый файл для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="50627-148">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="50627-149">Исполняемый файл является самоизвлекаемым и содержит все зависимости (включая машинные), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="50627-149">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="50627-150">При первом запуске приложение извлекается в каталог, который зависит от имени и идентификатора сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="50627-150">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="50627-151">Впоследствии запуск происходит быстрее.</span><span class="sxs-lookup"><span data-stu-id="50627-151">Startup is faster when the application is run again.</span></span> <span data-ttu-id="50627-152">Если версия не изменилась, приложению не нужно извлекать себя заново.</span><span class="sxs-lookup"><span data-stu-id="50627-152">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="50627-153">Чтобы опубликовать однофайловый исполняемый файл, задайте `PublishSingleFile` в своем проекте или в командной строке с помощью команды `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="50627-153">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="50627-154">-или-</span><span class="sxs-lookup"><span data-stu-id="50627-154">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="50627-155">Дополнительные сведения о публикации однофайловых исполняемых файлов см. в [документе о разработке однофайловых пакетных установщиков](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="50627-155">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="50627-156">Связывание сборок</span><span class="sxs-lookup"><span data-stu-id="50627-156">Assembly linking</span></span>

<span data-ttu-id="50627-157">Пакет SDK для .NET Core 3.0 содержит инструмент, который позволяет уменьшить размер приложения, анализируя промежуточный язык и устраняя неиспользуемые сборки.</span><span class="sxs-lookup"><span data-stu-id="50627-157">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="50627-158">Автономные приложения включают все необходимое для выполнения кода. Это позволяет не устанавливать .NET на соответствующем компьютере.</span><span class="sxs-lookup"><span data-stu-id="50627-158">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="50627-159">Но во многих случаях для работы приложения достаточно небольшого набора функций платформы, а все неиспользуемые библиотеки можно удалить.</span><span class="sxs-lookup"><span data-stu-id="50627-159">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="50627-160">Теперь .NET Core предоставляет параметр, который позволяет использовать [компоновщик IL](https://github.com/mono/linker) для сканирования кода приложения на промежуточном языке.</span><span class="sxs-lookup"><span data-stu-id="50627-160">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="50627-161">Это средство отслеживает необходимый код, а затем удаляет все неиспользуемые библиотеки.</span><span class="sxs-lookup"><span data-stu-id="50627-161">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="50627-162">Это позволяет значительно снизить размер развертывания для некоторых приложений.</span><span class="sxs-lookup"><span data-stu-id="50627-162">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="50627-163">Чтобы включить этот инструмент, укажите в проекте параметр `<PublishTrimmed>` и опубликуйте автономное приложение:</span><span class="sxs-lookup"><span data-stu-id="50627-163">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="50627-164">Например, простейший шаблон консольного приложения hello world, который входит в стандартную поставку, при публикации достигает размера около 70 МБ.</span><span class="sxs-lookup"><span data-stu-id="50627-164">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="50627-165">С помощью `<PublishTrimmed>` этот размер можно снизить до 30 МБ.</span><span class="sxs-lookup"><span data-stu-id="50627-165">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="50627-166">Важно учитывать, что приложения и платформы (в том числе ASP.NET Core и WPF), которые используют отражение или связанные динамические функции, могут стать неработоспособными после обрезки.</span><span class="sxs-lookup"><span data-stu-id="50627-166">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="50627-167">Такие нарушения возникают потому, что компоновщик ничего не знает о динамическом поведении и не может определить, какие типы платформы потребуются для отражения.</span><span class="sxs-lookup"><span data-stu-id="50627-167">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="50627-168">Но вы можете настроить компоновщик IL так, чтобы он учитывал этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="50627-168">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="50627-169">В любом случае обязательно протестируйте приложение после обрезки.</span><span class="sxs-lookup"><span data-stu-id="50627-169">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="50627-170">Дополнительные сведения о компоновщике IL вы найдете в [этой документации](https://aka.ms/dotnet-illink) или на страницах репозитория [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="50627-170">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="50627-171">Многоуровневая компиляция</span><span class="sxs-lookup"><span data-stu-id="50627-171">Tiered compilation</span></span>

<span data-ttu-id="50627-172">[Многоуровневая компиляция](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (МК) по умолчанию входит только в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="50627-172">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="50627-173">Эта функция позволяет среде выполнения более адаптивно использовать компилятор JIT для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="50627-173">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="50627-174">Основное преимущество многоуровневой компиляции состоит в том, что она обеспечивает два типа методов JIT: более качественные, но при этом более медленные, или менее качественные, но более быстрые.</span><span class="sxs-lookup"><span data-stu-id="50627-174">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="50627-175">Качество определяет то, насколько хорошо оптимизирован метод.</span><span class="sxs-lookup"><span data-stu-id="50627-175">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="50627-176">Многоуровневая компиляция позволяет повысить производительность приложения на разных этапах его выполнения: с первого запуска и до достижения стабильной работы.</span><span class="sxs-lookup"><span data-stu-id="50627-176">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="50627-177">Если же многоуровневая компиляция отключена, каждый метод компилируется одним и тем же способом с упором на стабильную работу, а не скорость запуска.</span><span class="sxs-lookup"><span data-stu-id="50627-177">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="50627-178">Когда многоуровневая компиляция включена, при запуске приложения компиляция методов происходит описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="50627-178">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="50627-179">Если метод имеет скомпилированный в режиме Ahead Of Time код ([ReadyToRun](#readytorun-images)), используется предварительно сформированный код.</span><span class="sxs-lookup"><span data-stu-id="50627-179">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="50627-180">В противном случае производится JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="50627-180">Otherwise, the method is jitted.</span></span> <span data-ttu-id="50627-181">Как правило, эти методы являются универсальными для типов значений.</span><span class="sxs-lookup"><span data-stu-id="50627-181">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="50627-182">*Быстрая JIT-компиляция* позволяет быстрее создавать код с более низким качеством (менее оптимизированный).</span><span class="sxs-lookup"><span data-stu-id="50627-182">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="50627-183">В .NET Core 3.0 быстрая JIT-компиляция по умолчанию включена для методов, которые не содержат циклов, и является предпочтительной при запуске.</span><span class="sxs-lookup"><span data-stu-id="50627-183">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="50627-184">JIT-компиляция с полной оптимизацией позволяет создать высококачественный (более оптимизированный) код. Но на это уходит больше времени.</span><span class="sxs-lookup"><span data-stu-id="50627-184">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="50627-185">Для методов, где не применяется быстрая JIT-компиляция (например, если метод имеет атрибут <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), используется JIT-компиляция с полной оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="50627-185">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="50627-186">Для часто вызываемых методов JIT-компилятор в конечном итоге создает полностью оптимизированный код в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="50627-186">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="50627-187">После этого оптимизированный код заменяет предварительно скомпилированный код для данного метода.</span><span class="sxs-lookup"><span data-stu-id="50627-187">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="50627-188">Код, созданный быстрой JIT-компиляцией, может выполняться медленнее, выделять больше памяти или использовать больше пространства стека.</span><span class="sxs-lookup"><span data-stu-id="50627-188">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="50627-189">При возникновении проблем быструю JIT-компиляцию можно отключить с помощью следующего свойства MSBuild в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="50627-189">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="50627-190">Чтобы полностью отключить многоуровневую компиляцию, добавьте в файл проекта следующее свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="50627-190">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="50627-191">При внесении изменений в эти параметры в файле проекта может потребоваться выполнить чистую сборку, чтобы они вступили в силу (удалите каталоги `obj` и `bin` и перестройте проект).</span><span class="sxs-lookup"><span data-stu-id="50627-191">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="50627-192">Дополнительные сведения о настройке компиляции во время выполнения см. в статье [Параметры конфигурации времени выполнения для компиляции](../run-time-config/compilation.md).</span><span class="sxs-lookup"><span data-stu-id="50627-192">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="50627-193">Образы ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="50627-193">ReadyToRun images</span></span>

<span data-ttu-id="50627-194">Вы можете снизить время запуска приложения .NET Core, скомпилировав все сборки приложения в формат ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="50627-194">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="50627-195">R2R является разновидностью компиляции AOT.</span><span class="sxs-lookup"><span data-stu-id="50627-195">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="50627-196">Бинарные файлы R2R повышают производительность при запуске, снижая объем работы, выполняемой на этом этапе компилятором JIT.</span><span class="sxs-lookup"><span data-stu-id="50627-196">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="50627-197">Бинарные файлы содержат такой же машинный код, который создается компилятором JIT.</span><span class="sxs-lookup"><span data-stu-id="50627-197">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="50627-198">Но бинарные файлы R2R имеют больший размер, так как содержат не только код на промежуточном языке (IL), который по-прежнему необходим для некоторых сценариев, но и версию того же кода на машинном языке.</span><span class="sxs-lookup"><span data-stu-id="50627-198">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="50627-199">Функция R2R доступна только при публикации автономного приложения, предназначенного для конкретной среды выполнения (RID), например для Windows x64 или Linux x64.</span><span class="sxs-lookup"><span data-stu-id="50627-199">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="50627-200">Чтобы скомпилировать проект как ReadyToRun, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="50627-200">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="50627-201">Добавьте в проект параметр `<PublishReadyToRun>`:</span><span class="sxs-lookup"><span data-stu-id="50627-201">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="50627-202">Опубликуйте автономное приложение.</span><span class="sxs-lookup"><span data-stu-id="50627-202">Publish a self-contained app.</span></span> <span data-ttu-id="50627-203">Например, такая команда создает автономное приложение для 64-разрядной версии Windows:</span><span class="sxs-lookup"><span data-stu-id="50627-203">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="50627-204">Ограничения при работе с несколькими платформами и архитектурами</span><span class="sxs-lookup"><span data-stu-id="50627-204">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="50627-205">Компилятор ReadyToRun пока не поддерживает перекрестное нацеливание.</span><span class="sxs-lookup"><span data-stu-id="50627-205">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="50627-206">Компиляцию необходимо выполнять в конкретной целевой среде.</span><span class="sxs-lookup"><span data-stu-id="50627-206">You must compile on a given target.</span></span> <span data-ttu-id="50627-207">Например, если вам нужен образ R2R для 64-разрядной ОС Windows, команду публикации следует выполнять именно в этой среде.</span><span class="sxs-lookup"><span data-stu-id="50627-207">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="50627-208">Исключения для кроссплатформенного таргетирования:</span><span class="sxs-lookup"><span data-stu-id="50627-208">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="50627-209">можно использовать Windows x64 для компиляции образов Windows ARM32, ARM64 и x86;</span><span class="sxs-lookup"><span data-stu-id="50627-209">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="50627-210">можно использовать Windows x86 для компиляции образов Windows ARM32;</span><span class="sxs-lookup"><span data-stu-id="50627-210">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="50627-211">можно использовать Linux x64 для компиляции образов Linux ARM32 и ARM64.</span><span class="sxs-lookup"><span data-stu-id="50627-211">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="50627-212">Среда выполнения и пакет SDK</span><span class="sxs-lookup"><span data-stu-id="50627-212">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="50627-213">Накат основной версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="50627-213">Major-version runtime roll forward</span></span>

<span data-ttu-id="50627-214">В .NET Core 3.0 появилась функция согласия, которая позволяет приложению выполнять накат до последней основной версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50627-214">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="50627-215">Кроме того, добавлен новый параметр для управления тем, как накат применяется к приложению.</span><span class="sxs-lookup"><span data-stu-id="50627-215">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="50627-216">Его можно настроить одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="50627-216">This can be configured in the following ways:</span></span>

- <span data-ttu-id="50627-217">Свойство файла проекта: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="50627-217">Project file property: `RollForward`</span></span>
- <span data-ttu-id="50627-218">Свойство файла конфигурации среды выполнения: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="50627-218">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="50627-219">Переменная среды: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="50627-219">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="50627-220">Аргумент командной строки: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="50627-220">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="50627-221">Необходимо указать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="50627-221">One of the following values must be specified.</span></span> <span data-ttu-id="50627-222">Если параметр не указан, ему по умолчанию присваивается значение **Minor**.</span><span class="sxs-lookup"><span data-stu-id="50627-222">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="50627-223">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="50627-223">**LatestPatch**</span></span>\
<span data-ttu-id="50627-224">Накат до версии с наибольшим номером исправления.</span><span class="sxs-lookup"><span data-stu-id="50627-224">Roll forward to the highest patch version.</span></span> <span data-ttu-id="50627-225">Отключает накат дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="50627-225">This disables minor version roll forward.</span></span>
- <span data-ttu-id="50627-226">**Minor**</span><span class="sxs-lookup"><span data-stu-id="50627-226">**Minor**</span></span>\
<span data-ttu-id="50627-227">Накат до дополнительной версии со следующим по порядку возрастания номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50627-227">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="50627-228">Если запрошенная дополнительная версия присутствует, используется политика **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="50627-228">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="50627-229">**Major**</span><span class="sxs-lookup"><span data-stu-id="50627-229">**Major**</span></span>\
<span data-ttu-id="50627-230">Накат до основной версии со следующим по порядку возрастания или дополнительной версии с наименьшим номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50627-230">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="50627-231">Если запрошенная основная версия присутствует, используется политика **Minor**.</span><span class="sxs-lookup"><span data-stu-id="50627-231">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="50627-232">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="50627-232">**LatestMinor**</span></span>\
<span data-ttu-id="50627-233">Накат до дополнительной версии с наибольшим номером, даже если запрошенная дополнительная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="50627-233">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="50627-234">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="50627-234">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="50627-235">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="50627-235">**LatestMajor**</span></span>\
<span data-ttu-id="50627-236">Накат до основной версии с наибольшим номером и дополнительной версии с наибольшим номером, даже если запрошенная основная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="50627-236">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="50627-237">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="50627-237">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="50627-238">**Disable**</span><span class="sxs-lookup"><span data-stu-id="50627-238">**Disable**</span></span>\
<span data-ttu-id="50627-239">Накат не выполняется.</span><span class="sxs-lookup"><span data-stu-id="50627-239">Don't roll forward.</span></span> <span data-ttu-id="50627-240">Привязка только к указанной версии.</span><span class="sxs-lookup"><span data-stu-id="50627-240">Only bind to specified version.</span></span> <span data-ttu-id="50627-241">Эта политика не рекомендуется для общего использования, поскольку отключает возможность наката до последних исправлений.</span><span class="sxs-lookup"><span data-stu-id="50627-241">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="50627-242">Это значение рекомендуется использовать только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="50627-242">This value is only recommended for testing.</span></span>

<span data-ttu-id="50627-243">Все параметры, кроме параметра **Disable**, будут использовать версию с последним доступным исправлением.</span><span class="sxs-lookup"><span data-stu-id="50627-243">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="50627-244">Сборка копирует зависимости</span><span class="sxs-lookup"><span data-stu-id="50627-244">Build copies dependencies</span></span>

<span data-ttu-id="50627-245">Команда `dotnet build` копирует зависимости NuGet для вашего приложения из кэша NuGet в выходную папку сборки.</span><span class="sxs-lookup"><span data-stu-id="50627-245">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="50627-246">Ранее зависимости копировались только в рамках выполнения команды `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="50627-246">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="50627-247">Для некоторых операций, таких как связывание и публикация страницы Razor, по-прежнему будет требоваться публикация.</span><span class="sxs-lookup"><span data-stu-id="50627-247">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="50627-248">Локальные средства</span><span class="sxs-lookup"><span data-stu-id="50627-248">Local tools</span></span>

<span data-ttu-id="50627-249">В .NET Core 3.0 появились локальные средства.</span><span class="sxs-lookup"><span data-stu-id="50627-249">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="50627-250">Локальные средства похожи на [глобальные средства](../tools/global-tools.md), но связаны с определенным расположением на диске.</span><span class="sxs-lookup"><span data-stu-id="50627-250">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="50627-251">Локальные средства недоступны глобально и распространяются в виде пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="50627-251">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="50627-252">Если вы пробовали использовать локальные средства в предварительной версии 1 .NET Core 3.0, например запуск `dotnet tool restore` или `dotnet tool install`, удалите папку кэша локальных средств.</span><span class="sxs-lookup"><span data-stu-id="50627-252">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="50627-253">В противном случае локальные средства не будут работать ни в одной более новой версии.</span><span class="sxs-lookup"><span data-stu-id="50627-253">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="50627-254">Эта папка находится по адресу:</span><span class="sxs-lookup"><span data-stu-id="50627-254">This folder is located at:</span></span>
>
> <span data-ttu-id="50627-255">В macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="50627-255">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="50627-256">В Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="50627-256">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="50627-257">Локальные средства используют имя файла манифеста `dotnet-tools.json` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="50627-257">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="50627-258">Этот файл манифеста определяет, какие средства доступны в этой папке и далее.</span><span class="sxs-lookup"><span data-stu-id="50627-258">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="50627-259">Файл манифеста можно распространять вместе с кодом, чтобы те же средства мог восстановить и использовать любой, кто работает с вашим кодом.</span><span class="sxs-lookup"><span data-stu-id="50627-259">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="50627-260">Для глобальных и локальных средств требуется совместимая версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="50627-260">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="50627-261">Сейчас на сайте NuGet.org многие средства предназначены для среды выполнения .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="50627-261">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="50627-262">Чтобы установить эти средства глобально или локально, нужно, как и раньше, установить [среду выполнения NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="50627-262">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="50627-263">Новые параметры global.json</span><span class="sxs-lookup"><span data-stu-id="50627-263">New global.json options</span></span>

<span data-ttu-id="50627-264">Файл *Global. JSON* содержит новые параметры, которые позволяют более гибко определять требуемую версию пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50627-264">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="50627-265">Эти новые параметры перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="50627-265">The new options are:</span></span>

- <span data-ttu-id="50627-266">`allowPrerelease`. Указывает, должен ли сопоставитель пакетов SDK учитывать предварительные версии при выборе версии пакета SDK, которую следует использовать.</span><span class="sxs-lookup"><span data-stu-id="50627-266">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="50627-267">`rollForward`. Обозначает политику наката, которая используется при выборе версии пакета SDK (либо в качестве резервной, если определенная версия пакета SDK отсутствует, либо в качестве директивы для использования более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="50627-267">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="50627-268">Дополнительные сведения об изменениях, в том числе значения по умолчанию, поддерживаемые значения и новые правила сопоставления, см. в разделе [общих сведений о global.json](../tools/global-json.md).</span><span class="sxs-lookup"><span data-stu-id="50627-268">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="50627-269">Уменьшенные размеры куч сборки мусора</span><span class="sxs-lookup"><span data-stu-id="50627-269">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="50627-270">Размер кучи сборщика мусора по умолчанию был уменьшен, так что теперь .NET Core использует меньше памяти.</span><span class="sxs-lookup"><span data-stu-id="50627-270">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="50627-271">Это изменение лучше соответствует выделению бюджета нулевого поколения и размерам кэша современных процессоров.</span><span class="sxs-lookup"><span data-stu-id="50627-271">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="50627-272">Поддержка больших страниц сборки мусора</span><span class="sxs-lookup"><span data-stu-id="50627-272">Garbage Collection Large Page support</span></span>

<span data-ttu-id="50627-273">Большие страницы (также известные как огромные страницы в Linux) — это функция, благодаря которой операционная система может задавать области памяти больше, чем размер нативной страницы (часто 4K), чтобы повысить производительность приложения, запрашивающего такие страницы.</span><span class="sxs-lookup"><span data-stu-id="50627-273">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="50627-274">Сборщик мусора теперь можно настраивать с помощью параметра **GCLargePages** как дополнительной функции, позволяющей выделять большие страницы в Windows.</span><span class="sxs-lookup"><span data-stu-id="50627-274">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="50627-275">Классическое приложение Windows и модель COM</span><span class="sxs-lookup"><span data-stu-id="50627-275">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="50627-276">Установщик пакета SDK Windows для .NET Core</span><span class="sxs-lookup"><span data-stu-id="50627-276">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="50627-277">Начиная с .NET Core 3.0, установщик MSI для Windows был изменен.</span><span class="sxs-lookup"><span data-stu-id="50627-277">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="50627-278">Установщики пакетов SDK теперь обновляют дополнительные пакеты функций SDK на месте.</span><span class="sxs-lookup"><span data-stu-id="50627-278">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="50627-279">Пакеты функций определяют *сотни* в обозначении *исправления* в номере версии.</span><span class="sxs-lookup"><span data-stu-id="50627-279">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="50627-280">Например, в версиях **3.0._101_** и **3.0._201_** пакеты функций различаются, а в версиях **3.0._101_** и **3.0._199_**  — одинаковы.</span><span class="sxs-lookup"><span data-stu-id="50627-280">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="50627-281">При установке пакета SDK для .NET Core **3.0._101_** пакет SDK для .NET Core **3.0._100_** , если он есть на компьютере, удаляется.</span><span class="sxs-lookup"><span data-stu-id="50627-281">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="50627-282">Когда на тот же компьютер устанавливается пакет SDK для .NET Core **3.0._200_** , пакет SDK для .NET Core **3.0._101_** удаляться не будет.</span><span class="sxs-lookup"><span data-stu-id="50627-282">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="50627-283">Дополнительные сведения об управлении версиями см. в разделе [Общие сведения об управлении версиями в .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="50627-283">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="50627-284">Классические приложения Windows</span><span class="sxs-lookup"><span data-stu-id="50627-284">Windows desktop</span></span>

<span data-ttu-id="50627-285">.NET Core 3.0 поддерживает классические приложения Windows с помощью Windows Presentation Foundation (WPF) и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="50627-285">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="50627-286">Эти платформы также поддерживают использование современных элементов управления и стилей Fluent из библиотеки XAML пользовательского интерфейса Windows (WinUI) через [острова XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="50627-286">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="50627-287">Компонент Windows Desktop является частью пакета SDK .NET Core 3.0 для Windows.</span><span class="sxs-lookup"><span data-stu-id="50627-287">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="50627-288">Вы можете создать приложение WPF или Windows Forms с помощью следующих команд `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="50627-288">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="50627-289">Visual Studio 2019 добавляет шаблоны **Новый проект** для .NET Core 3.0 Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="50627-289">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="50627-290">Дополнительные сведения о переносе существующего приложения .NET Framework см. в разделах [Перенос проектов WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) и [Перенос проектов Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="50627-290">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="50627-291">Высокое разрешение для WinForms</span><span class="sxs-lookup"><span data-stu-id="50627-291">WinForms high DPI</span></span>

<span data-ttu-id="50627-292">Приложения .NET Core Windows Forms могут устанавливать режим высокого разрешения экрана с помощью <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50627-292">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50627-293">Метод `SetHighDpiMode` задает соответствующий режим высокого разрешения, если параметр не задан другими способами, например с помощью `App.Manifest` или P/Invoke перед `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="50627-293">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="50627-294">Возможны следующие значения `highDpiMode`, выраженные перечислением <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="50627-294">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="50627-295">См. о [разработке классических приложений с поддержкой высокого разрешения экрана в Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="50627-295">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="50627-296">Создание компонентов COM</span><span class="sxs-lookup"><span data-stu-id="50627-296">Create COM components</span></span>

<span data-ttu-id="50627-297">Теперь в Windows можно создавать управляемые компоненты, вызываемые COM.</span><span class="sxs-lookup"><span data-stu-id="50627-297">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="50627-298">Эта возможность необходима для использования .NET Core с моделями надстроек COM и обеспечивает соответствие с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50627-298">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="50627-299">В отличие от .NET Framework, где в качестве сервера использовалась библиотека *mscoree.dll*, .NET Core при сборке вашего COM-компонента добавляет в каталог *bin* dll собственного средства запуска.</span><span class="sxs-lookup"><span data-stu-id="50627-299">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="50627-300">Пример того, как создать и использовать компонент COM, см. в разделе [Демонстрация COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="50627-300">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="50627-301">Собственное взаимодействие Windows</span><span class="sxs-lookup"><span data-stu-id="50627-301">Windows Native Interop</span></span>

<span data-ttu-id="50627-302">Windows предоставляет собственный API с широкими возможностями в виде API C, COM и WinRT.</span><span class="sxs-lookup"><span data-stu-id="50627-302">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="50627-303">При том что .NET Core поддерживает **P/Invoke**, в .NET Core 3.0 добавлена возможность **воссоздавать API COM** и **активировать API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="50627-303">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="50627-304">Пример кода см. в разделе [Демонстрация Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="50627-304">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="50627-305">Развертывание MSIX</span><span class="sxs-lookup"><span data-stu-id="50627-305">MSIX Deployment</span></span>

<span data-ttu-id="50627-306">[MSIX](https://docs.microsoft.com/windows/msix/) — это новый формат пакета приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="50627-306">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="50627-307">Его можно использовать для развертывания классических приложений .NET Core 3.0 для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="50627-307">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="50627-308">[Проект упаковки приложений Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), доступный в Visual Studio 2019, позволяет создавать пакеты MSIX с [автономными](../deploying/index.md#publish-self-contained) приложениями .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50627-308">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#publish-self-contained) .NET Core applications.</span></span>

<span data-ttu-id="50627-309">Файл проекта .NET Core должен указывать поддерживаемые среды выполнения в свойстве `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="50627-309">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="50627-310">Усовершенствования Linux</span><span class="sxs-lookup"><span data-stu-id="50627-310">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="50627-311">SerialPort для Linux</span><span class="sxs-lookup"><span data-stu-id="50627-311">SerialPort for Linux</span></span>

<span data-ttu-id="50627-312">.NET Core 3.0 обеспечивает базовую поддержку <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> в Linux.</span><span class="sxs-lookup"><span data-stu-id="50627-312">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="50627-313">Раньше среда .NET Core поддерживала `SerialPort` только в Windows.</span><span class="sxs-lookup"><span data-stu-id="50627-313">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="50627-314">Дополнительные сведения об ограниченной поддержке последовательного порта в Linux см. в описании [проблемы № 33146 на сайте GitHub](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="50627-314">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="50627-315">Ограничения памяти в Docker и cgroup</span><span class="sxs-lookup"><span data-stu-id="50627-315">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="50627-316">Запуск .NET Core 3.0 на платформе Linux с помощью Docker лучше работает с ограничениями памяти в cgroup.</span><span class="sxs-lookup"><span data-stu-id="50627-316">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="50627-317">Запуск контейнера Docker с ограничениями памяти, например с `docker run -m`, изменяет поведение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50627-317">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="50627-318">Размер кучи сборщика мусора (GC) по умолчанию составляет не более 20 МБ или 75 % от ограничения памяти для контейнера.</span><span class="sxs-lookup"><span data-stu-id="50627-318">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="50627-319">Конкретный размер можно указать абсолютным числом или в виде процента от ограничения cgroup.</span><span class="sxs-lookup"><span data-stu-id="50627-319">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="50627-320">Минимальный зарезервированный размер сегмента в куче GC составляет 16 МБ.</span><span class="sxs-lookup"><span data-stu-id="50627-320">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="50627-321">При использовании такого размера количество создаваемых на компьютерах куч будет меньше.</span><span class="sxs-lookup"><span data-stu-id="50627-321">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="50627-322">Поддержка GPIO для Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="50627-322">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="50627-323">В NuGet выпущено два новых пакета, которые можно использовать для программирования GPIO:</span><span class="sxs-lookup"><span data-stu-id="50627-323">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="50627-324">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="50627-324">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="50627-325">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="50627-325">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="50627-326">Пакеты GPIO содержат API для устройств *GPIO*, *SPI*, *I2C* и *PWM*.</span><span class="sxs-lookup"><span data-stu-id="50627-326">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="50627-327">Пакет привязок Интернета вещей содержит привязки устройств.</span><span class="sxs-lookup"><span data-stu-id="50627-327">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="50627-328">Дополнительные сведения см. в [репозитории GitHub устройств](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="50627-328">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="50627-329">Поддержка ARM64 Linux</span><span class="sxs-lookup"><span data-stu-id="50627-329">ARM64 Linux support</span></span>

<span data-ttu-id="50627-330">В .NET Core 3.0 добавлена поддержка ARM64 для Linux.</span><span class="sxs-lookup"><span data-stu-id="50627-330">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="50627-331">Основной вариант использования для ARM64 в данный момент — это сценарии Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="50627-331">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="50627-332">Дополнительные сведения см. в статье [Состояние .NET Core в ARM64](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="50627-332">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="50627-333">[Образы Docker для .NET Core в ARM64](https://hub.docker.com/r/microsoft/dotnet/) доступны для Alpine, Debian и Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="50627-333">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="50627-334">Поддержка **ARM64** в Windows еще недоступна.</span><span class="sxs-lookup"><span data-stu-id="50627-334">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="50627-335">Безопасность</span><span class="sxs-lookup"><span data-stu-id="50627-335">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="50627-336">TLS 1.3 и OpenSSL 1.1.1 в Linux</span><span class="sxs-lookup"><span data-stu-id="50627-336">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="50627-337">Теперь .NET Core использует преимущества [поддержки TLS 1.3 в OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), когда она доступна в данной среде.</span><span class="sxs-lookup"><span data-stu-id="50627-337">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="50627-338">В TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="50627-338">With TLS 1.3:</span></span>

- <span data-ttu-id="50627-339">За счет уменьшения количества круговых путей между клиентом и сервером уменьшено время соединения.</span><span class="sxs-lookup"><span data-stu-id="50627-339">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="50627-340">За счет удаления различных устаревших и небезопасных алгоритмов шифрования повышена безопасность.</span><span class="sxs-lookup"><span data-stu-id="50627-340">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="50627-341">В системе Linux .NET Core 3.0 по возможности использует **OpenSSL 1.1.1**, **OpenSSL 1.1.0** или **OpenSSL 1.0.2**.</span><span class="sxs-lookup"><span data-stu-id="50627-341">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="50627-342">Если есть доступ к **OpenSSL 1.1.1**, оба типа, <xref:System.Net.Security.SslStream?displayProperty=nameWithType> и <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>, используют **TLS 1.3** (при условии что клиент и сервер поддерживают **TLS 1.3**).</span><span class="sxs-lookup"><span data-stu-id="50627-342">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50627-343">Windows и macOS еще не поддерживают **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="50627-343">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="50627-344">.NET Core 3.0 будет поддерживать **TLS 1.3** в этих операционных системах, когда поддержка станет доступной.</span><span class="sxs-lookup"><span data-stu-id="50627-344">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="50627-345">В следующем примере C# 8.0 показано, как .NET Core 3.0 в Ubuntu 18.10 подключается к <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="50627-345">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="50627-346">Шифры криптографии</span><span class="sxs-lookup"><span data-stu-id="50627-346">Cryptography ciphers</span></span>

<span data-ttu-id="50627-347">В .NET 3.0 добавлена поддержка шифров **AES-GCM** и **AES-CCM**, реализованных с помощью <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> и <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> соответственно.</span><span class="sxs-lookup"><span data-stu-id="50627-347">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="50627-348">Оба этих алгоритма представляют собой [алгоритмы AEAD (аутентифицированного шифрования с присоединенными данными)](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="50627-348">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="50627-349">В следующем коде показано использование шифра `AesGcm` для шифрования и расшифровки случайных данных.</span><span class="sxs-lookup"><span data-stu-id="50627-349">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="50627-350">Импорт и экспорт криптографических ключей</span><span class="sxs-lookup"><span data-stu-id="50627-350">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="50627-351">.NET Core 3.0 поддерживает импорт и экспорт асимметричных открытых и закрытых ключей из стандартных форматов.</span><span class="sxs-lookup"><span data-stu-id="50627-351">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="50627-352">Сертификат X.509 использовать не нужно.</span><span class="sxs-lookup"><span data-stu-id="50627-352">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="50627-353">Все типы ключей, включая *RSA*, *DSA*, *ECDsa* и *ECDiffieHellman*, поддерживают следующие форматы:</span><span class="sxs-lookup"><span data-stu-id="50627-353">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="50627-354">**Открытый ключ**</span><span class="sxs-lookup"><span data-stu-id="50627-354">**Public Key**</span></span>
  - <span data-ttu-id="50627-355">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="50627-355">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="50627-356">**Закрытый ключ**</span><span class="sxs-lookup"><span data-stu-id="50627-356">**Private key**</span></span>
  - <span data-ttu-id="50627-357">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="50627-357">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="50627-358">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="50627-358">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="50627-359">Ключи RSA также поддерживают:</span><span class="sxs-lookup"><span data-stu-id="50627-359">RSA keys also support:</span></span>

- <span data-ttu-id="50627-360">**Открытый ключ**</span><span class="sxs-lookup"><span data-stu-id="50627-360">**Public Key**</span></span>
  - <span data-ttu-id="50627-361">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="50627-361">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="50627-362">**Закрытый ключ**</span><span class="sxs-lookup"><span data-stu-id="50627-362">**Private key**</span></span>
  - <span data-ttu-id="50627-363">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="50627-363">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="50627-364">Методы экспорта создают двоичные данные в кодировке DER, а методы импорта выполняют то же самое.</span><span class="sxs-lookup"><span data-stu-id="50627-364">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="50627-365">Если ключ хранится в формате PEM в виде текста, вызывающему объекту потребуется выполнить декодирование содержимого в формате base64, прежде чем вызывать метод импорта.</span><span class="sxs-lookup"><span data-stu-id="50627-365">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="50627-366">Файлы **PKCS 8** можно проверять с помощью <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType>, а файлы **PFX/PKCS #12** — с помощью <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50627-366">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50627-367">Для манипуляций с файлами **PFX/PKCS #12** можно использовать <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50627-367">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="50627-368">Изменения API .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="50627-368">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="50627-369">Диапазоны и индексы</span><span class="sxs-lookup"><span data-stu-id="50627-369">Ranges and indices</span></span>

<span data-ttu-id="50627-370">Новый тип <xref:System.Index?displayProperty=nameWithType> можно использовать для индексирования.</span><span class="sxs-lookup"><span data-stu-id="50627-370">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="50627-371">Вы можете создать с помощью `int` индекс, который отсчитывается с начала, а с помощью оператора `^` префикса (C#) индекс, который отсчитывается с конца:</span><span class="sxs-lookup"><span data-stu-id="50627-371">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="50627-372">Кроме того, есть тип <xref:System.Range?displayProperty=nameWithType>, который состоит из двух значений `Index` (одно для начала и одно для конца) и который можно написать с помощью выражения диапазона `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="50627-372">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="50627-373">После этого можно выполнить индексацию с помощью команды `Range`, которая создает срез:</span><span class="sxs-lookup"><span data-stu-id="50627-373">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="50627-374">Дополнительные сведения см. в [руководстве по диапазонам и индексам](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="50627-374">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="50627-375">Асинхронные потоки</span><span class="sxs-lookup"><span data-stu-id="50627-375">Async streams</span></span>

<span data-ttu-id="50627-376">Тип <xref:System.Collections.Generic.IAsyncEnumerable%601> — это новая асинхронная версия <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="50627-376">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="50627-377">Язык позволяет выполнить действие `await foreach` с этими объектами `IAsyncEnumerable<T>`, чтобы использовать их элементы, и действие `yield return` по отношению к ним, чтобы создать элементы.</span><span class="sxs-lookup"><span data-stu-id="50627-377">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="50627-378">В приведенном ниже примере демонстрируется создание и применение асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="50627-378">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="50627-379">Инструкция `foreach` является асинхронной и использует `yield return`, чтобы создать асинхронные потоки для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="50627-379">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="50627-380">Этот шаблон (с использованием `yield return`) является рекомендуемой моделью для создания асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="50627-380">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="50627-381">Помимо возможности `await foreach` вы также можете создать асинхронные итераторы, например, итератор, который возвращает `IAsyncEnumerable/IAsyncEnumerator`, для которого можно применить `await` и `yield`.</span><span class="sxs-lookup"><span data-stu-id="50627-381">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="50627-382">Для объектов, которые необходимо удалить, можно использовать `IAsyncDisposable`, который реализовывают различные типы BCL, такие как `Stream` и `Timer`.</span><span class="sxs-lookup"><span data-stu-id="50627-382">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="50627-383">Дополнительные сведения см. в [руководстве по асинхронным потокам](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="50627-383">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="50627-384">IEEE с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="50627-384">IEEE Floating-point</span></span>

<span data-ttu-id="50627-385">API плавающей запятой сейчас обновляются, чтобы соответствовать [редакции IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="50627-385">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="50627-386">Цель этих изменений — предоставлять все **обязательные** операции и гарантировать, что их поведение будет соответствовать спецификации IEEE. Дополнительные сведения об улучшениях, связанных с плавающей запятой, см. в записи блога [Улучшения в синтаксическом анализе и форматировании плавающей запятой в .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="50627-386">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="50627-387">Исправления синтаксического анализа и форматирования включают:</span><span class="sxs-lookup"><span data-stu-id="50627-387">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="50627-388">Правильный анализ и округление входных данных любой длины.</span><span class="sxs-lookup"><span data-stu-id="50627-388">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="50627-389">Правильный анализ и форматирование отрицательного нуля.</span><span class="sxs-lookup"><span data-stu-id="50627-389">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="50627-390">Правильный анализ `Infinity` и `NaN` с помощью проверки без учета регистра и допущения необязательного `+` в начале, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="50627-390">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="50627-391">Новый API <xref:System.Math?displayProperty=nameWithType> включают:</span><span class="sxs-lookup"><span data-stu-id="50627-391">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="50627-392"><xref:System.Math.BitIncrement(System.Double)> и <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="50627-392"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="50627-393">Соответствует операциям IEEE `nextUp` и `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="50627-393">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="50627-394">Они возвращают наименьшее число с плавающей запятой, которое может быть больше или меньше входных данных (соответственно).</span><span class="sxs-lookup"><span data-stu-id="50627-394">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="50627-395">Например, `Math.BitIncrement(0.0)` вернет `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="50627-395">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="50627-396"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> и <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="50627-396"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="50627-397">Соответствуют операциям IEEE `maxNumMag` и `minNumMag`. Они возвращают значение, которое будет больше или меньше из двух величин (соответственно).</span><span class="sxs-lookup"><span data-stu-id="50627-397">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="50627-398">Например, `Math.MaxMagnitude(2.0, -3.0)` вернет `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="50627-398">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="50627-399">Соответствует операции IEEE `logB`, которая возвращает целочисленное значение. Она возвращает целочисленный логарифм по основанию 2 входного параметра.</span><span class="sxs-lookup"><span data-stu-id="50627-399">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="50627-400">Этот метод действует практически так же, как `floor(log2(x))`, но с минимальными погрешностями округления.</span><span class="sxs-lookup"><span data-stu-id="50627-400">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="50627-401">Соответствует операции IEEE `scaleB`, которая принимает целочисленное значение. Возвращает `x * pow(2, n)`, но выполняется с минимальными погрешностями округления.</span><span class="sxs-lookup"><span data-stu-id="50627-401">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="50627-402">Соответствует операции IEEE `log2`. Возвращает логарифм по основанию 2.</span><span class="sxs-lookup"><span data-stu-id="50627-402">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="50627-403">Сводит к минимуму погрешность округления.</span><span class="sxs-lookup"><span data-stu-id="50627-403">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="50627-404">Соответствует операции IEEE `fma`. Выполняет умножение и сложение.</span><span class="sxs-lookup"><span data-stu-id="50627-404">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="50627-405">То есть он выполняет `(x * y) + z` как одну операцию, тем самым сводя к минимуму погрешность округления.</span><span class="sxs-lookup"><span data-stu-id="50627-405">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="50627-406">Например, `FusedMultiplyAdd(1e308, 2.0, -1e308)` возвращает `1e308`.</span><span class="sxs-lookup"><span data-stu-id="50627-406">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="50627-407">Стандартный `(1e308 * 2.0) - 1e308` возвращает `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="50627-407">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="50627-408">Соответствует операции IEEE `copySign`. Возвращает значение `x`, но со знаком `y`.</span><span class="sxs-lookup"><span data-stu-id="50627-408">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="50627-409">Встроенные объекты, зависимые от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="50627-409">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="50627-410">Были добавлены API-интерфейсы, которые разрешают доступ к определенным инструкциям ЦП, ориентированным на производительность, например **SIMD** или наборы **инструкций побитовой обработки**.</span><span class="sxs-lookup"><span data-stu-id="50627-410">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="50627-411">Эти инструкции помогут значительно улучшить производительность в некоторых сценариях, таких как эффективная параллельная обработка данных.</span><span class="sxs-lookup"><span data-stu-id="50627-411">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="50627-412">Там, где это возможно, библиотеки .NET начали использовать эти инструкции для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="50627-412">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="50627-413">Дополнительные сведения см. в разделе [Встроенные объекты, зависимые от платформы .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span><span class="sxs-lookup"><span data-stu-id="50627-413">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="50627-414">Улучшенные API версий .NET Core</span><span class="sxs-lookup"><span data-stu-id="50627-414">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="50627-415">Начиная с .NET Core 3.0, API версий, предоставляемые с .NET Core, возвращают те данные, которые должны.</span><span class="sxs-lookup"><span data-stu-id="50627-415">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="50627-416">Пример:</span><span class="sxs-lookup"><span data-stu-id="50627-416">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="50627-417">Критическое изменение.</span><span class="sxs-lookup"><span data-stu-id="50627-417">Breaking change.</span></span> <span data-ttu-id="50627-418">С технической точки зрения это изменение является критическим, поскольку изменилась схема управления версиями.</span><span class="sxs-lookup"><span data-stu-id="50627-418">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="50627-419">Быстрая встроенная поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="50627-419">Fast built-in JSON support</span></span>

<span data-ttu-id="50627-420">Пользователи .NET в основном полагались на [Newtonsoft.Json](https://www.newtonsoft.com/json) и другие популярные библиотеки JSON, которые по-прежнему остаются хорошими вариантами.</span><span class="sxs-lookup"><span data-stu-id="50627-420">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="50627-421">`Newtonsoft.Json` использует в качестве базового типа данных строки .NET, которые обладают внутренней структурой UTF-16.</span><span class="sxs-lookup"><span data-stu-id="50627-421">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="50627-422">Новая встроенная поддержка JSON отличается высокой производительностью, малым распределением и поддержкой текста JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="50627-422">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="50627-423">Дополнительные сведения о пространстве имен и типах <xref:System.Text.Json> см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="50627-423">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="50627-424">Сериализация JSON в .NET — общие сведения</span><span class="sxs-lookup"><span data-stu-id="50627-424">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="50627-425">[Практическое руководство. Сериализация и десериализация JSON в .NET](../../standard/serialization/system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="50627-425">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="50627-426">Переход с Newtonsoft.Json на System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="50627-426">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="50627-427">Поддержка HTTP/2</span><span class="sxs-lookup"><span data-stu-id="50627-427">HTTP/2 support</span></span>

<span data-ttu-id="50627-428">Тип <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> поддерживает протокол HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="50627-428">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="50627-429">Если протокол HTTP/2 включен, версия протокола HTTP согласуется через TLS/ALPN, а HTTP/2 используется, только если его выбрал сервер.</span><span class="sxs-lookup"><span data-stu-id="50627-429">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="50627-430">Протоколом по умолчанию остается HTTP/1.1, но у вас есть два способа включить HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="50627-430">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="50627-431">Во-первых, можно указать использование HTTP/2 в заголовке запроса:</span><span class="sxs-lookup"><span data-stu-id="50627-431">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="50627-432">Во-вторых, можно изменить <xref:System.Net.Http.HttpClient> для использования HTTP/2 по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="50627-432">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="50627-433">При разработке приложений часто требуется подключение без шифрования.</span><span class="sxs-lookup"><span data-stu-id="50627-433">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="50627-434">Если вы знаете, что целевая конечная точка использует протокол HTTP/2, вы можете включить незашифрованные подключения для HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="50627-434">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="50627-435">Для этого задайте переменной среды `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` значение `1` или включите этот параметр в контексте приложения:</span><span class="sxs-lookup"><span data-stu-id="50627-435">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="50627-436">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="50627-436">Next steps</span></span>

- [<span data-ttu-id="50627-437">Изучите критические отличия между версиями между .NET Core 2.2 и 3.0.</span><span class="sxs-lookup"><span data-stu-id="50627-437">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="50627-438">Изучите критические изменения в NET Core 3.0 для приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="50627-438">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
