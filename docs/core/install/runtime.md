---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca55b8fab4aa9ca9f7e308cce57181e2c7e89f4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397965"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="9fca4-104">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="9fca4-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="9fca4-105">В этой статье вы узнаете, как скачать и установить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="9fca4-106">Среда выполнения .NET Core используется для запуска приложений, созданных с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="9fca4-107">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="9fca4-107">Install with an installer</span></span>

<span data-ttu-id="9fca4-108">В Windows есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="9fca4-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="9fca4-109">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="9fca4-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="9fca4-110">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="9fca4-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="9fca4-111">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="9fca4-111">Install with an installer</span></span>

<span data-ttu-id="9fca4-112">В macOS есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="9fca4-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="9fca4-113">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="9fca4-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="9fca4-114">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="9fca4-114">Download and manually install</span></span>

<span data-ttu-id="9fca4-115">В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fca4-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="9fca4-116">Чтобы установить среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="9fca4-117">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="9fca4-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="9fca4-118">Предполагается, что среда выполнения скачивается в файл `~/Downloads/dotnet-runtime.pkg`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="9fca4-119">Установка с помощью диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="9fca4-119">Install with a package manager</span></span>

<span data-ttu-id="9fca4-120">Вы можете установить среду выполнения .NET Core с помощью множества стандартных диспетчеров пакетов Linux.</span><span class="sxs-lookup"><span data-stu-id="9fca4-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="9fca4-121">Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="9fca4-122">Установка с помощью диспетчера пакетов поддерживается только в архитектуре x64.</span><span class="sxs-lookup"><span data-stu-id="9fca4-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="9fca4-123">Если вы устанавливаете среду выполнения .NET Core с другой архитектурой, например ARM, следуйте инструкциям на странице [Загрузка и установка вручную](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="9fca4-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="9fca4-124">См. сведения о поддерживаемых архитектурах в описании [зависимостей и требований .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="9fca4-125">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="9fca4-125">Download and manually install</span></span>

<span data-ttu-id="9fca4-126">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="9fca4-127">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="9fca4-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="9fca4-128">Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.</span><span class="sxs-lookup"><span data-stu-id="9fca4-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="9fca4-129">Вы можете изменить профиль оболочки, чтобы добавить команды окончательно.</span><span class="sxs-lookup"><span data-stu-id="9fca4-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="9fca4-130">Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль.</span><span class="sxs-lookup"><span data-stu-id="9fca4-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="9fca4-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fca4-131">For example:</span></span>
>
> - <span data-ttu-id="9fca4-132">**Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="9fca4-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="9fca4-133">**Оболочка Korn**: *~/.kshrc* или *.profile*</span><span class="sxs-lookup"><span data-stu-id="9fca4-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="9fca4-134">**Оболочка Z**: *~/.zshrc* или *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="9fca4-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="9fca4-135">Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="9fca4-136">Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="9fca4-137">Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.</span><span class="sxs-lookup"><span data-stu-id="9fca4-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="9fca4-138">Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="9fca4-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="9fca4-139">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fca4-139">Install with PowerShell automation</span></span>

<span data-ttu-id="9fca4-140">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="9fca4-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="9fca4-141">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="9fca4-142">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fca4-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="9fca4-143">Вы можете выбрать конкретный выпуск, указав параметр `Channel`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="9fca4-144">Включите параметр `Runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fca4-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="9fca4-145">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="9fca4-146">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="9fca4-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="9fca4-147">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="9fca4-148">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="9fca4-148">Download and manually install</span></span>

<span data-ttu-id="9fca4-149">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="9fca4-150">Затем создайте каталог в котором будете выполнять установку, например `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="9fca4-151">Наконец, извлеките скачанный ZIP-файл в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="9fca4-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="9fca4-152">По умолчанию команды и приложения .NET Core CLI не будут использовать .NET Core, установленный таким образом.</span><span class="sxs-lookup"><span data-stu-id="9fca4-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="9fca4-153">Необходимо явно выбрать его использование.</span><span class="sxs-lookup"><span data-stu-id="9fca4-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="9fca4-154">Для этого измените переменные среды, с которыми запускается приложение:</span><span class="sxs-lookup"><span data-stu-id="9fca4-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="9fca4-155">Такой подход позволяет установить несколько версий в отдельные расположения, а затем явно выбрать расположение установки, которое должно использовать приложение, запустив приложение с переменными среды, указывающими на это расположение.</span><span class="sxs-lookup"><span data-stu-id="9fca4-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="9fca4-156">Даже если эти переменные среды заданы, .NET Core по-прежнему учитывает глобальное расположение установки по умолчанию при выборе лучшей платформы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="9fca4-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="9fca4-157">По умолчанию обычно это расположение `C:\Program Files\dotnet`, которое используют установщики.</span><span class="sxs-lookup"><span data-stu-id="9fca4-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="9fca4-158">Вы можете указать среде выполнения использовать только пользовательское расположение установки, задав эту переменную среды.</span><span class="sxs-lookup"><span data-stu-id="9fca4-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="9fca4-159">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="9fca4-159">Install with bash automation</span></span>

<span data-ttu-id="9fca4-160">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="9fca4-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="9fca4-161">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="9fca4-162">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fca4-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="9fca4-163">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="9fca4-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="9fca4-164">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fca4-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="9fca4-165">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="9fca4-166">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="9fca4-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="9fca4-167">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fca4-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="9fca4-168">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="9fca4-168">All .NET Core downloads</span></span>

<span data-ttu-id="9fca4-169">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="9fca4-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="9fca4-170">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9fca4-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="9fca4-171">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9fca4-171">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="9fca4-172">Docker</span><span class="sxs-lookup"><span data-stu-id="9fca4-172">Docker</span></span>

<span data-ttu-id="9fca4-173">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="9fca4-173">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="9fca4-174">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="9fca4-174">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="9fca4-175">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="9fca4-175">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="9fca4-176">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="9fca4-176">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="9fca4-177">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9fca4-177">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="9fca4-178">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="9fca4-178">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="9fca4-179">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="9fca4-179">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="9fca4-180">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-180">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fca4-181">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9fca4-181">Next steps</span></span>

- <span data-ttu-id="9fca4-182">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-182">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
