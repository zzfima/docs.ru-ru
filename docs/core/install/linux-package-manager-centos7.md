---
title: Установка .NET Core на CentOS 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на CentOS 7.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 66e78aadf933d3e10b99e3d2c7258733e96164f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920854"
---
# <a name="centos-7-package-manager---install-net-core"></a><span data-ttu-id="2f397-103">Диспетчер пакетов CentOS 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f397-103">CentOS 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="2f397-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на CentOS 7.</span><span class="sxs-lookup"><span data-stu-id="2f397-104">This article describes how to use a package manager to install .NET Core on CentOS 7.</span></span> <span data-ttu-id="2f397-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f397-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="2f397-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="2f397-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="2f397-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="2f397-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="2f397-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="2f397-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="2f397-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="2f397-109">Register the product repository.</span></span>
- <span data-ttu-id="2f397-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="2f397-110">Install required dependencies.</span></span>

<span data-ttu-id="2f397-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="2f397-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="2f397-112">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2f397-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="2f397-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f397-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="2f397-114">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f397-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="2f397-115">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2f397-115">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="2f397-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2f397-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="2f397-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2f397-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="2f397-118">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2f397-118">In your terminal, run the following command.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="2f397-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f397-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="2f397-120">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f397-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="2f397-121">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2f397-121">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2f397-122">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="2f397-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="2f397-123">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="2f397-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="2f397-124">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f397-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="2f397-125">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="2f397-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
