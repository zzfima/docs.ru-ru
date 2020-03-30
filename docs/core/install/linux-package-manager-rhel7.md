---
title: Установка .NET Core на Linux RHEL 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: d1f1372b32c7b2471a96492d48aab5533dadb64a
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134206"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="84bf5-103">Диспетчер пакетов RHEL 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="84bf5-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="84bf5-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="84bf5-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="84bf5-105">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="84bf5-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="84bf5-106">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="84bf5-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="84bf5-107">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="84bf5-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="84bf5-108">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="84bf5-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="84bf5-109">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="84bf5-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="84bf5-110">В терминале выполните приведенные ниже команды, чтобы включить канал dotnet RHEL 7 и выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="84bf5-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="84bf5-111">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="84bf5-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="84bf5-112">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="84bf5-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="84bf5-113">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="84bf5-113">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="84bf5-114">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="84bf5-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="84bf5-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="84bf5-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="84bf5-116">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="84bf5-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a><span data-ttu-id="84bf5-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84bf5-117">See also</span></span>

- [<span data-ttu-id="84bf5-118">Использование .NET Core 3.1 на Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="84bf5-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
