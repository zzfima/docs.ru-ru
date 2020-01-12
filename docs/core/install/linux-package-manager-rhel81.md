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
# <a name="rhel-81-package-manager---install-net-core"></a>Диспетчер пакетов RHEL 8.1 — установка .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на RHEL 8.1. Версия .NET Core 3.1 пока недоступна для RHEL 8.1.

> [!NOTE]
> RHEL 8.0 не включает в себя .NET Core 3.0. Используйте команду `yum upgrade` для обновления до RHEL 8.1.

## <a name="register-your-red-hat-subscription"></a>Регистрация подписки Red Hat

Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat. Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core. В терминале выполните приведенные ниже команды.

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core. В терминале выполните приведенные ниже команды.

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core. В терминале выполните приведенные ниже команды.

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a>См. также

- [Использование .NET Core 3.0 на Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
