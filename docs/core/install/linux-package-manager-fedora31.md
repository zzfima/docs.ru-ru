---
title: Установка .NET Core на Fedora 31 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Fedora 31.
author: thraka
ms.author: adegeo
ms.date: 12/17/2019
ms.openlocfilehash: 25c670694ed2d9e89fe37cedf0b06efd8bc93293
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116954"
---
# <a name="fedora-31-package-manager---install-net-core"></a>Диспетчер пакетов Fedora 31 — установка .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

В этой статье описывается, как использовать диспетчер пакетов для установки .NET Core на Fedora 31. Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Регистрация ключа Майкрософт и веб-канала

Перед установкой .NET нужно сделать следующее:

- зарегистрировать ключ Майкрософт;
- зарегистрировать репозиторий продуктов;
- установить необходимые зависимости.

Данную операцию достаточно выполнить один раз для каждого компьютера.

Откройте терминал и выполните приведенные ниже команды.

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Установка других версий

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
