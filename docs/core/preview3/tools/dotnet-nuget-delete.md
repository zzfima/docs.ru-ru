---
title: "Команда dotnet-nuget-delete | Пакет SDK для .NET Core"
description: "Команда dotnet-nuget-delete удаляет пакет с сервера или из списка."
keywords: "dotnet-nuget-delete, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
manager: wpickett
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: a338f91d33347d48eefe572ea61da5d58d5c639a

---

#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Имя 
Команда `dotnet-nuget-delete` удаляет пакет с сервера или из списка. 

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget delete [<package_name> <package_version>] 
    [--help] [--source] [--non-interactive] 
    [--api-key] [--force-english-output] [--verbosity] [--config-file]`

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

`--verbosity <LEVEL>`

Отображает эти сведения в выходных данных. Доступные уровни: `normal`, `quiet` или `detailed`.

`--config-file <FILE>`

Файл конфигурации NuGet используется специально для этой команды, заменяя другие файлы конфигурации, обнаруженные стандартным процессом поиска и построения цепочки. Путь может быть как абсолютным, так и относительным.
См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](https://docs.nuget.org/ndocs/consume-packages/configuring-nuget-behavior). 

## <a name="examples"></a>Примеры

Удаляет пакет MyPackage версии 1.0:

`dotnet nuget delete MyPackage 1.0` 

Удаляет пакет MyPackage версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

Удаляет пакет MyPackage версии 1.0, указав собственный файл конфигурации *./config/My.Config*:

`dotnet nuget delete MyPackage 1.0 --config-file ./config/My.Config`

Удаляет пакет MyPackage версии 1.0 с максимальным уровнем детализации:

`dotnet nuget delete MyPackage 1.0 --verbosity detailed`



<!--HONumber=Nov16_HO3-->


