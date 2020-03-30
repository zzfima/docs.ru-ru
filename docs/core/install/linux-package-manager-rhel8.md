---
title: Установка .NET Core на Linux RHEL 8 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b564a386eb67b6e414a832ad3bca10d3d09022bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134196"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="905d9-103">Диспетчер пакетов RHEL 8 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="905d9-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="905d9-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="905d9-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="905d9-105">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="905d9-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="905d9-106">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="905d9-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="905d9-107">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="905d9-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="905d9-108">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="905d9-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="905d9-109">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="905d9-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="905d9-110">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="905d9-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="905d9-111">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="905d9-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="905d9-112">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="905d9-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="905d9-113">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="905d9-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="905d9-114">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="905d9-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="905d9-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="905d9-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="905d9-116">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="905d9-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="905d9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="905d9-117">See also</span></span>

- [<span data-ttu-id="905d9-118">Использование .NET Core 3.1 на Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="905d9-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
