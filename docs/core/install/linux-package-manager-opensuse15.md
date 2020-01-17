---
title: Установка .NET Core на openSUSE 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740670"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>Диспетчер пакетов openSUSE 15 — установка .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на openSUSE 15. Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Регистрация ключа Майкрософт и веб-канала

Перед установкой .NET нужно сделать следующее:

- зарегистрировать ключ Майкрософт;
- зарегистрировать репозиторий продуктов;
- установить необходимые зависимости.

Данную операцию достаточно выполнить один раз для каждого компьютера.

Откройте терминал и выполните приведенные ниже команды.

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a>Ошибка зависимости в .NET Core 3.1

В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**. Используйте следующую команду, чтобы установить правильные зависимости перед установкой .NET Core 3.1 или ASP.NET Core 3.1.

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**. Используйте следующую команду, чтобы установить правильные зависимости перед установкой пакета SDK для .NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a>Установка среды выполнения ASP.NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**. Используйте следующую команду, чтобы установить правильные зависимости перед установкой среды выполнения для ASP.NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core. В терминале выполните приведенную ниже команду.

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**. Используйте следующую команду, чтобы установить правильные зависимости перед установкой среды выполнения для .NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a>Установка других версий

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
