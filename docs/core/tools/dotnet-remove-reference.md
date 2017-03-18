---
title: "Команда dotnet-remove reference | Документы Майкрософт"
description: "Команду dotnet-remove reference удобно использовать для удаления ссылок между проектами."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 1f1a364b703c6b83a9b21ee420d62411bf9cd3ec
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-reference"></a>dotnet-remove reference

## <a name="name"></a>Имя

`dotnet-remove reference` — удаляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

```
dotnet remove [project] reference [-f|--framework] <project_references>
dotnet remove reference [-h|--help]
```

## <a name="description"></a>Описание

Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.

## <a name="arguments"></a>Аргументы

`project`

Целевой файл проекта. Если он не указан, команда будет искать текущий каталог для него.

`project_references`

Удаляемые перекрестные ссылки между проектами. Вы можете указать один или несколько проектов. Шаблон глобализации поддерживается в терминалах на основе Unix или Linux.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-f|--framework <FRAMEWORK>`

Удаляет ссылку только при ориентации на конкретную платформу.

## <a name="examples"></a>Примеры

Удаление ссылки на проект из указанного проекта:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Удаление нескольких ссылок на проекты из проекта в текущем каталоге:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Удаление нескольких ссылок на проект с помощью стандартной маски:

`dotnet remove app/app.csproj reference **/*.csproj`
