---
title: "Команда dotnet-add reference — CLI .NET Core"
description: "Команду dotnet-add reference удобно использовать для добавления ссылок между проектами."
keywords: "dotnet-add, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 98491efc183ad62f47275d0832a32dde5899373d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>Имя

`dotnet-add reference` — добавляет перекрестные ссылки между проектами (P2P).

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Описание

Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект. После запуска этой команды в файл проекта добавляются элементы [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает файл проекта. Если он не указан, команда будет искать текущий каталог для него.

`PROJECT_REFERENCES`

Добавляемые перекрестные ссылки между проектами (P2P). Укажите один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-f|--framework <FRAMEWORK>`

Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).

## <a name="examples"></a>Примеры

Добавление ссылки на проект:

`dotnet add app/app.csproj reference lib/lib.csproj`

Добавление нескольких ссылок на проект:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`

