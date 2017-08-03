---
title: "Команда dotnet-nuget-delete — CLI .NET Core"
description: "Команда dotnet-nuget-delete удаляет пакет с сервера или из списка."
keywords: "dotnet-nuget-delete, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce6886f2f4cc8cc633cfc61215fe17550f746c91
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-delete"></a>dotnet-nuget delete

## <a name="name"></a>Имя

Команда `dotnet-nuget-delete` удаляет пакет с сервера или из списка.

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка. Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.

## <a name="arguments"></a>Аргументы

`PACKAGE_NAME`

Удаляемый пакет.

`PACKAGE_VERSION`

Версия удаляемого пакета.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

`--non-interactive`

Не запрашивает у пользователя данные или подтверждения.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--force-english-output`

Принудительно отображает выходные данные командной строки на английском языке.

## <a name="examples"></a>Примеры

Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`

