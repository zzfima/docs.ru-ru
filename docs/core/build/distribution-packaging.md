---
title: Упаковка дистрибутивов .NET Core
description: Узнайте, как создавать пакеты .NET Core, присваивать им имена и управлять их версиями для распространения.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: d72677cba1e7685f8e05cf479ec508683dd77b55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394164"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="ad271-103">Упаковка дистрибутивов .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad271-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="ad271-104">Так как .NET Core становится доступным на все большем количестве платформ, полезно знать, как создавать пакеты, присваивать им имена и управлять их версиями.</span><span class="sxs-lookup"><span data-stu-id="ad271-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="ad271-105">Таким образом издатели пакетов смогут обеспечить согласованную работу независимо от платформы, выбранной пользователями для запуска .NET.</span><span class="sxs-lookup"><span data-stu-id="ad271-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="ad271-106">Эта статья пригодится пользователям, которые:</span><span class="sxs-lookup"><span data-stu-id="ad271-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="ad271-107">выполняют сборку .NET Core из исходного кода;</span><span class="sxs-lookup"><span data-stu-id="ad271-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="ad271-108">хотят внести в .NET Core CLI изменения, способные повлиять на итоговый макет или создаваемые пакеты.</span><span class="sxs-lookup"><span data-stu-id="ad271-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="ad271-109">Структура диска</span><span class="sxs-lookup"><span data-stu-id="ad271-109">Disk layout</span></span>

<span data-ttu-id="ad271-110">Установка .NET Core включает несколько компонентов, которые располагаются в файловой системе следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ad271-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
├── packs
│   ├── Microsoft.AspNetCore.App.Ref
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref
│       └── <netstandard version>        (15)
├── shared
│   ├── Microsoft.NETCore.App
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App
│       └── <desktop app version> (7)
└── templates
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="ad271-111">(1) **dotnet**: основное приложение (также называется "мультиплексором") выполняет две функции: активирует среду выполнения для запуска приложения и активирует пакет SDK для отправки в него команд.</span><span class="sxs-lookup"><span data-stu-id="ad271-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="ad271-112">Основное приложение представляет собой исполняемый файл в машинном коде (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="ad271-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="ad271-113">Хотя основное приложение одно, большинство остальных компонентов хранятся в каталогах версий (2, 3, 5, 6).</span><span class="sxs-lookup"><span data-stu-id="ad271-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="ad271-114">Это значит, что в системе могут быть представлены сразу несколько версий, поскольку разные версии компонентов устанавливаются параллельно.</span><span class="sxs-lookup"><span data-stu-id="ad271-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="ad271-115">(2) **host/fxr/\<fxr version>** содержит логику разрешений платформы, используемую основным приложением.</span><span class="sxs-lookup"><span data-stu-id="ad271-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="ad271-116">Основное приложение использует новейшую установленную версию hostfxr.</span><span class="sxs-lookup"><span data-stu-id="ad271-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="ad271-117">Hostfxr отвечает за выбор необходимой среды выполнения при запуске приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="ad271-118">Например, приложение, созданное для среды выполнения .NET Core 2.0.0, использует версию 2.0.5, если версия 2.0.0 недоступна.</span><span class="sxs-lookup"><span data-stu-id="ad271-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="ad271-119">Аналогично hostfxr выбирает соответствующую версию SDK во время разработки.</span><span class="sxs-lookup"><span data-stu-id="ad271-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="ad271-120">(3) **sdk/\<версия пакета sdk>** Пакет SDK (или "инструментарий") — это набор управляемых инструментов, которые используются для написания кода и сборки библиотек и приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="ad271-121">Пакет SDK включает интерфейс командной строки .NET Core (CLI), компиляторы языков с управляемым кодом, MSBuild, а также соответствующие задачи и целевые объекты сборки, NuGet, новые шаблоны проектов и т. д.</span><span class="sxs-lookup"><span data-stu-id="ad271-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="ad271-122">(4) **sdk/NuGetFallbackFolder** содержит кэш пакетов NuGet, которые пакет SDK использует во время операции восстановления, например при выполнении `dotnet restore` или `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="ad271-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="ad271-123">Эта папка используется только в версиях, предшествующих .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ad271-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="ad271-124">Ее невозможно создать из источника, так как она содержит предварительно созданные двоичные ресурсы из `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="ad271-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="ad271-125">Папка **shared** содержит платформы.</span><span class="sxs-lookup"><span data-stu-id="ad271-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="ad271-126">Общая платформа предоставляет набор библиотек в центральном расположении таким образом, что они могут использоваться другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="ad271-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="ad271-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** эта платформа содержит среду выполнения .NET Core и вспомогательные управляемые библиотеки.</span><span class="sxs-lookup"><span data-stu-id="ad271-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="ad271-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** содержит библиотеки ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="ad271-129">Библиотеки в каталоге `Microsoft.AspNetCore.App` разрабатываются и поддерживаются как часть проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="ad271-130">Библиотеки в каталоге `Microsoft.AspNetCore.All` представляют собой подмножество, которое также содержит сторонние библиотеки.</span><span class="sxs-lookup"><span data-stu-id="ad271-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="ad271-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** содержит библиотеки для классических приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="ad271-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="ad271-132">Не используется на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="ad271-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="ad271-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** — это, соответственно, лицензии на .NET Core и на сторонние библиотеки, которые используются в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="ad271-134">(9, 10) **dotnet.1.gz, dotnet** `dotnet.1.gz` — это страница руководства по dotnet.</span><span class="sxs-lookup"><span data-stu-id="ad271-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="ad271-135">`dotnet` представляет собой символическую ссылку на основное приложение dotnet (1).</span><span class="sxs-lookup"><span data-stu-id="ad271-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="ad271-136">Эти файлы устанавливаются в типичные расположения для системной интеграции.</span><span class="sxs-lookup"><span data-stu-id="ad271-136">These files are installed at well known locations for system integration.</span></span>

- <span data-ttu-id="ad271-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** описывают API версии `x.y` .NET Core и ASP.NET Core соответственно.</span><span class="sxs-lookup"><span data-stu-id="ad271-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="ad271-138">Эти пакеты используются при компиляции для этих целевых версий.</span><span class="sxs-lookup"><span data-stu-id="ad271-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="ad271-139">(13) **Microsoft.NETCore.App.Host.\<rid>** содержит собственный двоичный файл для платформы `rid`.</span><span class="sxs-lookup"><span data-stu-id="ad271-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="ad271-140">Этот двоичный файл представляет собой шаблон, используемый при компиляции приложения .NET Core в собственный двоичный файл для этой платформы.</span><span class="sxs-lookup"><span data-stu-id="ad271-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="ad271-141">(14) **Microsoft.WindowsDesktop.App.Ref** описывает API версии `x.y` для классических приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="ad271-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="ad271-142">Эти файлы используются при компиляции для этого целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="ad271-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="ad271-143">Не используется на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="ad271-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="ad271-144">(15) **NETStandard.Library.Ref** описывает API `x.y` netstandard.</span><span class="sxs-lookup"><span data-stu-id="ad271-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="ad271-145">Эти файлы используются при компиляции для этого целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="ad271-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="ad271-146">(16) **/etc/dotnet/install_location** — это файл, содержащий полный путь к папке, в которой находится двоичный файл узла `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="ad271-146">(16) **/etc/dotnet/install_location** is a file that contains the full path to the folder that contains the `dotnet` host binary.</span></span> <span data-ttu-id="ad271-147">Путь может заканчиваться новой строкой.</span><span class="sxs-lookup"><span data-stu-id="ad271-147">The path may be terminated with a newline.</span></span> <span data-ttu-id="ad271-148">Если корневым элементом является `/usr/share/dotnet`, добавлять этот файл не нужно.</span><span class="sxs-lookup"><span data-stu-id="ad271-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="ad271-149">(17) **templates** содержат шаблоны, используемые пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="ad271-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="ad271-150">Например, `dotnet new` находит шаблоны проектов.</span><span class="sxs-lookup"><span data-stu-id="ad271-150">For example, `dotnet new` finds project templates here.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="ad271-151">Рекомендуемые пакеты</span><span class="sxs-lookup"><span data-stu-id="ad271-151">Recommended packages</span></span>

<span data-ttu-id="ad271-152">Управление версиями .NET Core основано на номерах версий компонентов среды выполнения вида `[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="ad271-152">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="ad271-153">Версия пакета SDK использует тот же `[major].[minor]` и имеет независимый номер `[patch]`, отражающий функцию и номер исправления для пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="ad271-153">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="ad271-154">Например: Пакет SDK версии 2.2.302 — это второй выпуск исправления для третьей функции пакета SDK, который поддерживает среду выполнения версии 2.2.</span><span class="sxs-lookup"><span data-stu-id="ad271-154">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="ad271-155">Дополнительные сведения о принципах управления версиями см. в разделе [Общие сведения об управлении версиями .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad271-155">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="ad271-156">Некоторые пакеты содержат часть номера версии в своем имени.</span><span class="sxs-lookup"><span data-stu-id="ad271-156">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="ad271-157">Это позволяет устанавливать определенную версию.</span><span class="sxs-lookup"><span data-stu-id="ad271-157">This allows you to install a specific version.</span></span>
<span data-ttu-id="ad271-158">Остальная часть версии в имя версии не включается.</span><span class="sxs-lookup"><span data-stu-id="ad271-158">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="ad271-159">Это позволяет диспетчеру пакетов операционной системы обновлять пакеты (например, автоматически устанавливать исправления безопасности).</span><span class="sxs-lookup"><span data-stu-id="ad271-159">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="ad271-160">Поддерживаемые диспетчеры пакетов рассчитаны на Linux.</span><span class="sxs-lookup"><span data-stu-id="ad271-160">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="ad271-161">Далее перечислены рекомендуемые пакеты.</span><span class="sxs-lookup"><span data-stu-id="ad271-161">The following lists the recommended packages:</span></span>

- <span data-ttu-id="ad271-162">`dotnet-sdk-[major].[minor]` — устанавливает новейшую версию пакета SDK для конкретной среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ad271-162">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="ad271-163">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-163">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-164">**Пример:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="ad271-164">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="ad271-165">**Содержит:** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="ad271-165">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="ad271-166">**Зависимости:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="ad271-166">**Dependencies:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="ad271-167">`aspnetcore-runtime-[major].[minor]` — устанавливает конкретную среду выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ad271-167">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="ad271-168">**Версия:** \<версия среды выполнения aspnetcore></span><span class="sxs-lookup"><span data-stu-id="ad271-168">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="ad271-169">**Пример:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="ad271-169">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="ad271-170">**Содержит:** (6)</span><span class="sxs-lookup"><span data-stu-id="ad271-170">**Contains:** (6)</span></span>
  - <span data-ttu-id="ad271-171">**Зависимости:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="ad271-171">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="ad271-172">`dotnet-runtime-deps-[major].[minor]` _(Необязательно)_  — устанавливает зависимости для запуска автономных приложений</span><span class="sxs-lookup"><span data-stu-id="ad271-172">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="ad271-173">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-173">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-174">**Пример:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="ad271-174">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="ad271-175">**Зависимости:** _зависимости для конкретного дистрибутива_</span><span class="sxs-lookup"><span data-stu-id="ad271-175">**Dependencies:** _distro specific dependencies_</span></span>

- <span data-ttu-id="ad271-176">`dotnet-runtime-[major].[minor]` — устанавливает конкретную среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ad271-176">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="ad271-177">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-178">**Пример:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="ad271-178">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="ad271-179">**Содержит:** (5)</span><span class="sxs-lookup"><span data-stu-id="ad271-179">**Contains:** (5)</span></span>
  - <span data-ttu-id="ad271-180">**Зависимости:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="ad271-180">**Dependencies:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="ad271-181">`dotnet-hostfxr` — зависимость</span><span class="sxs-lookup"><span data-stu-id="ad271-181">`dotnet-hostfxr` - dependency</span></span>
  - <span data-ttu-id="ad271-182">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-182">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-183">**Пример:** dotnet-hostfxr</span><span class="sxs-lookup"><span data-stu-id="ad271-183">**Example:** dotnet-hostfxr</span></span>
  - <span data-ttu-id="ad271-184">**Содержит:** (2)</span><span class="sxs-lookup"><span data-stu-id="ad271-184">**Contains:** (2)</span></span>
  - <span data-ttu-id="ad271-185">**Зависимости:** `host:<runtime version>+`</span><span class="sxs-lookup"><span data-stu-id="ad271-185">**Dependencies:** `host:<runtime version>+`</span></span>

- <span data-ttu-id="ad271-186">`dotnet-host` — зависимость</span><span class="sxs-lookup"><span data-stu-id="ad271-186">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="ad271-187">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-187">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-188">**Пример:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="ad271-188">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="ad271-189">**Содержит:** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="ad271-189">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="ad271-190">`dotnet-apphost-pack-[major].[minor]` — зависимость</span><span class="sxs-lookup"><span data-stu-id="ad271-190">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="ad271-191">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-192">**Содержит:** (13)</span><span class="sxs-lookup"><span data-stu-id="ad271-192">**Contains:** (13)</span></span>

- <span data-ttu-id="ad271-193">`dotnet-targeting-pack-[major].[minor]` — нацеливание на непоследнюю среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ad271-193">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="ad271-194">**Версия:** \<версия среды выполнения></span><span class="sxs-lookup"><span data-stu-id="ad271-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="ad271-195">**Содержит:** (12)</span><span class="sxs-lookup"><span data-stu-id="ad271-195">**Contains:** (12)</span></span>

- <span data-ttu-id="ad271-196">`aspnetcore-targeting-pack-[major].[minor]` — нацеливание на непоследнюю среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ad271-196">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="ad271-197">**Версия:** \<версия среды выполнения aspnetcore></span><span class="sxs-lookup"><span data-stu-id="ad271-197">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="ad271-198">**Содержит:** (11)</span><span class="sxs-lookup"><span data-stu-id="ad271-198">**Contains:** (11)</span></span>

- <span data-ttu-id="ad271-199">`netstandard-targeting-pack-[major].[minor]` — нацеливание на версию netstandard</span><span class="sxs-lookup"><span data-stu-id="ad271-199">`netstandard-targeting-pack-[major].[minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="ad271-200">**Версия:** \<версия пакета SDK></span><span class="sxs-lookup"><span data-stu-id="ad271-200">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="ad271-201">**Содержит:** (15)</span><span class="sxs-lookup"><span data-stu-id="ad271-201">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="ad271-202">**Версия:** \<версия пакета SDK></span><span class="sxs-lookup"><span data-stu-id="ad271-202">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="ad271-203">**Содержит:** (15)</span><span class="sxs-lookup"><span data-stu-id="ad271-203">**Contains:** (15)</span></span>

<span data-ttu-id="ad271-204">Для использования `dotnet-runtime-deps-[major].[minor]` необходимо понимать _зависимости для конкретных дистрибутивов_.</span><span class="sxs-lookup"><span data-stu-id="ad271-204">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro specific dependencies_.</span></span> <span data-ttu-id="ad271-205">Так как система сборки дистрибутива может наследовать этот пакет автоматически, он является необязательным. В этом случае эти зависимости добавляются прямо в пакет `dotnet-runtime-[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="ad271-205">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="ad271-206">Если содержимое пакета находится в папке, которой присвоена версия, имя пакета `[major].[minor]` совпадает с именем этой папки.</span><span class="sxs-lookup"><span data-stu-id="ad271-206">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="ad271-207">Для всех пакетов, кроме `netstandard-targeting-pack-[major].[minor]`, также обязательно совпадение версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad271-207">For all packages, except the `netstandard-targeting-pack-[major].[minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="ad271-208">Для зависимостей между пакетами должно действовать следующее применимое к версиям правило: _больше или равно_.</span><span class="sxs-lookup"><span data-stu-id="ad271-208">Dependencies between packages should use a _equal or greater than_ version requirement.</span></span> <span data-ttu-id="ad271-209">Например, для `dotnet-sdk-2.2:2.2.401` требуется `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="ad271-209">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="ad271-210">В этом случае пользователь может обновить свою установку с помощью корневого пакета (например, `dnf update dotnet-sdk-2.2`).</span><span class="sxs-lookup"><span data-stu-id="ad271-210">This makes it possible for the user to upgrade their installation via a root package (e.g. `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="ad271-211">Большинство дистрибутивов требуют построения из источника всех артефактов.</span><span class="sxs-lookup"><span data-stu-id="ad271-211">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="ad271-212">Это определенным образом влияет на пакеты:</span><span class="sxs-lookup"><span data-stu-id="ad271-212">This has some impact on the packages:</span></span>

- <span data-ttu-id="ad271-213">Сторонние библиотеки в каталоге `shared/Microsoft.AspNetCore.All` нельзя собрать из исходного хода.</span><span class="sxs-lookup"><span data-stu-id="ad271-213">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="ad271-214">Поэтому эта папка исключена из пакета `aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="ad271-214">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="ad271-215">Папка `NuGetFallbackFolder` заполняется двоичными артефактами с сайта `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="ad271-215">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="ad271-216">Она должна оставаться пустой.</span><span class="sxs-lookup"><span data-stu-id="ad271-216">It should remain empty.</span></span>

<span data-ttu-id="ad271-217">Несколько пакетов `dotnet-sdk` могут предоставлять одни и те же файлы для каталога `NuGetFallbackFolder`.</span><span class="sxs-lookup"><span data-stu-id="ad271-217">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="ad271-218">Чтобы не возникали проблемы с диспетчером пакетов, эти файлы (контрольная сумма, дата изменения и т. д.) должны быть идентичны.</span><span class="sxs-lookup"><span data-stu-id="ad271-218">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="ad271-219">Построение пакетов</span><span class="sxs-lookup"><span data-stu-id="ad271-219">Building packages</span></span>

<span data-ttu-id="ad271-220">Репозиторий [dotnet/source-build](https://github.com/dotnet/source-build) содержит инструкции по созданию архива TAR с исходным кодом пакета SDK для .NET Core и всех его компонентов.</span><span class="sxs-lookup"><span data-stu-id="ad271-220">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="ad271-221">Выход репозитория, построенного из источника, соответствует виду, описанному в первом разделе этой статьи.</span><span class="sxs-lookup"><span data-stu-id="ad271-221">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
