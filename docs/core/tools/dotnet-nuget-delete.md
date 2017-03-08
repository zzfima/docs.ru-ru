---
title: "Команда dotnet-nuget-delete | Microsoft Docs"
description: "Команда dotnet-nuget-delete удаляет пакет с сервера или из списка."
keywords: "dotnet-nuget-delete, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 2ce157e3f32f3e899245e38bb4520b17be3e0b32
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

## <a name="name"></a>Имя

Команда `dotnet-nuget-delete` удаляет пакет с сервера или из списка. 

## <a name="synopsis"></a>Краткий обзор

```
dotnet nuget delete [<package_name> <package_version>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet nuget delete` удаляет пакет с сервера или из списка. На сайте NuGet.org команда удаляет пакет из списка.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Поддерживаемые URL-адреса для NuGet.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`. Для частных каналов замените имя узла (например, `%hostname%/api/v3`).

`--non-interactive`

Не запрашивает данные или подтверждения, предоставляемые пользователем.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--force-english-output`

Принудительно отображает выходные данные командной строки на английском языке.

## <a name="examples"></a>Примеры

Удаляет пакет MyPackage версии 1.0:

`dotnet nuget delete MyPackage 1.0` 

Удаляет пакет MyPackage версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

