---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d36909e06bd9a3de0940c4c1b2b9eacbf9cafe7f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740592"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="1559c-104">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="1559c-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="1559c-105">В этой статье вы узнаете, как скачать и установить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1559c-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="1559c-106">Среда выполнения .NET Core используется для запуска приложений, созданных с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1559c-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="1559c-107">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="1559c-107">Install with an installer</span></span>

<span data-ttu-id="1559c-108">В Windows есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="1559c-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="1559c-109">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="1559c-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="1559c-110">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="1559c-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="1559c-111">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="1559c-111">Install with an installer</span></span>

<span data-ttu-id="1559c-112">В macOS есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="1559c-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="1559c-113">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="1559c-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="1559c-114">Установка с помощью диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="1559c-114">Install with a package manager</span></span>

<span data-ttu-id="1559c-115">Вы можете установить среду выполнения .NET Core с помощью множества стандартных диспетчеров пакетов Linux.</span><span class="sxs-lookup"><span data-stu-id="1559c-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="1559c-116">Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="1559c-117">Установка с помощью диспетчера пакетов поддерживается только в архитектуре x64.</span><span class="sxs-lookup"><span data-stu-id="1559c-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="1559c-118">Если вы устанавливаете среду выполнения .NET Core с другой архитектурой, например ARM, следуйте инструкциям на странице [Загрузка и установка вручную](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="1559c-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="1559c-119">См. сведения о поддерживаемых архитектурах в описании [зависимостей и требований .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="1559c-120">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="1559c-120">Download and manually install</span></span>

<span data-ttu-id="1559c-121">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1559c-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="1559c-122">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="1559c-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="1559c-123">Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.</span><span class="sxs-lookup"><span data-stu-id="1559c-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="1559c-124">Вы можете изменить профиль оболочки, чтобы добавить команды окончательно.</span><span class="sxs-lookup"><span data-stu-id="1559c-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="1559c-125">Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль.</span><span class="sxs-lookup"><span data-stu-id="1559c-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="1559c-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="1559c-126">For example:</span></span>
>
> - <span data-ttu-id="1559c-127">**Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="1559c-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="1559c-128">**Оболочка Korn**: *~/.kshrc* или *.profile*</span><span class="sxs-lookup"><span data-stu-id="1559c-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="1559c-129">**Оболочка Z**: *~/.zshrc* или *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="1559c-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="1559c-130">Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`.</span><span class="sxs-lookup"><span data-stu-id="1559c-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="1559c-131">Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="1559c-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="1559c-132">Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.</span><span class="sxs-lookup"><span data-stu-id="1559c-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="1559c-133">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="1559c-133">Install with PowerShell automation</span></span>

<span data-ttu-id="1559c-134">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="1559c-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="1559c-135">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="1559c-136">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1559c-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="1559c-137">Вы можете выбрать конкретный выпуск, указав параметр `Channel`.</span><span class="sxs-lookup"><span data-stu-id="1559c-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="1559c-138">Включите параметр `Runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1559c-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="1559c-139">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="1559c-140">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="1559c-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="1559c-141">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1559c-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="1559c-142">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="1559c-142">Install with bash automation</span></span>

<span data-ttu-id="1559c-143">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="1559c-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="1559c-144">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="1559c-145">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="1559c-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="1559c-146">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="1559c-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="1559c-147">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1559c-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="1559c-148">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="1559c-149">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="1559c-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="1559c-150">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1559c-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="1559c-151">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="1559c-151">All .NET Core downloads</span></span>

<span data-ttu-id="1559c-152">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="1559c-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="1559c-153">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1559c-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="1559c-154">Скачиваемые файлы для .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1559c-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="1559c-155">Скачиваемые файлы для .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1559c-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="1559c-156">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1559c-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="1559c-157">Docker</span><span class="sxs-lookup"><span data-stu-id="1559c-157">Docker</span></span>

<span data-ttu-id="1559c-158">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="1559c-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="1559c-159">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="1559c-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="1559c-160">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="1559c-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="1559c-161">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="1559c-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="1559c-162">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1559c-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="1559c-163">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="1559c-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="1559c-164">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="1559c-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="1559c-165">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1559c-166">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1559c-166">Next steps</span></span>

- <span data-ttu-id="1559c-167">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="1559c-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
