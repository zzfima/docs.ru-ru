---
title: Установка .NET Core на openSUSE 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: ae0f6664c0545ceb047cd9b110fe3f26740e5816
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116168"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="7050e-103">Диспетчер пакетов openSUSE 15 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="7050e-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="7050e-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="7050e-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="7050e-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7050e-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="7050e-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="7050e-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="7050e-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="7050e-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="7050e-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="7050e-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="7050e-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="7050e-109">Register the product repository.</span></span>
- <span data-ttu-id="7050e-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="7050e-110">Install required dependencies.</span></span>

<span data-ttu-id="7050e-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="7050e-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="7050e-112">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="7050e-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="7050e-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="7050e-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="7050e-114">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7050e-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="7050e-115">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7050e-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="7050e-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7050e-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="7050e-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7050e-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="7050e-118">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7050e-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="7050e-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="7050e-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="7050e-120">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7050e-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="7050e-121">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7050e-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7050e-122">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="7050e-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
