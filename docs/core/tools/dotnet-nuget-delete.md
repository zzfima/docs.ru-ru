---
title: Команда dotnet nuget-delete — CLI .NET Core
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: 1b58136d0bc04947f0a5baba320e5e6b3e45e2f1
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728418"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a>Описание:

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка. Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.

## <a name="arguments"></a>Аргументы

`PACKAGE_NAME`

Имя/идентификатор удаляемого пакета.

`PACKAGE_VERSION`

Версия удаляемого пакета.

## <a name="options"></a>Параметры

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force-english-output`

 Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

`-h|--help`

Выводит краткую справку по команде.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--no-service-endpoint` Не добавляет "api/v2/package" в исходный URL-адрес.

`--non-interactive`

Не запрашивает у пользователя данные или подтверждения.

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force-english-output`

 Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

`-h|--help`

Выводит краткую справку по команде.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--non-interactive`

Не запрашивает у пользователя данные или подтверждения.

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--force-english-output`

 Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

`-h|--help`

Выводит краткую справку по команде.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--non-interactive`

Не запрашивает у пользователя данные или подтверждения.

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

---

## <a name="examples"></a>Примеры

Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
