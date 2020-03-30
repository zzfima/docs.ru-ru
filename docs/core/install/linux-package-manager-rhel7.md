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
# <a name="rhel-7-package-manager---install-net-core"></a>Диспетчер пакетов RHEL 7 — установка .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 7.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Регистрация подписки Red Hat

Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat. Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core. В терминале выполните приведенные ниже команды, чтобы включить канал dotnet RHEL 7 и выполнить установку.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core. В терминале выполните приведенные ниже команды.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core. В терминале выполните приведенные ниже команды.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a>См. также раздел

- [Использование .NET Core 3.1 на Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
