---
title: Использование пакета SDK и средств .NET Core при непрерывной интеграции (CI)
description: Сведения об использовании пакета SDK для .NET Core и входящих в него средств на сервере сборки.
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.openlocfilehash: 0835ffafc6c091c311b03c90f665cbd669cccfe9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43749938"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="2183a-103">Использование пакета SDK и средств .NET Core при непрерывной интеграции (CI)</span><span class="sxs-lookup"><span data-stu-id="2183a-103">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

## <a name="overview"></a><span data-ttu-id="2183a-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="2183a-104">Overview</span></span>

<span data-ttu-id="2183a-105">В этой статье описывается использование пакета SDK для .NET Core и входящих в него средств на сервере сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-105">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="2183a-106">Набор инструментов .NET Core поддерживает два режима: интерактивный (разработчик вводит команды в командной строке) и автоматический (сервер непрерывной интеграции выполняет скрипт сборки).</span><span class="sxs-lookup"><span data-stu-id="2183a-106">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="2183a-107">Команды, параметры, входные и выходные данные совпадают. В этом случае нужно только указать способ получения средств и систему сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="2183a-107">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="2183a-108">В этом документе рассматриваются сценарии ввода в эксплуатацию средства обеспечения непрерывной интеграции, а также рекомендации по разработке и структуре скриптов сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-108">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="2183a-109">Варианты установки для серверов сборки CI</span><span class="sxs-lookup"><span data-stu-id="2183a-109">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="2183a-110">Использование собственных установщиков</span><span class="sxs-lookup"><span data-stu-id="2183a-110">Using the native installers</span></span>

<span data-ttu-id="2183a-111">В macOS, Linux и Windows доступны собственные установщики.</span><span class="sxs-lookup"><span data-stu-id="2183a-111">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="2183a-112">Установщики требуют доступа администратора (sudo) к серверу сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-112">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="2183a-113">Преимущество использования собственного установщика заключается в том, что он устанавливает собственные зависимости, необходимые для выполнения средства.</span><span class="sxs-lookup"><span data-stu-id="2183a-113">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="2183a-114">Кроме того, собственные установщики обеспечивают системную установку пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2183a-114">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="2183a-115">Пользователи macOS должны использовать установщики PKG.</span><span class="sxs-lookup"><span data-stu-id="2183a-115">macOS users should use the PKG installers.</span></span> <span data-ttu-id="2183a-116">В случае с Linux можно выбрать диспетчер пакетов на основе каналов, например apt-get для Ubuntu или yum для CentOS. Кроме того, можно использовать сами пакеты (DEB или RPM).</span><span class="sxs-lookup"><span data-stu-id="2183a-116">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="2183a-117">Для платформ Windows можно использовать установщик MSI.</span><span class="sxs-lookup"><span data-stu-id="2183a-117">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="2183a-118">Последние надежные двоичные файлы можно найти на странице, посвященной [началу работы с .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="2183a-118">The latest stable binaries are found at [Get Started with .NET Core](https://aka.ms/dotnetcoregs).</span></span> <span data-ttu-id="2183a-119">Чтобы использовать последние (возможно, ненадежные) предварительные выпуски средств, воспользуйтесь ссылками в [репозитории GitHub](https://github.com/dotnet/cli#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="2183a-119">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/cli GitHub repository](https://github.com/dotnet/cli#installers-and-binaries).</span></span> <span data-ttu-id="2183a-120">Для дистрибутивов Linux также доступны архивы `tar.gz` (`tarballs`). Используйте вложенные в них скрипты, чтобы установить .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2183a-120">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="2183a-121">Использование скрипта установки</span><span class="sxs-lookup"><span data-stu-id="2183a-121">Using the installer script</span></span>

<span data-ttu-id="2183a-122">Скрипт установки позволяет выполнять установку на сервере сборки без прав администратора. Кроме того, с его помощью очень легко обеспечить автоматизацию.</span><span class="sxs-lookup"><span data-stu-id="2183a-122">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="2183a-123">Скрипт самостоятельно скачивает средство и распаковывает его в стандартную или указанную папку.</span><span class="sxs-lookup"><span data-stu-id="2183a-123">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="2183a-124">Вы также можете указать версию средства, которую следует установить, а также нужно ли установить пакет SDK целиком или только общую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="2183a-124">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="2183a-125">Работу скрипта установки можно автоматизировать в начале процесса сборки. Это позволяет получить и установить требуемую версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2183a-125">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="2183a-126">*Требуемая версия* — это версия пакета SDK, необходимая в проектах для сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-126">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="2183a-127">Этот скрипт позволяет установить пакет SDK в локальном каталоге на сервере, запустить средства из папки установки, а затем выполнить очистку после завершения сборки (очистку также может выполнить сервер непрерывной интеграции).</span><span class="sxs-lookup"><span data-stu-id="2183a-127">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="2183a-128">Это обеспечивает инкапсуляцию и изоляцию процесса сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-128">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="2183a-129">Ссылку на скрипт установки можно найти в справке по [dotnet-install](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2183a-129">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="2183a-130">При использовании скрипта установки собственные зависимости не устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="2183a-130">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="2183a-131">Их необходимо установить вручную, если их нет в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="2183a-131">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="2183a-132">Список предварительных требований см. в [этом репозитории GitHub](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="2183a-132">See the list of prerequisites in the [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) topic.</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="2183a-133">Примеры установки решений CI</span><span class="sxs-lookup"><span data-stu-id="2183a-133">CI setup examples</span></span>

<span data-ttu-id="2183a-134">В этом разделе приведены сведения о ручной настройке с помощью скрипта PowerShell или bash, а также описано несколько решений SaaS для непрерывной интеграции,</span><span class="sxs-lookup"><span data-stu-id="2183a-134">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="2183a-135">таких как [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) и [Visual Studio Team Services](https://docs.microsoft.com/vsts/build-release/index).</span><span class="sxs-lookup"><span data-stu-id="2183a-135">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Visual Studio Team Services Build](https://docs.microsoft.com/vsts/build-release/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="2183a-136">Ручная настройка</span><span class="sxs-lookup"><span data-stu-id="2183a-136">Manual setup</span></span>

<span data-ttu-id="2183a-137">Каждая служба SaaS имеет собственные методы создания и настройки процесса сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-137">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="2183a-138">Если вы используете другое решения SaaS, нежели упомянутые выше, или хотите внести дополнительные изменения, конфигурацию необходимо выполнить вручную.</span><span class="sxs-lookup"><span data-stu-id="2183a-138">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="2183a-139">Как правило, в процессе ручной настройки необходимо получить версию средства (или последнюю сборку) и выполнить скрипт сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-139">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="2183a-140">Вы можете использовать скрипт PowerShell или bash, чтобы настроить команды .NET Core, а также файл проекта, который определяет процесс сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-140">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="2183a-141">Подробные сведения об этих параметрах см. в разделе [Оркестрация сборки](#orchestrating-the-build).</span><span class="sxs-lookup"><span data-stu-id="2183a-141">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="2183a-142">После создания сценария, выполняющего ручную настройку сервера сборки CI, проверьте его на локальном компьютере разработки.</span><span class="sxs-lookup"><span data-stu-id="2183a-142">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="2183a-143">Если проблем со скриптом не возникло, разверните его на сервере сборки CI.</span><span class="sxs-lookup"><span data-stu-id="2183a-143">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="2183a-144">Ниже приведен относительно простой сценарий PowerShell, позволяющий получить пакет SDK для .NET Core и установить его на сервере сборки Windows.</span><span class="sxs-lookup"><span data-stu-id="2183a-144">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="2183a-145">Сведения о реализации процесса сборки следует указать в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="2183a-145">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="2183a-146">Скрипт получает средства, а затем выполняет процесс сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-146">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="2183a-147">Ниже приведен скрипт bash, который выполняет те же действия, что и описанный выше сценарий PowerShell, он выполняется на компьютерах UNIX.</span><span class="sxs-lookup"><span data-stu-id="2183a-147">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="2183a-148">Travis CI</span><span class="sxs-lookup"><span data-stu-id="2183a-148">Travis CI</span></span>

<span data-ttu-id="2183a-149">Средство [Travis CI](https://travis-ci.org/) можно настроить, чтобы установить пакет SDK для .NET Core с помощью языка `csharp` и ключа `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="2183a-149">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="2183a-150">Дополнительные сведения см. в официальной документации Travis CI по [созданию проектов C#, F# или Visual Basic](https://docs.travis-ci.com/user/languages/csharp/).</span><span class="sxs-lookup"><span data-stu-id="2183a-150">See the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) for more information.</span></span> <span data-ttu-id="2183a-151">Обратите внимание, что при доступе к сведениям сообщества Travis CI идентификатор языка `language: csharp` работает для всех языков .NET, в том числе F# и Mono.</span><span class="sxs-lookup"><span data-stu-id="2183a-151">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="2183a-152">Travis CI выполняет в *матрице сборки* как задания macOS (OS X 10.11, OS X 10.12), так и задания Linux (Ubuntu 14.04). Вы можете указать сочетание среды выполнения, окружения, а также исключений и включений, чтобы охватить свои сочетания сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="2183a-152">Travis CI runs both macOS (OS X 10.11, OS X 10.12) and Linux (Ubuntu 14.04) jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="2183a-153">Дополнительные сведения см. в [примере .travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml) и статье о [настройке сборки](https://docs.travis-ci.com/user/customizing-the-build) в документации по Travis CI.</span><span class="sxs-lookup"><span data-stu-id="2183a-153">See the [.travis.yml example](https://github.com/dotnet/docs/blob/master/.travis.yml) file and [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) in the Travis CI docs for more information.</span></span> <span data-ttu-id="2183a-154">Средства на основе MSBuild включают среды выполнения LTS (1.0.x) и текущие среды выполнения (1.1.x). Установив этот пакет SDK, вы получите все необходимые компоненты сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-154">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="2183a-155">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="2183a-155">AppVeyor</span></span>

<span data-ttu-id="2183a-156">Средство [AppVeyor](https://www.appveyor.com/) устанавливает рабочий образ сборки `Visual Studio 2017` с пакетом SDK для .NET Core 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="2183a-156">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="2183a-157">Но также доступны и другие образы сборки с разными версиями пакета SDK для .NET Core. Дополнительные сведения см. в [примере appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) и [разделе о рабочих образах сборки](https://www.appveyor.com/docs/build-environment/#build-worker-images) в документации по AppVeyor.</span><span class="sxs-lookup"><span data-stu-id="2183a-157">Other build images with different versions of the .NET Core SDK are available; see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) topic in the AppVeyor docs for more information.</span></span>

<span data-ttu-id="2183a-158">Двоичные файлы пакета SDK для .NET Core загружаются в подкаталог и распаковываются в нем с помощью скрипта установки. Затем они добавляются в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="2183a-158">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="2183a-159">Добавьте матрицу сборки, чтобы выполнить тесты интеграции с разными версиями пакета SDK для .NET Core:</span><span class="sxs-lookup"><span data-stu-id="2183a-159">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="visual-studio-team-services-vsts"></a><span data-ttu-id="2183a-160">Visual Studio Team Services (VSTS)</span><span class="sxs-lookup"><span data-stu-id="2183a-160">Visual Studio Team Services (VSTS)</span></span>

<span data-ttu-id="2183a-161">Настройте Visual Studio Team Services, чтобы создать проекты .NET Core, используя один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="2183a-161">Configure Visual Studio Team Services (VSTS) to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="2183a-162">Выполнение скрипта из раздела [Ручная настройка](#manual-setup) с использованием собственных команд.</span><span class="sxs-lookup"><span data-stu-id="2183a-162">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="2183a-163">Создание сборки, состоящей из нескольких встроенных задач сборки VSTS, которые используют средства .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2183a-163">Create a build composed of several VSTS built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="2183a-164">Оба решения допустимые.</span><span class="sxs-lookup"><span data-stu-id="2183a-164">Both solutions are valid.</span></span> <span data-ttu-id="2183a-165">С помощью скрипта ручной настройки можно управлять версиями средства, полученными в процессе сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-165">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="2183a-166">Сборка выполняется с помощью скрипта, который необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="2183a-166">The build is run from a script that you must create.</span></span> <span data-ttu-id="2183a-167">В этом разделе описывается только создание вручную.</span><span class="sxs-lookup"><span data-stu-id="2183a-167">This topic only covers the manual option.</span></span> <span data-ttu-id="2183a-168">Дополнительные сведения о создании сборки с помощью задач сборки VSTS см. в статье [Непрерывная интеграция и развертывание](https://docs.microsoft.com/vsts/build-release/index).</span><span class="sxs-lookup"><span data-stu-id="2183a-168">For more information on composing a build with VSTS build tasks, visit the VSTS [Continuous integration and deployment](https://docs.microsoft.com/vsts/build-release/index) topic.</span></span>

<span data-ttu-id="2183a-169">Чтобы использовать скрипт ручной настройки в VSTS, создайте определение сборки и укажите скрипт, выполняющий этап сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-169">To use a manual setup script in VSTS, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="2183a-170">Это можно сделать с помощью пользовательского интерфейса VSTS:</span><span class="sxs-lookup"><span data-stu-id="2183a-170">This is accomplished using the VSTS user interface:</span></span>

1. <span data-ttu-id="2183a-171">Сначала создайте определение сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-171">Start by creating a new build definition.</span></span> <span data-ttu-id="2183a-172">Когда появится окно определения типа создаваемой сборки, выберите параметр **Пусто**.</span><span class="sxs-lookup"><span data-stu-id="2183a-172">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![Выбор пустого определения сборки](./media/using-ci-with-cli/screen1.png)

1. <span data-ttu-id="2183a-174">После настройки репозитория сборки откроется окно "Определения сборок".</span><span class="sxs-lookup"><span data-stu-id="2183a-174">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="2183a-175">Выберите **Добавить шаг сборки**:</span><span class="sxs-lookup"><span data-stu-id="2183a-175">Select **Add build step**:</span></span>

   ![Добавление шага сборки](./media/using-ci-with-cli/screen2.png)

1. <span data-ttu-id="2183a-177">После этого откроется **каталог задач**.</span><span class="sxs-lookup"><span data-stu-id="2183a-177">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="2183a-178">В нем содержатся задачи, используемые в сборке.</span><span class="sxs-lookup"><span data-stu-id="2183a-178">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="2183a-179">Так как у вас есть скрипт, нажмите кнопку **Добавить** рядом с параметром **PowerShell: Запуск скрипта PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2183a-179">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![Добавление этапа сценария PowerShell](./media/using-ci-with-cli/screen3.png)

1. <span data-ttu-id="2183a-181">Настройте сервер сборки.</span><span class="sxs-lookup"><span data-stu-id="2183a-181">Configure the build step.</span></span> <span data-ttu-id="2183a-182">Добавьте скрипт из репозитория, для которого выполняется сборка:</span><span class="sxs-lookup"><span data-stu-id="2183a-182">Add the script from the repository that you're building:</span></span>

   ![Указание выполняемого сценария PowerShell](./media/using-ci-with-cli/screen4.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="2183a-184">Оркестрация сборки</span><span class="sxs-lookup"><span data-stu-id="2183a-184">Orchestrating the build</span></span>

<span data-ttu-id="2183a-185">Большая часть статьи посвящена тому, как получить средства .NET Core и настроить различные службы CI. Оркестрация или *фактическое создание* кода с помощью .NET Core до этого момента не упоминались.</span><span class="sxs-lookup"><span data-stu-id="2183a-185">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="2183a-186">Способ структурирования процесса сборки зависит от многих факторов, которые нельзя здесь описать в общем виде.</span><span class="sxs-lookup"><span data-stu-id="2183a-186">The choices on how to structure the build process depend on many factors that cannot be covered in a general way here.</span></span> <span data-ttu-id="2183a-187">Дополнительные сведения об оркестрации сборок на основе каждой упомянутой в этой статье технологии, а также ресурсы и примеры см. в документации по [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) и [VSTS](https://docs.microsoft.com/vsts/build-release/index).</span><span class="sxs-lookup"><span data-stu-id="2183a-187">Explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [VSTS](https://docs.microsoft.com/vsts/build-release/index) for more information on orchestrating your builds with each technology.</span></span>

<span data-ttu-id="2183a-188">Два принципиальных подхода структурирования процесса сборки кода .NET Core с использованием средств .NET Core заключаются в использовании MSBuild напрямую или с помощью программ командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2183a-188">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="2183a-189">Выберите подход, который проще и удобнее для вас.</span><span class="sxs-lookup"><span data-stu-id="2183a-189">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="2183a-190">MSBuild предоставляет возможность представить процесс сборки в виде задач и целевых объектов, но сложность этого подхода заключается в необходимости изучения синтаксиса файла проекта MSBuild.</span><span class="sxs-lookup"><span data-stu-id="2183a-190">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="2183a-191">Подход с использованием программ командной строки .NET Core, возможно, проще, но в этом случае следует написать логику оркестрации на языке написания скриптов, например `bash` или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2183a-191">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="2183a-192">См. также</span><span class="sxs-lookup"><span data-stu-id="2183a-192">See also</span></span>

* [<span data-ttu-id="2183a-193">Начало работы с .NET Core</span><span class="sxs-lookup"><span data-stu-id="2183a-193">Ubuntu acquisition steps</span></span>](https://www.microsoft.com/net/core#linuxubuntu)
