---
title: Установка .NET Core на Ubuntu 19.10 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Ubuntu 19.10.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: aac63ba74a8bfaba63e9d23882c9350a7d3d84f3
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134103"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a><span data-ttu-id="518f2-103">Диспетчер пакетов Ubuntu 19.10 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="518f2-103">Ubuntu 19.10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="518f2-104">В этой статье описывается, как использовать диспетчер пакетов для установки .NET Core на Ubuntu 19.10.</span><span class="sxs-lookup"><span data-stu-id="518f2-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="518f2-105">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="518f2-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="518f2-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="518f2-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="518f2-107">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="518f2-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="518f2-108">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="518f2-108">Register the product repository.</span></span>
- <span data-ttu-id="518f2-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="518f2-109">Install required dependencies.</span></span>

<span data-ttu-id="518f2-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="518f2-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="518f2-111">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="518f2-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="518f2-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="518f2-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="518f2-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518f2-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="518f2-114">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="518f2-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="518f2-115">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-3.1** (Не удалось найти пакет dotnet-sdk-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="518f2-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="518f2-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="518f2-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="518f2-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="518f2-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="518f2-118">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="518f2-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="518f2-119">Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-3.1** (Не удалось найти пакет aspnetcore-runtime-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="518f2-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="518f2-120">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="518f2-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="518f2-121">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518f2-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="518f2-122">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="518f2-122">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="518f2-123">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-runtime-3.1** (Не удалось найти пакет dotnet-runtime-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="518f2-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="518f2-124">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="518f2-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="518f2-125">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="518f2-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="518f2-126">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518f2-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="518f2-127">Ошибка обнаружения</span><span class="sxs-lookup"><span data-stu-id="518f2-127">Unable to locate</span></span>

<span data-ttu-id="518f2-128">Если появляется сообщение об ошибке, похожее на **Unable to locate package {the .NET Core package}** (Не удалось найти пакет {пакет .NET Core}), выполните проведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="518f2-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="518f2-129">Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="518f2-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="518f2-130">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="518f2-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
