---
title: "Скрипты dotnet-install"
description: "Сведения о скриптах dotnet-install, которые служат для установки средств CLI .NET Core и общей среды выполнения."
keywords: "dotnet-install, скрипты dotnet-install, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.translationtype: HT
ms.sourcegitcommit: b041fbec3ff22157d00af2447e76a7ce242007fc
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.contentlocale: ru-ru
ms.lasthandoff: 09/14/2017

---

# <a name="dotnet-install-scripts-reference"></a>Справка по скриптам dotnet-install

## <a name="name"></a>Имя

`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и средств .NET Core CLI.

## <a name="synopsis"></a>Краткий обзор

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

Mac OS и Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a>Описание

Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и средства .NET Core CLI.

Мы рекомендуем использовать стабильную версию, размещенную на [основном веб-сайте .NET Core](https://dot.net). Прямые пути к скриптам:

* https://dot.net/v1/dotnet-install.sh (bash, UNIX)
* https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)

Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора. Существует два скрипта. Один — скрипт PowerShell, который работает в Windows. Второй — bash-скрипт, который выполняется в Linux и macOS. Оба скрипта выполняют одни и те же функции. Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS. 

Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`. По умолчанию скрипты установки скачивают и устанавливают пакет SDK. Если вы хотите получить только общую среду выполнения, укажите аргумент `--shared-runtime`. 

По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса. Переопределите это поведение по умолчанию, указав аргумент `--no-path`. 

Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

Вы можете установить конкретную версию с помощью аргумента `--version`. Версию следует указывать в виде трехкомпонентного номера (например, 1.0.0-13232). Если она не указана, используется версия `latest`.

## <a name="options"></a>Параметры

`-Channel <CHANNEL>`

Указывает исходный канал для установки. Допустимые значения:

- `Current` — текущий выпуск.
- `LTS` — канал долгосрочной поддержки (текущий поддерживаемый выпуск).
- Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.0` или `1.0`).
- Имя ветви [например, `release/2.0.0`, `release/2.0.0-preview2` или `master` для последней из ветви `master` ("суперсовременные" ночные выпуски)].

Значение по умолчанию — `LTS`. Дополнительные сведения о каналах поддержки .NET см. в документе [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Жизненный цикл поддержки .NET Core).

`-Version <VERSION>`

Представляет определенную версию сборки. Допустимые значения:

- `latest` — последняя сборка в канале (используется с параметром `-Channel`).
- `coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)
- Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`. Пример: `2.0.0-preview2-006120`

Если значение не указано, для параметра `-Version` по умолчанию используется значение `latest`.

`-InstallDir <DIRECTORY>`

Указывает путь установки. Если такого пути нет, создается каталог. Значение по умолчанию — *%LocalAppData%\.dotnet*. Обратите внимание, что двоичные файлы помещаются непосредственно в каталог.

`-Architecture <ARCHITECTURE>`

Архитектура устанавливаемых двоичных файлов .NET Core. Допустимые значения: `auto`, `x64` и `x86`. Значение по умолчанию — `auto`, представляющее текущую используемую архитектуру ОС.

`-SharedRuntime`

Если параметр задан, он ограничивает установку общей средой выполнения. Установка всего пакета SDK не выполняется.

`-DryRun`

Если значение задано, скрипт не будет выполнять установку. Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии CLI .NET Core. Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки. Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.

`-NoPath`

Если значение задано, префикс и каталог установки не экспортируются в путь текущего сеанса. По умолчанию скрипт изменит значение PATH, благодаря этому средства CLI становятся доступными сразу после установки.

`-AzureFeed`

Указывает URL-адрес для веб-канала Azure этого установщика. Изменять это значение не рекомендуется. Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов. (Доступно только для Windows.)

`--verbose`

Отображение сведений о диагностике.

`--help`

Выводит справку для скрипта.

## <a name="examples"></a>Примеры

Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:

Windows:

`./dotnet-install.ps1 -Channel LTS`

Mac OS и Linux:

`./dotnet-install.sh --channel LTS`

Установка последней версии из канала версии 2.0 в указанное расположение:

Windows:

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

Mac OS и Linux:

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

Установка общей среды выполнения версии 1.1.0:

Windows:

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

Mac OS и Linux:

`./dotnet-install.sh --shared-runtime --version 1.1.0`

Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:

Windows:

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

Mac OS и Linux:

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a>См. также

[Выпуски .NET Core](https://github.com/dotnet/core/releases)   
[Архив загрузки пакета SDK и среды выполнения .NET Core](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)

