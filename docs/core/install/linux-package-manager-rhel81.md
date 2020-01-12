---
title: Установка .NET Core на Linux RHEL 8.1 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 8.1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714379"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="dbf12-103">Диспетчер пакетов RHEL 8.1 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="dbf12-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="dbf12-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="dbf12-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="dbf12-105">Версия .NET Core 3.1 пока недоступна для RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="dbf12-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="dbf12-106">RHEL 8.0 не включает в себя .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="dbf12-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="dbf12-107">Используйте команду `yum upgrade` для обновления до RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="dbf12-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="dbf12-108">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="dbf12-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="dbf12-109">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="dbf12-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="dbf12-110">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="dbf12-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="dbf12-111">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="dbf12-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="dbf12-112">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dbf12-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="dbf12-113">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="dbf12-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="dbf12-114">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dbf12-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="dbf12-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dbf12-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="dbf12-116">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="dbf12-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="dbf12-117">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="dbf12-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="dbf12-118">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dbf12-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="dbf12-119">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="dbf12-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="dbf12-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dbf12-120">See also</span></span>

- [<span data-ttu-id="dbf12-121">Использование .NET Core 3.0 на Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="dbf12-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
