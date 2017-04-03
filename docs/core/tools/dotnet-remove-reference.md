---
title: "Команда dotnet-remove reference — CLI .NET Core | Документы Майкрософт"
description: "Команду dotnet-remove reference удобно использовать для удаления ссылок между проектами."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 22db4037195afa2c49ef038832e09a99c6a0d54e
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-remove-reference"></a>dotnet-remove reference

## <a name="name"></a>Имя

`dotnet-remove reference` — удаляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Описание

Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Файл целевого проекта. Если он не указан, команда ищет текущий каталог для него.

`PROJECT_REFERENCES`

Удаляемые перекрестные ссылки между проектами (P2P). Вы можете указать один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-f|--framework <FRAMEWORK>`

Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).

## <a name="examples"></a>Примеры

Удаление ссылки на проект из указанного проекта:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Удаление нескольких ссылок на проекты из проекта в текущем каталоге:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:

`dotnet remove app/app.csproj reference **/*.csproj`

