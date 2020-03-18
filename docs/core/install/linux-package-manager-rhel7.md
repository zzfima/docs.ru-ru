---
title: Установка .NET Core на Linux RHEL 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 4f85ed3da8a434fcd5b6ee88491daf623c3c8b31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76980188"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="10bd9-103">Диспетчер пакетов RHEL 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="10bd9-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="10bd9-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="10bd9-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="10bd9-105">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="10bd9-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="10bd9-106">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="10bd9-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="10bd9-107">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="10bd9-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="10bd9-108">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="10bd9-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="10bd9-109">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10bd9-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="10bd9-110">В терминале выполните приведенные ниже команды, чтобы включить канал dotnet RHEL 7 и выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="10bd9-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="10bd9-111">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="10bd9-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="10bd9-112">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="10bd9-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="10bd9-113">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="10bd9-113">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="10bd9-114">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="10bd9-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="10bd9-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10bd9-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="10bd9-116">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="10bd9-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a><span data-ttu-id="10bd9-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10bd9-117">See also</span></span>

- [<span data-ttu-id="10bd9-118">Использование .NET Core 3.1 на Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="10bd9-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
