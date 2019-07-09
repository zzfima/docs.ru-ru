---
title: Команда dotnet nuget push
description: Команда dotnet nuget push отправляет пакет на сервер и публикует его.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4d5efa94c6a4494158aea447be98256d2a307cd6
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539134"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet nuget push` — отправляет пакет на сервер и публикует его.

## <a name="synopsis"></a>Краткий обзор

```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>ОПИСАНИЕ

Команда `dotnet nuget push` отправляет пакет на сервер и публикует его. Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации. См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior). Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.

## <a name="arguments"></a>Аргументы

* **`ROOT`**

  Указывает путь к файлу пакета для отправки.

## <a name="options"></a>Параметры

* **`-d|--disable-buffering`**

  Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.

* **`--force-english-output`**

  Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

* **`-h|--help`**

Выводит краткую справку по команде.

* **`--interactive`**

  Позволяет блокировать команду до выполнения действия пользователем, например аутентификации. Параметр доступен, начиная с пакета SDK для .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  Ключ API для сервера.

* **`-n|--no-symbols`**

  Не передает символы (даже если они присутствуют).

* **`--no-service-endpoint`**

  Не добавляет "api/v2/package" в исходный URL-адрес. Параметр доступен, начиная с пакета SDK для .NET Core 2.1.

* **`-s|--source <SOURCE>`**

  Определяет URL-адрес сервера. Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.

* **`-sk|--symbol-api-key <API_KEY>`**

  Ключ API для сервера символов.

* **`-ss|--symbol-source <SOURCE>`**

  Указывает URL-адрес сервера символов.

* **`-t|--timeout <TIMEOUT>`**

  Указывает время ожидания для передачи на сервер в секундах. Значение по умолчанию — 300 секунд (5 минут). При указании 0 (ноль секунд) применяется значение по умолчанию.

## <a name="examples"></a>Примеры

* Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API:

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `https://customsource`, предоставляя ключ API:

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.

  ```console
  dotnet nuget push foo.nupkg
  ```

* Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд:

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.

  ```console
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > Если эта команда не работает, возможно, это связано с ошибкой, которая существовала в более старых версиях пакета SDK (пакет SDK для .NET Core 2.1 и более ранних версий).
  > Чтобы устранить эту проблему, обновите версию пакета SDK или выполните следующую команду: `dotnet nuget push **/*.nupkg`
