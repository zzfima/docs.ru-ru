---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157640"
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

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить среду выполнения.

Чтобы установить среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core. Затем откройте терминал и выполните приведенные ниже команды. Предполагается, что среда выполнения скачивается в файл `~/Downloads/dotnet-runtime.pkg`.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Установка с помощью диспетчера пакетов

Вы можете установить среду выполнения .NET Core с помощью множества стандартных диспетчеров пакетов Linux. Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-managers.md).

Установка с помощью диспетчера пакетов поддерживается только в архитектуре x64. Если вы устанавливаете среду выполнения .NET Core с другой архитектурой, например ARM, следуйте инструкциям на странице [Загрузка и установка вручную](#download-and-manually-install). См. сведения о поддерживаемых архитектурах в описании [зависимостей и требований .NET Core](dependencies.md).

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core. Затем откройте терминал и выполните приведенные ниже команды.

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
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

Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.

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

## <a name="download-and-manually-install"></a>Скачивание и установка вручную

Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core. Затем создайте каталог в котором будете выполнять установку, например `%USERPROFILE%\dotnet`. Наконец, извлеките скачанный ZIP-файл в этот каталог.

По умолчанию команды и приложения .NET Core CLI не будут использовать .NET Core, установленный таким образом. Необходимо явно выбрать его использование. Для этого измените переменные среды, с которыми запускается приложение:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

Такой подход позволяет установить несколько версий в отдельные расположения, а затем явно выбрать расположение установки, которое должно использовать приложение, запустив приложение с переменными среды, указывающими на это расположение.

Даже если эти переменные среды заданы, .NET Core по-прежнему учитывает глобальное расположение установки по умолчанию при выборе лучшей платформы для запуска приложения. По умолчанию обычно это расположение `C:\Program Files\dotnet`, которое используют установщики. Вы можете указать среде выполнения использовать только пользовательское расположение установки, задав эту переменную среды.

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Установка с помощью функции автоматизации Bash

[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора. Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).

Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1. Вы можете выбрать конкретный выпуск, указав параметр `current`. Включите параметр `runtime` для установки среды выполнения. В противном случае сценарий устанавливает пакет [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
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
