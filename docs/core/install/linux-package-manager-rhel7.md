---
title: Установка .NET Core на Linux RHEL 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: bcc41bfcd7c6d03038952e3faaf07952c3deb69d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715538"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="7ff77-103">Диспетчер пакетов RHEL 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="7ff77-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="7ff77-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="7ff77-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="7ff77-105">Версия .NET Core 3.1 пока недоступна для RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="7ff77-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="7ff77-106">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="7ff77-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="7ff77-107">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="7ff77-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="7ff77-108">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="7ff77-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="7ff77-109">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="7ff77-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="7ff77-110">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ff77-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="7ff77-111">В терминале выполните приведенные ниже команды, чтобы включить канал dotnet RHEL 7 и выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="7ff77-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="7ff77-112">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7ff77-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="7ff77-113">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ff77-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="7ff77-114">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="7ff77-114">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="7ff77-115">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="7ff77-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="7ff77-116">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ff77-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="7ff77-117">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="7ff77-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="7ff77-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7ff77-118">See also</span></span>

- [<span data-ttu-id="7ff77-119">Использование .NET Core 3.0 на Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="7ff77-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
