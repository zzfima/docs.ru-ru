---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0950f03c0986bde17ae3e2e7170d402ea8222853
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733118"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка. Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.

## <a name="arguments"></a>Аргументы

* **`PACKAGE_NAME`**

  Имя/идентификатор удаляемого пакета.

* **`PACKAGE_VERSION`**

  Версия удаляемого пакета.

## <a name="options"></a>Параметры

* **`--force-english-output`**

  Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`--interactive`**

  Позволяет блокировать команду до выполнения действия пользователем, например аутентификации. Параметр доступен, начиная с пакета SDK для .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  Ключ API для сервера.

* **`--no-service-endpoint`**

  Не добавляет "api/v2/package" в исходный URL-адрес. Параметр доступен, начиная с пакета SDK для .NET Core 2.1.

* **`--non-interactive`**

  Не запрашивает у пользователя данные или подтверждения.

* **`-s|--source <SOURCE>`**

  Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

## <a name="examples"></a>Примеры

* Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
