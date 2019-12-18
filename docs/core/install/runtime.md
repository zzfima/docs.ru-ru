---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998891"
---
# <a name="install-the-net-core-runtime"></a>Установка среды выполнения .NET Core

В этой статье вы узнаете, как скачать и установить среду выполнения .NET Core. Среда выполнения .NET Core используется для запуска приложений, созданных с помощью .NET Core.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Установка с помощью установщика

В Windows есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:

- [Процессоры x64 (64-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Процессоры x86 (32-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Установка с помощью установщика

В macOS есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:

- [Процессоры x64 (64-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Установка с помощью диспетчера пакетов

Вы можете установить среду выполнения .NET Core с помощью множества стандартных диспетчеров пакетов Linux. Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-manager-rhel7.md).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Установка с помощью функции автоматизации PowerShell

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Вы можете выбрать конкретный выпуск, указав параметр `Channel`. Включите параметр `Runtime` для установки среды выполнения. В противном случае сценарий устанавливает пакет [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости. Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Установка с помощью функции автоматизации Bash

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Вы можете выбрать конкретный выпуск, указав параметр `current`. Включите параметр `runtime` для установки среды выполнения. В противном случае сценарий устанавливает пакет [SDK](sdk.md).

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости. Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.

::: zone-end

## <a name="all-net-core-downloads"></a>Все скачиваемые файлы для .NET Core

Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:

- [Скачиваемые файлы для .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Скачиваемые файлы для .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [Скачиваемые файлы для .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [Скачиваемые файлы для .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы. Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.

.NET Core можно выполнять в контейнере Docker. Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/). Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.

Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев. Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.

Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Следующие шаги

- [Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md).
