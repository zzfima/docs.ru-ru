---
title: Установка .NET Core на Linux RHEL 8 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 054494a9b77e1c7803e42c947e067d3eb290f73c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78849798"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="14368-103">Диспетчер пакетов RHEL 8 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="14368-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="14368-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="14368-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="14368-105">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="14368-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="14368-106">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="14368-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="14368-107">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="14368-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="14368-108">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="14368-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="14368-109">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14368-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="14368-110">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="14368-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="14368-111">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="14368-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="14368-112">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="14368-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="14368-113">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="14368-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="14368-114">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="14368-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="14368-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14368-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="14368-116">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="14368-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="14368-117">См. также</span><span class="sxs-lookup"><span data-stu-id="14368-117">See also</span></span>

- [<span data-ttu-id="14368-118">Использование .NET Core 3.1 на Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="14368-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
