---
title: Новые возможности .NET Core 3.0
description: Дополнительные сведения о новых возможностях .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 26fb7cb25b9bf7f00f87059fbe1848763f7f175d
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415550"
---
# <a name="whats-new-in-net-core-30-preview-1"></a><span data-ttu-id="4d804-103">Новые возможности .NET Core 3.0 (предварительная версия 1)</span><span class="sxs-lookup"><span data-stu-id="4d804-103">What's new in .NET Core 3.0 (Preview 1)</span></span>

<span data-ttu-id="4d804-104">В этой статье описываются новые возможности в .NET Core 3.0 (предварительная версия 1).</span><span class="sxs-lookup"><span data-stu-id="4d804-104">This article describes what is new in .NET Core 3.0 (preview 1).</span></span> <span data-ttu-id="4d804-105">Одно из основных усовершенствований — это поддержка классических приложений Windows (только Windows).</span><span class="sxs-lookup"><span data-stu-id="4d804-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="4d804-106">Используя компонент .NET Core 3.0 под названием Windows Desktop, вы можете перенести приложения Windows Forms и Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="4d804-106">By utilizing a .NET Core 3.0 component called Windows Desktop, you can port your Windows Forms Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="4d804-107">Следует уточнить, что компонент Windows Desktop поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="4d804-107">To be clear, the Windows Desktop component is only supported on Windows.</span></span> <span data-ttu-id="4d804-108">Дополнительные сведения см. в разделе [Классические приложения Windows](#windows-desktop), приведенном ниже.</span><span class="sxs-lookup"><span data-stu-id="4d804-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="4d804-109">В .NET Core 3.0 добавлена поддержка C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="4d804-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="4d804-110">[Скачайте и начните работу с .NET Core 3 (предварительная версия 1)](https://aka.ms/netcore3download) прямо сейчас в Windows, Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="4d804-110">[Download and get started with .NET Core 3 Preview 1](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="4d804-111">Полное описание выпуска .NET Core 3 (предварительная версия 1) см. [здесь](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="4d804-111">You can see complete details of the release in the [.NET Core 3 Preview 1 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="4d804-112">Дополнительные сведения см. в статье, посвященной [объявлению .NET Core 3.0 (предварительная версия 1)](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span><span class="sxs-lookup"><span data-stu-id="4d804-112">For more information, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="4d804-113">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="4d804-113">.NET Standard 2.1</span></span>

<span data-ttu-id="4d804-114">.NET Core 3.0 реализует .NET Standard 2.1.</span><span class="sxs-lookup"><span data-stu-id="4d804-114">.NET Core 3.0 implements .NET Standard 2.1.</span></span>

## <a name="default-executables"></a><span data-ttu-id="4d804-115">Исполняемые файлы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4d804-115">Default executables</span></span>

<span data-ttu-id="4d804-116">.NET Core теперь будет создавать [зависящие от платформы исполняемые файлы](../deploying/index.md#framework-dependent-executables-fde) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d804-116">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="4d804-117">Это новый аспект для приложений, использующих глобально установленную версию .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4d804-117">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="4d804-118">До настоящего времени исполняемые файлы создавались только в [автономных развертываниях](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="4d804-118">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="4d804-119">Во время выполнения команды `dotnet build` или `dotnet publish` создается исполняемый файл, который соответствует среде и платформе используемого пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="4d804-119">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="4d804-120">Предполагается, что с этими исполняемыми файлами можно выполнять те же действия, что и с другими исполняемыми файлами в машинном коде, например:</span><span class="sxs-lookup"><span data-stu-id="4d804-120">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="4d804-121">исполняемый файл можно дважды щелкнуть;</span><span class="sxs-lookup"><span data-stu-id="4d804-121">You can double-click on the executable.</span></span>
* <span data-ttu-id="4d804-122">приложение можно запустить из командной строки напрямую, например `myapp.exe` в Windows и `./myapp` в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="4d804-122">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="4d804-123">Сборка копирует зависимости</span><span class="sxs-lookup"><span data-stu-id="4d804-123">Build copies dependencies</span></span>

<span data-ttu-id="4d804-124">`dotnet build` теперь копирует зависимости NuGet для вашего приложения из кэша NuGet в выходную папку сборки.</span><span class="sxs-lookup"><span data-stu-id="4d804-124">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="4d804-125">Ранее зависимости копировались только в рамках выполнения команды `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="4d804-125">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="4d804-126">Для некоторых операций, таких как связывание и публикация страницы Razor, по-прежнему будет требоваться публикация.</span><span class="sxs-lookup"><span data-stu-id="4d804-126">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="4d804-127">Локальные средства dotnet</span><span class="sxs-lookup"><span data-stu-id="4d804-127">Local dotnet tools</span></span>

<span data-ttu-id="4d804-128">Хотя в .NET Core 2.1 была поддержка глобальных средств, в .NET Core 3.0 теперь есть локальные средства.</span><span class="sxs-lookup"><span data-stu-id="4d804-128">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="4d804-129">Локальные средства похожи на глобальные средства, но связаны с определенным расположением на диске.</span><span class="sxs-lookup"><span data-stu-id="4d804-129">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="4d804-130">Это обеспечивает инструменты для отдельных проектов и репозиториев.</span><span class="sxs-lookup"><span data-stu-id="4d804-130">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="4d804-131">Любое средство, установленное локально, недоступно глобально.</span><span class="sxs-lookup"><span data-stu-id="4d804-131">Any tool installed locally isn't available globally.</span></span>

<span data-ttu-id="4d804-132">Локальные средства используют имя файла манифеста `dotnet-tools.json` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4d804-132">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="4d804-133">Этот файл манифеста определяет, какие средства доступны.</span><span class="sxs-lookup"><span data-stu-id="4d804-133">This manifest file defines the tools to be available.</span></span> <span data-ttu-id="4d804-134">Если создать этот файл манифеста в корне репозитория, любой пользователь, клонировавший код, сможет восстановить и использовать средства, необходимые для успешной работы с кодом.</span><span class="sxs-lookup"><span data-stu-id="4d804-134">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="4d804-135">Если файл манифеста локальных средств доступен, выполните приведенную ниже команду, чтобы автоматически скачать и установить эти средства локально:</span><span class="sxs-lookup"><span data-stu-id="4d804-135">When the local tools manifest file is available, use the following command to automatically download and install those tools locally:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="4d804-136">Запустите локальное средство с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4d804-136">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="4d804-137">При вызове локального средства dotnet выполняет поиск манифеста в структуре каталогов.</span><span class="sxs-lookup"><span data-stu-id="4d804-137">When a local tool is called, dotnet searches for a manifest up the directory structure.</span></span> <span data-ttu-id="4d804-138">Когда файл манифеста средства обнаруживается, выполняется поиск запрашиваемого средства.</span><span class="sxs-lookup"><span data-stu-id="4d804-138">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="4d804-139">При обнаружении средства добавляются сведения, необходимые для поиска средства в расположении глобальных пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="4d804-139">If the tool is found, it includes the information needed to find the tool in the NuGet global packages location.</span></span> 

<span data-ttu-id="4d804-140">Если средство обнаруживается в манифесте, а не в кэше, пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4d804-140">If the tool is found in the manifest, but not the cache, the user receives an error.</span></span> <span data-ttu-id="4d804-141">Сообщение будет усовершенствовано после выхода предварительной версии 1: оно будет содержать запрос для пользователя на запуск `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="4d804-141">The message will be improved after Preview 1 to request the user run `dotnet tool restore`.</span></span>

<span data-ttu-id="4d804-142">Чтобы добавить локальные средства в каталог, необходимо сначала создать файл манифеста средства.</span><span class="sxs-lookup"><span data-stu-id="4d804-142">To add local tools to a directory, you need to first create the tool manifest file.</span></span> <span data-ttu-id="4d804-143">После выхода предварительной версии 1 мы предложим механизм создания файлов манифестов средств, например новый шаблон dotnet.</span><span class="sxs-lookup"><span data-stu-id="4d804-143">After Preview 1, we will offer a mechanism for creating tool manifest files, such as a dotnet new template.</span></span> <span data-ttu-id="4d804-144">Для предварительной версии 1 необходимо создать файл с именем `dotnet-tools.json` со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="4d804-144">For Preview 1 you must create the file named `dotnet-tools.json` with the following contents:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="4d804-145">После создания манифеста можно добавить в него локальные средства с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4d804-145">Once the manifest is created, you can add local tools to it using:</span></span>

```console
dotnet tool install <toolPackageId>
```

<span data-ttu-id="4d804-146">Эта команда устанавливает последнюю версию средства, если не указана другая версия.</span><span class="sxs-lookup"><span data-stu-id="4d804-146">This command installs the latest version of the tool, unless another version is specified.</span></span>  <span data-ttu-id="4d804-147">Даже если автоматически была выбрана последняя версия, версия средства записывается в файл манифеста средства, чтобы можно было восстановить или запустить правильную версию средства.</span><span class="sxs-lookup"><span data-stu-id="4d804-147">Even if the latest version was automatically chosen, the version of the tool is written into the tool manifest file to allow the correct version of the tool to be restored or run.</span></span>

<span data-ttu-id="4d804-148">Файл манифеста средства разработан так, чтобы его можно было редактировать вручную, например, когда необходимо обновить требуемую версию для работы с репозиторием.</span><span class="sxs-lookup"><span data-stu-id="4d804-148">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span>

<span data-ttu-id="4d804-149">Ниже приведен пример файла `dotnet-tools.json`:</span><span class="sxs-lookup"><span data-stu-id="4d804-149">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="4d804-150">Чтобы удалить средство из файла манифеста средства, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4d804-150">To remove a tool from the tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <toolPackageId>
```

<span data-ttu-id="4d804-151">Для глобальных и локальных средств требуется совместимая версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d804-151">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="4d804-152">Сейчас на сайте NuGet.org многие средства предназначены для среды выполнения .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="4d804-152">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="4d804-153">Чтобы установить их глобально или локально, по-прежнему необходимо установить [среду выполнения NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="4d804-153">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="4d804-154">Дополнительные сведения см. в [документации по предварительной версии локальных средств](https://github.com/dotnet/cli/issues/10288).</span><span class="sxs-lookup"><span data-stu-id="4d804-154">For more information, see [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="4d804-155">Классические приложения Windows</span><span class="sxs-lookup"><span data-stu-id="4d804-155">Windows desktop</span></span>

<span data-ttu-id="4d804-156">Начиная с .NET Core 3.0 (предварительная версия 1), можно создавать классические приложения Windows с помощью WPF и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4d804-156">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="4d804-157">Эти платформы также поддерживают использование современных элементов управления и стилей Fluent из библиотеки XAML пользовательского интерфейса Windows (WinUI) через [острова XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="4d804-157">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="4d804-158">Компонент Windows Desktop является частью пакета SDK .NET Core 3.0 для Windows.</span><span class="sxs-lookup"><span data-stu-id="4d804-158">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="4d804-159">Вы можете создать приложение WPF или Windows Forms с помощью следующих команд `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="4d804-159">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="4d804-160">Вы можете также открывать и запускать проекты WPF и Windows Forms .NET Core 3.0 и выполнять их отладку в Visual Studio 2019 (предварительная версия 1).</span><span class="sxs-lookup"><span data-stu-id="4d804-160">You can also open, launch, and debug .NET Core 3.0 WPF and Windows Forms projects in Visual Studio 2019 Preview 1.</span></span> <span data-ttu-id="4d804-161">Сейчас эти проекты можно открывать в Visual Studio 2017 15.9, но этот сценарий не поддерживается (и вам нужно [включить предварительные версии](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span><span class="sxs-lookup"><span data-stu-id="4d804-161">It's currently possible to open these projects in Visual Studio 2017 15.9, however, it isn't a supported scenario (and you need to [enable previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span></span>

<span data-ttu-id="4d804-162">Новые проекты идентичны имеющимся проектам .NET Core с некоторыми добавлениями.</span><span class="sxs-lookup"><span data-stu-id="4d804-162">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="4d804-163">Ниже приведено сравнение базового консольного проекта .NET Core и базового проекта Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="4d804-163">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="4d804-164">Консольный проект .NET Core использует пакет SDK `Microsoft.NET.Sdk` и объявляет зависимость в .NET Core 3.0 с помощью требуемой версии .NET Framework `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="4d804-164">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="4d804-165">Чтобы создать приложение Windows Desktop, используйте пакет SDK `Microsoft.NET.Sdk.WindowsDesktop` и выберите, какую платформу пользовательского интерфейса использовать:</span><span class="sxs-lookup"><span data-stu-id="4d804-165">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4d804-166">Чтобы выбрать Windows Forms вместо WPF, установите `UseWindowsForms` вместо `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="4d804-166">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4d804-167">Для `UseWPF` и `UseWindowsForms` можно задать значение `true`, если приложение использует обе платформы, например, если в диалоговом окне Windows Forms размещен элемент управления WPF.</span><span class="sxs-lookup"><span data-stu-id="4d804-167">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="4d804-168">Оставьте свой отзыв в репозитории [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) и [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="4d804-168">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="4d804-169">Быстрая встроенная поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="4d804-169">Fast built-in JSON support</span></span>

<span data-ttu-id="4d804-170">`System.Text.Json.Utf8JsonReader` — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="4d804-170">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="4d804-171">`Utf8JsonReader` — это основной тип низкого уровня, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="4d804-171">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="4d804-172">Чтение полезных данных JSON с помощью нового `Utf8JsonReader` осуществляется в два раза быстрее, чем при использовании модуля чтения от [JSON.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="4d804-172">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from [Json.NET](https://www.newtonsoft.com/json).</span></span> <span data-ttu-id="4d804-173">Распределение не осуществляется, пока не понадобится актуализировать токены JSON в виде строк (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="4d804-173">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="4d804-174">Этот новый интерфейс API будет включать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4d804-174">This new API will include the following components:</span></span>

* <span data-ttu-id="4d804-175">В предварительной версии 1: модуль чтения JSON (последовательный доступ).</span><span class="sxs-lookup"><span data-stu-id="4d804-175">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="4d804-176">Ожидается в следующем выпуске: модуль записи JSON, DOM (произвольный доступ), сериализатор poco, десериализатор poco.</span><span class="sxs-lookup"><span data-stu-id="4d804-176">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="4d804-177">Ниже приведен цикл базового модуля чтения для `Utf8JsonReader`, который можно использовать в качестве отправной точки:</span><span class="sxs-lookup"><span data-stu-id="4d804-177">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

<span data-ttu-id="4d804-178">В экосистеме .NET использовалась [Json.NET](https://www.newtonsoft.com/json) и другие популярные библиотеки JSON, которые по-прежнему остаются хорошими вариантами.</span><span class="sxs-lookup"><span data-stu-id="4d804-178">The .NET ecosystem has relied on [Json.NET](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="4d804-179">JSON.NET использует в качестве базового типа данных строки .NET, которые обладают внутренней структурой UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4d804-179">JSON.NET uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span> 

<span data-ttu-id="4d804-180">В .NET Core 2.1 и 3.0 добавлены новые интерфейсы API, что дает возможность записывать интерфейсы API JSON (такие как `Utf8JsonReader`), для которых требуется гораздо меньше памяти и которые основаны на использовании `Span<T>` и строк UTF-8 и лучше удовлетворяют потребности приложений с высокой пропускной способностью, таких как Kestrel, веб-сервер ASP. NET Core.</span><span class="sxs-lookup"><span data-stu-id="4d804-180">In .NET Core 2.1 and 3.0, we added new APIs that makes it possible to write JSON APIs (such as `Utf8JsonReader`) that require much less memory, based on using `Span<T>` and UTF-8 strings, and better serve the needs of high-throughput applications like Kestrel, ASP.NET Core web server.</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="4d804-181">Диапазоны и индексы</span><span class="sxs-lookup"><span data-stu-id="4d804-181">Ranges and indices</span></span>

<span data-ttu-id="4d804-182">Новый тип `Index` можно использовать для индексирования.</span><span class="sxs-lookup"><span data-stu-id="4d804-182">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="4d804-183">Вы можете создать с помощью `int` индекс, который отсчитывается с начала, а с помощью оператора `^` префикса (C#) индекс, который отсчитывается с конца:</span><span class="sxs-lookup"><span data-stu-id="4d804-183">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="4d804-184">Кроме того, есть тип `Range`, который состоит из двух значений `Index` (одно для начала и одно для конца) и который можно написать с помощью выражения диапазона `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="4d804-184">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="4d804-185">Затем можно индексировать с помощью `Range` для создания среза:</span><span class="sxs-lookup"><span data-stu-id="4d804-185">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> <span data-ttu-id="4d804-186">Только [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) поддерживает синтаксис для `Range` и `Index`.</span><span class="sxs-lookup"><span data-stu-id="4d804-186">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports syntax for `Range` and `Index`.</span></span>

## <a name="async-streams"></a><span data-ttu-id="4d804-187">Асинхронные потоки</span><span class="sxs-lookup"><span data-stu-id="4d804-187">Async streams</span></span>

<span data-ttu-id="4d804-188">Тип `IAsyncEnumerable<T>` — это новая асинхронная версия `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="4d804-188">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="4d804-189">Язык позволяет выполнить действие `await foreach` с этими объектами, чтобы использовать их элементы, и действие `yield return` по отношению к ним, чтобы создать элементы.</span><span class="sxs-lookup"><span data-stu-id="4d804-189">The language lets you `await foreach` over these to consume their elements, and `yield return` to them to produce elements.</span></span>

<span data-ttu-id="4d804-190">В приведенном ниже примере демонстрируется создание и применение асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="4d804-190">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="4d804-191">Инструкция `foreach` является асинхронной и использует `yield return`, чтобы создать асинхронные потоки для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="4d804-191">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="4d804-192">Этот шаблон (с использованием `yield return`) является рекомендуемой моделью для создания асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="4d804-192">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> <span data-ttu-id="4d804-193">В .NET Core 3.0 (предварительная версия 1) сейчас есть ошибка с `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="4d804-193">.NET Core 3.0 Preview 1 currently has a bug with `await foreach`.</span></span> <span data-ttu-id="4d804-194">Вместо этого используйте `GetEnumerator` и `MoveNext` для обработки элементов.</span><span class="sxs-lookup"><span data-stu-id="4d804-194">Instead, use `GetEnumerator` and `MoveNext` to process elements.</span></span> <span data-ttu-id="4d804-195">Дополнительные сведения см. в [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span><span class="sxs-lookup"><span data-stu-id="4d804-195">For more information, see [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span></span>

<span data-ttu-id="4d804-196">Помимо возможности `await foreach` вы также можете создать асинхронные итераторы, например, итератор, который возвращает `IAsyncEnumerable/IAsyncEnumerator`, для которого можно применить `await` и `yield`.</span><span class="sxs-lookup"><span data-stu-id="4d804-196">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="4d804-197">Для объектов, которые необходимо удалить, можно использовать `IAsyncDisposable`, который реализовывают различные типы BCL, такие как `Stream` и `Timer`.</span><span class="sxs-lookup"><span data-stu-id="4d804-197">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="4d804-198">Только [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) поддерживает синтаксис `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="4d804-198">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports `await foreach` syntax.</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="4d804-199">Тип: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="4d804-199">Type: SequenceReader</span></span>

<span data-ttu-id="4d804-200">В .NET Core 3.0 добавлен `System.Buffers.SequenceReader`, который можно использовать в качестве модуля чтения для `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="4d804-200">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="4d804-201">Это обеспечивает простой и высокопроизводительный анализ данных `System.IO.Pipelines` с низким уровнем распределения, которые могут пересекать несколько буферов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="4d804-201">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="4d804-202">В следующем примере входные данные `Sequence` разбиваются на допустимые строки `CR/LF` с разделителями:</span><span class="sxs-lookup"><span data-stu-id="4d804-202">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="4d804-203">Тип: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="4d804-203">Type: MetadataLoadContext</span></span>

<span data-ttu-id="4d804-204">Добавлен тип `MetadataLoadContext`, позволяющий считывать метаданные сборки, не влияя на домен приложения вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="4d804-204">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="4d804-205">Сборки считываются как данные, включая сборки, созданные для различных архитектур и платформ, а не для текущей среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d804-205">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="4d804-206">`MetadataLoadContext` перекрывается с <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, который доступен только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d804-206">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="4d804-207">`MetdataLoadContext` доступен в [пакете System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="4d804-207">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="4d804-208">Это пакет .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d804-208">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="4d804-209">`MetadataLoadContext` предоставляет интерфейсы API, подобные типу <xref:System.Runtime.Loader.AssemblyLoadContext>, но не на основе этого типа.</span><span class="sxs-lookup"><span data-stu-id="4d804-209">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="4d804-210">Подобно <xref:System.Runtime.Loader.AssemblyLoadContext> `MetadataLoadContext` обеспечивает загрузку сборок в изолированной вселенной загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="4d804-210">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="4d804-211">Интерфейсы API `MetdataLoadContext` возвращают объекты <xref:System.Reflection.Assembly>, позволяя использовать знакомые API отражения.</span><span class="sxs-lookup"><span data-stu-id="4d804-211">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="4d804-212">Интерфейсы API, ориентированные на выполнение, такие как [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), не разрешены и вызывают исключение InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="4d804-212">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="4d804-213">В следующем примере показано, как найти конкретные типы в сборке, которая реализует данный интерфейс:</span><span class="sxs-lookup"><span data-stu-id="4d804-213">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="4d804-214">Сценарии для `MetadataLoadContext` включают в себя возможности времени разработки, инструменты, используемые во время сборки, и возможности подготовки среды выполнения, в которые должна входить проверка набора сборок в качестве данных. В них есть все блокировки файлов, а после проверки память освобождается.</span><span class="sxs-lookup"><span data-stu-id="4d804-214">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="4d804-215">В `MetadataLoadContext` есть класс сопоставителя, переданный в конструктор.</span><span class="sxs-lookup"><span data-stu-id="4d804-215">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="4d804-216">Заданием сопоставителя является загрузка сборки (`Assembly`) с учетом ее `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="4d804-216">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="4d804-217">Класс сопоставителя является производным от абстрактного класса `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="4d804-217">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="4d804-218">Реализация сопоставителя для сценариев на основе пути входит в состав `PathAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="4d804-218">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="4d804-219">[Тесты MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) демонстрируют множество вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="4d804-219">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="4d804-220">[Тесты сборки](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) — хорошее место для начала.</span><span class="sxs-lookup"><span data-stu-id="4d804-220">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="4d804-221">TLS 1.3 и OpenSSL 1.1.1 в Linux</span><span class="sxs-lookup"><span data-stu-id="4d804-221">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="4d804-222">.NET Core теперь будет использовать преимущества [поддержки TLS 1.3 в OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), когда она станет доступна в данной среде.</span><span class="sxs-lookup"><span data-stu-id="4d804-222">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="4d804-223">Есть несколько преимуществ TLS 1.3 для [команды OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="4d804-223">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="4d804-224">уменьшено время соединения в результате уменьшения количества круговых путей между клиентом и сервером;</span><span class="sxs-lookup"><span data-stu-id="4d804-224">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="4d804-225">улучшена безопасность в результате удаления различных устаревших и небезопасных алгоритмов шифрования и шифрования нескольких подтверждений соединения.</span><span class="sxs-lookup"><span data-stu-id="4d804-225">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="4d804-226">В .NET Core 3.0 (предварительная версия 1) предусмотрена возможность использования **OpenSSL 1.1.1**, **OpenSSL 1.1.0** или **OpenSSL 1.0.2** (зависит от того, какая лучшая версия найдена в системе Linux).</span><span class="sxs-lookup"><span data-stu-id="4d804-226">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="4d804-227">Когда **OpenSSL 1.1.1** доступен, типы SslStream и HttpClient будут применять **TLS 1.3** при использовании `SslProtocols.None` (протоколы системы по умолчанию) при условии, что клиент и сервер поддерживают **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="4d804-227">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="4d804-228">В следующем примере показано, как .NET Core 3.0 (предварительная версия 1) подключается к Ubuntu 18.10 <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="4d804-228">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="4d804-229">Windows и macOS еще не поддерживают **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="4d804-229">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="4d804-230">.NET Core 3.0 будет поддерживать **TLS 1.3** в этих операционных системах, когда поддержка станет доступной.</span><span class="sxs-lookup"><span data-stu-id="4d804-230">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="4d804-231">Шифрование</span><span class="sxs-lookup"><span data-stu-id="4d804-231">Cryptography</span></span>

<span data-ttu-id="4d804-232">Добавлена поддержка шифров **AES-GCM** и **AES-CCM**, реализованных с помощью `System.Security.Cryptography.AesGcm` и `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="4d804-232">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="4d804-233">Эти алгоритмы являются [алгоритмами шифрования с проверкой подлинности с присоединенными данными](https://en.wikipedia.org/wiki/Authenticated_encryption), и первые алгоритмы шифрования с проверкой подлинности добавлены в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4d804-233">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="4d804-234">В следующем коде показано использование шифра **AesGcm** для шифрования и расшифровки случайных данных.</span><span class="sxs-lookup"><span data-stu-id="4d804-234">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="4d804-235">Код для **AesCcm** выглядит почти так же (только имена переменных класса отличаются).</span><span class="sxs-lookup"><span data-stu-id="4d804-235">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="4d804-236">Импорт и экспорт криптографических ключей</span><span class="sxs-lookup"><span data-stu-id="4d804-236">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="4d804-237">.NET Core 3.0 (предварительная версия 1) поддерживает импорт и экспорт асимметричных открытых и закрытых ключей из стандартных форматов, и при этом не нужно использовать сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="4d804-237">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="4d804-238">Все основные типы (RSA, DSA, ECDsa, ECDiffieHellman) поддерживают формат **X.509 SubjectPublicKeyInfo** для открытых ключей и форматы **PKCS#8 PrivateKeyInfo** и **PKCS#8 EncryptedPrivateKeyInfo** для закрытых ключей.</span><span class="sxs-lookup"><span data-stu-id="4d804-238">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="4d804-239">RSA также поддерживает **PKCS#1 RSAPublicKey** и **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="4d804-239">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="4d804-240">Все методы экспорта создают двоичные данные в кодировке DER, а методы импорта выполняют то же самое.</span><span class="sxs-lookup"><span data-stu-id="4d804-240">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="4d804-241">Если ключ хранится в формате PEM в виде текста, вызывающему объекту потребуется выполнить декодирование содержимого в формате base64, прежде чем вызывать метод импорта.</span><span class="sxs-lookup"><span data-stu-id="4d804-241">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="4d804-242">Файлы PKCS#8 можно проверить с помощью класса `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="4d804-242">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="4d804-243">Файлы PFX/PKCS#12 можно проверить и использовать с помощью `System.Security.Cryptography.Pkcs.Pkcs12Info` и `System.Security.Cryptography.Pkcs.Pkcs12Builder` соответственно.</span><span class="sxs-lookup"><span data-stu-id="4d804-243">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="4d804-244">SerialPort для Linux</span><span class="sxs-lookup"><span data-stu-id="4d804-244">SerialPort for Linux</span></span>

<span data-ttu-id="4d804-245">.NET Core 3.0 теперь поддерживает <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> в Linux.</span><span class="sxs-lookup"><span data-stu-id="4d804-245">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="4d804-246">Ранее среда .NET Core поддерживала только использование типа `SerialPort` в Windows.</span><span class="sxs-lookup"><span data-stu-id="4d804-246">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="4d804-247">Дополнительные улучшения BCL</span><span class="sxs-lookup"><span data-stu-id="4d804-247">More BCL Improvements</span></span>

<span data-ttu-id="4d804-248">`Span<T>`, `Memory<T>` и связанные типы, которые впервые появились в .NET Core 2.1, были оптимизированы в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4d804-248">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="4d804-249">Такие распространенные операции, как создание span, создание срезов, анализ и форматирование, теперь работают лучше.</span><span class="sxs-lookup"><span data-stu-id="4d804-249">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="4d804-250">Кроме того, усовершенствованы такие типы, как `String`, чтобы повысить их эффективность при использовании в качестве ключей с `Dictionary<TKey, TValue>` и другими коллекциями.</span><span class="sxs-lookup"><span data-stu-id="4d804-250">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="4d804-251">Для использования этих преимуществ изменения кода не требуются.</span><span class="sxs-lookup"><span data-stu-id="4d804-251">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="4d804-252">Следующие улучшения также являются новшествами в .NET Core 3 (предварительная версия 1):</span><span class="sxs-lookup"><span data-stu-id="4d804-252">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="4d804-253">поддержка Brotli, встроенная в HttpClient;</span><span class="sxs-lookup"><span data-stu-id="4d804-253">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="4d804-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem);</span><span class="sxs-lookup"><span data-stu-id="4d804-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="4d804-255">Unsafe.Unbox;</span><span class="sxs-lookup"><span data-stu-id="4d804-255">Unsafe.Unbox</span></span>
* <span data-ttu-id="4d804-256">CancellationToken.Unregister;</span><span class="sxs-lookup"><span data-stu-id="4d804-256">CancellationToken.Unregister</span></span>
* <span data-ttu-id="4d804-257">сложные арифметические операторы;</span><span class="sxs-lookup"><span data-stu-id="4d804-257">Complex arithmetic operators</span></span>
* <span data-ttu-id="4d804-258">интерфейсы API сокета для поддержки TCP в активном состоянии;</span><span class="sxs-lookup"><span data-stu-id="4d804-258">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="4d804-259">StringBuilder.GetChunks;</span><span class="sxs-lookup"><span data-stu-id="4d804-259">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="4d804-260">синтаксический анализ IPEndPoint;</span><span class="sxs-lookup"><span data-stu-id="4d804-260">IPEndPoint parsing</span></span>
* <span data-ttu-id="4d804-261">RandomNumberGenerator.GetInt32.</span><span class="sxs-lookup"><span data-stu-id="4d804-261">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="4d804-262">Многоуровневая компиляция</span><span class="sxs-lookup"><span data-stu-id="4d804-262">Tiered compilation</span></span>

<span data-ttu-id="4d804-263">[Многоуровневая компиляция](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) по умолчанию включена в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4d804-263">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="4d804-264">Это возможность, благодаря которой среда выполнения более адаптивно использует компилятор JIT для повышения производительности при запуске и максимального увеличения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4d804-264">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="4d804-265">Эта возможность добавлена в качестве возможности, включаемой пользователем в [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/), а затем была включена по умолчанию в [.NET Core 2.2 (предварительная версия 2)](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="4d804-265">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="4d804-266">Затем в выпуске .NET Core 2.2 она была возвращена в состояние возможности, включаемой пользователем.</span><span class="sxs-lookup"><span data-stu-id="4d804-266">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="4d804-267">Поддержка ARM64 Linux</span><span class="sxs-lookup"><span data-stu-id="4d804-267">ARM64 Linux support</span></span>

<span data-ttu-id="4d804-268">В этом выпуске мы добавили поддержку ARM64 для Linux.</span><span class="sxs-lookup"><span data-stu-id="4d804-268">We are adding support for ARM64 for Linux this release.</span></span> <span data-ttu-id="4d804-269">Для контекста мы добавили поддержку ARM32 для Linux в .NET Core 2.1 и Windows в .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="4d804-269">For context, we added support for ARM32 for Linux with .NET Core 2.1 and Windows with .NET Core 2.2.</span></span> <span data-ttu-id="4d804-270">Основной вариант использования для ARM64 в данный момент — это сценарии Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="4d804-270">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="4d804-271">[Образы Docker Alpine, Debian и Ubuntu доступны для .NET Core для ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="4d804-271">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="4d804-272">Дополнительные сведения см. в статье о [состоянии .NET Core ARM64](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="4d804-272">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="4d804-273">Поддержка **ARM64** в Windows еще недоступна.</span><span class="sxs-lookup"><span data-stu-id="4d804-273">**ARM64** Windows support isn't yet available.</span></span>
