---
title: "Команда dotnet remove reference — CLI .NET Core"
description: "Команду dotnet remove reference удобно использовать для удаления ссылок между проектами."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 7cb84c2dc7fc4d16b00bd6459132390ab80131f3
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Имя

`dotnet remove reference` — удаляет перекрестные ссылки между проектами.

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

