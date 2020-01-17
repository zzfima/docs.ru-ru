---
title: Установка пакета SDK для .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для разработки приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4a6c8b27812e9f60e52132169dda0464c24abcc2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740562"
---
# <a name="install-the-net-core-sdk"></a>Установка пакета SDK для .NET Core

В этой статье вы узнаете, как установить пакет SDK для .NET Core. Пакет SDK для .NET Core используется для создания приложений и библиотек .NET Core. Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Установка с помощью установщика

В Windows есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:

- [Процессоры x64 (64-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Процессоры x86 (32-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Установка с помощью установщика

В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:

- [Процессоры x64 (64-разрядные)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Установка с помощью диспетчера пакетов

Вы можете установить пакет SDK для .NET Core с помощью множества стандартных диспетчеров пакетов Linux. Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-managers.md).

Установка с помощью диспетчера пакетов поддерживается только в архитектуре x64. Если вы устанавливаете пакет SDK для .NET Core с другой архитектурой, например ARM, следуйте инструкциям по [скачиванию и установке вручную](#download-and-manually-install). См. сведения о поддерживаемых архитектурах в описании [зависимостей и требований .NET Core](dependencies.md).

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

Чтобы извлечь пакет SDK и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core. Затем откройте терминал и выполните приведенные ниже команды.

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.
>
> Вы можете изменить профиль оболочки, чтобы добавить команды окончательно. Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль. Пример:
>
> - **Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Оболочка Korn**: *~/.kshrc* или *.profile*
> - **Оболочка Z**: *~/.zshrc* или *.zprofile*
>
> Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`. Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.
>
> Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>Установка с помощью Visual Studio

Если вы используете Visual Studio для разработки приложений .NET Core, в следующей таблице указана минимальная требуемая версия Visual Studio на основе целевой версии пакета SDK для .NET Core.

| Версия пакета SDK для .NET Core | Версия Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 версии 16.4 или более поздней. |
| 3.0                   | Visual Studio 2019 версии 16.3 или более поздней. |
| 2.2                   | Visual Studio 2017 версии 15.9 или более поздней. |
| 2.1                   | Visual Studio 2017 версии 15.7 или более поздней. |

Если среда Visual Studio уже установлена, вы можете проверить ее версию, выполнив указанные ниже действия.

01. Запустите Visual Studio.
01. Выберите **Справка** > **О Microsoft Visual Studio**.
01. Считайте номер версии из диалогового окна **О программе**.

Visual Studio может установить последнюю пакета SDK для .NET Core и среды выполнения .NET Core.

- [Скачайте Visual Studio.](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

### <a name="select-a-workload"></a>Выбор рабочей нагрузки

При установке или изменении Visual Studio выберите одну или несколько из следующих рабочих нагрузок в зависимости от типа создаваемого приложения:

- рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;
- рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;
- рабочая нагрузка **Разработка для Azure** в разделе **Веб-разработка и облако**;
- рабочая нагрузка **Разработка классических приложений .NET** в разделе **Классические и мобильные**.

[![Windows Visual Studio 2019 с рабочей нагрузкой .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Установка с помощью Visual Studio для Mac

Visual Studio для Mac устанавливает пакет SDK для .NET Core, если выбрана рабочая нагрузка **.NET Core**. Чтобы приступить к разработке в .NET Core на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation). В последнем выпуске .NET Core 3.1 необходимо использовать предварительную версию Visual Studio для Mac 8.4.

[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET Core в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>Установка вместе с Visual Studio Code

Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере. Visual Studio Code доступен для Windows, macOS и Linux.

Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.

01. [Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).
01. [Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Установка с помощью функции автоматизации PowerShell

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Установка с помощью функции автоматизации Bash

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.

```bash
./dotnet-install.sh -c Current
```

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

::: zone pivot="os-windows"

- [Учебник. Hello World](../tutorials/with-visual-studio.md).
- [Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).

::: zone-end

::: zone pivot="os-macos"

- [Учебник. Начало работы с macOS](../tutorials/using-on-mac-vs.md).
- [Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).

::: zone-end

::: zone pivot="os-linux"

- [Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).

::: zone-end
