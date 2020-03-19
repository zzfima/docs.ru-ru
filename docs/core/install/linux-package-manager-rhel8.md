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
# <a name="rhel-8-package-manager---install-net-core"></a>Диспетчер пакетов RHEL 8 — установка .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.

## <a name="register-your-red-hat-subscription"></a>Регистрация подписки Red Hat

Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat. Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a>См. также

- [Использование .NET Core 3.1 на Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
