---
title: Установка .NET Core на Linux RHEL 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: f17a410ccea1ef4dec32de1d80ef6aac889aa6f3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998909"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="df707-103">Диспетчер пакетов RHEL 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="df707-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="df707-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="df707-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="df707-105">Версия .NET Core 3.1 пока недоступна для RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="df707-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="df707-106">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="df707-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="df707-107">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="df707-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="df707-108">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="df707-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="df707-109">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="df707-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="df707-110">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df707-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="df707-111">В терминале выполните приведенные ниже команды, чтобы включить канал dotnet RHEL 7 и выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="df707-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="df707-112">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="df707-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="df707-113">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="df707-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="df707-114">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="df707-114">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="df707-115">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="df707-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="df707-116">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df707-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="df707-117">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="df707-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="df707-118">См. также</span><span class="sxs-lookup"><span data-stu-id="df707-118">See also</span></span>

- [<span data-ttu-id="df707-119">Использование .NET Core 3.0 на Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="df707-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
