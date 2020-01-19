---
title: Скрипты dotnet-install
description: Сведения о скриптах dotnet-install, которые служат для установки средств CLI .NET Core и общей среды выполнения.
ms.date: 01/16/2019
ms.openlocfilehash: 765141ae92645db448ac7c9c3448a79b895faac6
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964348"
---
# <a name="dotnet-install-scripts-reference"></a>Справка по скриптам dotnet-install

## <a name="name"></a>name

`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и средств .NET Core CLI.

## <a name="synopsis"></a>Краткий обзор

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

Mac OS и Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a>Описание

Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и средства .NET Core CLI.

Мы рекомендуем использовать стабильную версию, размещенную на [основном веб-сайте .NET Core](https://dot.net). Прямые пути к скриптам:

- <https://dot.net/v1/dotnet-install.sh> (Bash, UNIX);
- <https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows).

Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора. Имеются два скрипта: один для PowerShell (работает в Windows), а второй — bash-скрипт, который работает в Linux и macOS. Оба скрипта выполняют одни и те же функции. Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.

Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`. По умолчанию скрипты установки скачивают и устанавливают пакет SDK. Если вы хотите получить только общую среду выполнения, укажите аргумент `--runtime`.

По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса. Переопределите это поведение по умолчанию, указав аргумент `--no-path`.

Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

Вы можете установить конкретную версию с помощью аргумента `--version`. Версию следует указывать в виде трехкомпонентного номера (например, 1.0.0-13232). Если она не указана, используется версия `latest`.

## <a name="options"></a>Параметры

- **`-Channel <CHANNEL>`**

  Указывает исходный канал для установки. Допустимые значения:

  - `Current` — самый последний выпуск.
  - `LTS` — канал долгосрочной поддержки (самый последний поддерживаемый выпуск).
  - Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.0` или `1.0`).
  - Имя ветви. Например, `release/2.0.0`, `release/2.0.0-preview2` или `master` (для ночных выпусков).

  Значение по умолчанию — `LTS`. Дополнительные сведения о каналах поддержки .NET см. на странице о [политике поддержки .NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- **`-Version <VERSION>`**

  Представляет определенную версию сборки. Допустимые значения:

  - `latest` — последняя сборка в канале (используется с параметром `-Channel`).
  - `coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)
  - Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`. Например, `2.0.0-preview2-006120`.

  Если не указано, `-Version` по умолчанию принимает значение `latest`.

- **`-InstallDir <DIRECTORY>`**

  Указывает путь установки. Если такого пути нет, создается каталог. Значение по умолчанию — *%LocalAppData%\Microsoft\dotnet*. Двоичные файлы помещаются непосредственно в этот каталог.

- **`-Architecture <ARCHITECTURE>`**

  Архитектура устанавливаемых двоичных файлов .NET Core. Допустимые значения: `<auto>`, `amd64`, `x64`, `x86`, `arm64` и `arm`. Значение по умолчанию — `<auto>`, представляющее текущую используемую архитектуру ОС.

- **`-SharedRuntime`**

  > [!NOTE]
  > Этот параметр является устаревшим и может быть удален в будущей версии скрипта. Вместо этого рекомендуется использовать параметр `Runtime`.

  Устанавливаются только двоичные файлы общей среды выполнения; в противном случае устанавливается весь пакет SDK. Это эквивалентно указанию `-Runtime dotnet`.

- **`-Runtime <RUNTIME>`**

  Устанавливается только общая среда выполнения, а не весь пакет SDK. Допустимые значения:

  - `dotnet` — общая среда выполнения `Microsoft.NETCore.App`.
  - `aspnetcore` — общая среда выполнения `Microsoft.AspNetCore.App`.

- **`-DryRun`**

  Если задано, скрипт не будет выполнять установку. Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии .NET Core CLI. Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки. Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.

- **`-NoPath`**

  Если значение задано, папка установки не экспортируется в путь текущего сеанса. По умолчанию скрипт изменит значение PATH, благодаря этому средства CLI становятся доступными сразу после установки.

- **`-Verbose`**

  Отображает сведения о диагностике.

- **`-AzureFeed`**

  Указывает URL-адрес для веб-канала Azure этого установщика. Изменять это значение не рекомендуется. Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.

- **`-UncachedFeed`**

  Позволяет изменять URL-адрес некэшированного веб-канала, используемого этим установщиком. Изменять это значение не рекомендуется.

- **`-NoCdn`**

  Отключает загрузку из [сети доставки содержимого Microsoft Azure (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) и напрямую использует некэшированный веб-канал.

- **`-FeedCredential`**

  Используется в качестве строки запроса для добавления в веб-канал Azure. Позволяет изменять URL-адрес для использования учетных записей хранилища BLOB-объектов, не являющихся общедоступными.

- **`-ProxyAddress`**

  Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов. (Доступно только для Windows.)

- **`ProxyUseDefaultCredentials`**

  Если задано, установщик использует учетные данные текущего пользователя при использовании адреса прокси-сервера. (Доступно только для Windows.)

- **`-SkipNonVersionedFiles`**

  Пропускает установку файлов без версии, таких как *dotnet.exe*, если они уже существуют.

- **`-Help`**

  Выводит справку для скрипта.

## <a name="examples"></a>Примеры

- Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- Установка последней версии из канала версии 2.0 в указанное расположение:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- Установка общей среды выполнения версии 1.1.0:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- Получите и установите скрипт версии 2.1.2 за корпоративным прокси-сервером (только для Windows):

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  Mac OS и Linux:

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>См. также

- [Выпуски .NET Core](https://github.com/dotnet/core/releases)
- [Архив загрузки пакета SDK и среды выполнения .NET Core](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
