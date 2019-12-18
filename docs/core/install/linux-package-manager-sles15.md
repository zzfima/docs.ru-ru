---
title: Установка .NET Core на SLES 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на SLES 15.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 5551ce8cffa92d4efb6bbe9db2a4887f4b26cd6e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998903"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="9d446-103">Диспетчер пакетов SLES 15 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="9d446-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9d446-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на SLES 15.</span><span class="sxs-lookup"><span data-stu-id="9d446-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span> <span data-ttu-id="9d446-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d446-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="9d446-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="9d446-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="9d446-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="9d446-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9d446-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="9d446-108">Register the Microsoft key</span></span>
- <span data-ttu-id="9d446-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="9d446-109">register the product repository</span></span>
- <span data-ttu-id="9d446-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="9d446-110">Install required dependencies</span></span>

<span data-ttu-id="9d446-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="9d446-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9d446-112">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="9d446-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9d446-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="9d446-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="9d446-114">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d446-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9d446-115">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="9d446-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9d446-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9d446-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9d446-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9d446-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="9d446-118">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="9d446-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9d446-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="9d446-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="9d446-120">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d446-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9d446-121">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="9d446-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9d446-122">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="9d446-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
