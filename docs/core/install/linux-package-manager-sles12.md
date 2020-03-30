---
title: Установка .NET Core на SLES 12 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на SLES 12.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 8358107c682274fc2b75bf72689eaa4b168a86c5
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134220"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="d16b2-103">Диспетчер пакетов SLES 12 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16b2-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="d16b2-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на SLES 12.</span><span class="sxs-lookup"><span data-stu-id="d16b2-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="d16b2-105">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="d16b2-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="d16b2-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="d16b2-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="d16b2-107">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="d16b2-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="d16b2-108">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="d16b2-108">Register the product repository.</span></span>
- <span data-ttu-id="d16b2-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="d16b2-109">Install required dependencies.</span></span>

<span data-ttu-id="d16b2-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="d16b2-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="d16b2-111">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d16b2-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="d16b2-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16b2-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="d16b2-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d16b2-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="d16b2-114">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d16b2-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="d16b2-115">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d16b2-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="d16b2-116">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d16b2-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="d16b2-117">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d16b2-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="d16b2-118">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="d16b2-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="d16b2-119">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d16b2-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="d16b2-120">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d16b2-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d16b2-121">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="d16b2-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d16b2-122">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="d16b2-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="d16b2-123">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d16b2-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d16b2-124">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="d16b2-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
