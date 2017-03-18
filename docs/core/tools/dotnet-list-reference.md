---
title: "Команда dotnet-list reference | Документы Майкрософт"
description: "Команду dotnet-list reference удобно использовать для перечисления ссылок между проектами."
keywords: "dotnet-list, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e95aa43bfed78d72ef1ea5f3883ae64e06ffaa99
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-list-reference"></a>dotnet-list reference

## <a name="name"></a>Имя

`dotnet-list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

```
dotnet list [project] reference
dotnet list reference [-h|--help]
```

## <a name="description"></a>Описание

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.

## <a name="arguments"></a>Аргументы

`project`

Файл проекта, для которого требуется вывести список ссылок. Если он не указан, команда будет искать текущий каталог для него.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Перечисление ссылок на проекты для указанного проекта:

`dotnet list app/app.csproj reference`

Перечисление ссылок на проекты для проекта в текущем каталоге:

`dotnet list reference`

