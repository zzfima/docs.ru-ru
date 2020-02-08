---
title: Установка .NET Core на Debian 9 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Debian 9.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 32b152ff9be5135cf0ca7f8914bc9ee4f78000be
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920850"
---
# <a name="debian-9-package-manager---install-net-core"></a><span data-ttu-id="f677d-103">Диспетчер пакетов Debian 9 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="f677d-103">Debian 9 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f677d-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на Debian 9.</span><span class="sxs-lookup"><span data-stu-id="f677d-104">This article describes how to use a package manager to install .NET Core on Debian 9.</span></span> <span data-ttu-id="f677d-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f677d-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="f677d-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="f677d-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="f677d-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="f677d-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f677d-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="f677d-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="f677d-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="f677d-109">Register the product repository.</span></span>
- <span data-ttu-id="f677d-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="f677d-110">Install required dependencies.</span></span>

<span data-ttu-id="f677d-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="f677d-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f677d-112">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f677d-112">Open a terminal and run the following commands.</span></span>

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f677d-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="f677d-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="f677d-114">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f677d-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f677d-115">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f677d-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f677d-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f677d-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f677d-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f677d-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f677d-118">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f677d-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f677d-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="f677d-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="f677d-120">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f677d-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f677d-121">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f677d-121">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f677d-122">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="f677d-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f677d-123">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="f677d-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="f677d-124">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f677d-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f677d-125">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="f677d-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
