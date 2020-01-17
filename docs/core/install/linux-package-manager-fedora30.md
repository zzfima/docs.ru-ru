---
title: Установка .NET Core на Fedora 30 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Fedora 30.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: bd7a199f551be0c51032510279ee9da74bcf0c7c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740695"
---
# <a name="fedora-30-package-manager---install-net-core"></a><span data-ttu-id="d9496-103">Диспетчер пакетов Fedora 30 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9496-103">Fedora 30 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="d9496-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на Fedora 30.</span><span class="sxs-lookup"><span data-stu-id="d9496-104">This article describes how to use a package manager to install .NET Core on Fedora 30.</span></span> <span data-ttu-id="d9496-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9496-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="d9496-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="d9496-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="d9496-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="d9496-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="d9496-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="d9496-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="d9496-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="d9496-109">Register the product repository.</span></span>
- <span data-ttu-id="d9496-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="d9496-110">Install required dependencies.</span></span>

<span data-ttu-id="d9496-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9496-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="d9496-112">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="d9496-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="d9496-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9496-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="d9496-114">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9496-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="d9496-115">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d9496-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="d9496-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9496-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="d9496-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d9496-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="d9496-118">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d9496-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="d9496-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9496-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="d9496-120">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9496-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="d9496-121">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="d9496-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d9496-122">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="d9496-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
