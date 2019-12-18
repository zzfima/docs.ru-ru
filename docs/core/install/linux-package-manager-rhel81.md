---
title: Установка .NET Core на Linux RHEL 8.1 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 8.1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 3ef639d5b76e81856ec8370d10e098c455ca8b3d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998915"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="c37bd-103">Диспетчер пакетов RHEL 8.1 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="c37bd-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="c37bd-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="c37bd-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="c37bd-105">Версия .NET Core 3.1 пока недоступна для RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="c37bd-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="c37bd-106">RHEL 8.0 не включает в себя .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c37bd-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="c37bd-107">Используйте команду `yum upgrade` для обновления до RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="c37bd-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="c37bd-108">RHEL 8.0 не включает в себя .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c37bd-108">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="c37bd-109">Используйте команду `yum upgrade` для обновления до RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="c37bd-109">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="c37bd-110">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="c37bd-110">Register your Red Hat subscription</span></span>

<span data-ttu-id="c37bd-111">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="c37bd-111">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="c37bd-112">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="c37bd-112">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="c37bd-113">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c37bd-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="c37bd-114">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c37bd-114">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="c37bd-115">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c37bd-115">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="c37bd-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c37bd-116">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="c37bd-117">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c37bd-117">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="c37bd-118">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c37bd-118">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="c37bd-119">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="c37bd-119">Install the .NET Core Runtime</span></span>

<span data-ttu-id="c37bd-120">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c37bd-120">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="c37bd-121">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c37bd-121">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="c37bd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c37bd-122">See also</span></span>

- [<span data-ttu-id="c37bd-123">Использование .NET Core 3.0 на Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="c37bd-123">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
