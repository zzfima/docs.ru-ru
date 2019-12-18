---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998891"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="609aa-104">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="609aa-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="609aa-105">В этой статье вы узнаете, как скачать и установить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609aa-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="609aa-106">Среда выполнения .NET Core используется для запуска приложений, созданных с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609aa-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="609aa-107">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="609aa-107">Install with an installer</span></span>

<span data-ttu-id="609aa-108">В Windows есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="609aa-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="609aa-109">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="609aa-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="609aa-110">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="609aa-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="609aa-111">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="609aa-111">Install with an installer</span></span>

<span data-ttu-id="609aa-112">В macOS есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="609aa-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="609aa-113">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="609aa-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="609aa-114">Установка с помощью диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="609aa-114">Install with a package manager</span></span>

<span data-ttu-id="609aa-115">Вы можете установить среду выполнения .NET Core с помощью множества стандартных диспетчеров пакетов Linux.</span><span class="sxs-lookup"><span data-stu-id="609aa-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="609aa-116">Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-manager-rhel7.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="609aa-117">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="609aa-117">Install with PowerShell automation</span></span>

<span data-ttu-id="609aa-118">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="609aa-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="609aa-119">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="609aa-120">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="609aa-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="609aa-121">Вы можете выбрать конкретный выпуск, указав параметр `Channel`.</span><span class="sxs-lookup"><span data-stu-id="609aa-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="609aa-122">Включите параметр `Runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="609aa-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="609aa-123">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="609aa-124">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="609aa-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="609aa-125">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609aa-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="609aa-126">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="609aa-126">Install with bash automation</span></span>

<span data-ttu-id="609aa-127">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="609aa-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="609aa-128">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="609aa-129">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="609aa-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="609aa-130">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="609aa-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="609aa-131">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="609aa-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="609aa-132">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="609aa-133">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="609aa-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="609aa-134">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609aa-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="609aa-135">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="609aa-135">All .NET Core downloads</span></span>

<span data-ttu-id="609aa-136">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="609aa-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="609aa-137">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="609aa-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="609aa-138">Скачиваемые файлы для .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="609aa-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="609aa-139">Скачиваемые файлы для .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="609aa-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="609aa-140">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="609aa-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="609aa-141">Docker</span><span class="sxs-lookup"><span data-stu-id="609aa-141">Docker</span></span>

<span data-ttu-id="609aa-142">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="609aa-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="609aa-143">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="609aa-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="609aa-144">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="609aa-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="609aa-145">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="609aa-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="609aa-146">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="609aa-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="609aa-147">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="609aa-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="609aa-148">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="609aa-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="609aa-149">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="609aa-150">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="609aa-150">Next steps</span></span>

- <span data-ttu-id="609aa-151">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="609aa-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
