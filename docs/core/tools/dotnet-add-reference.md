---
title: "Команда dotnet-add reference | Документы Майкрософт"
description: "Команду dotnet-add reference удобно использовать для добавления ссылок между проектами."
keywords: "dotnet-add, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 7d23377244cfe60730b50bd247209de6e90bec70
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>Имя

`dotnet-add reference` — добавляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

```
dotnet add [project] reference [-f|--framework] <project_references>
dotnet add reference [-h|--help]
```

## <a name="description"></a>Описание

Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект. После запуска этой команды в файл проекта добавляются фрагменты [`<ProjectReference>`](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items).

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Аргументы

`project`

Целевой файл проекта. Если он не указан, команда будет искать текущий каталог для него.

`project_references`

Добавляемые перекрестные ссылки между проектами. Вы можете указать один или несколько проектов. Стандартная маска поддерживается в терминалах на основе Unix или Linux.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-f|--framework <FRAMEWORK>`

Добавляет ссылки на проекты только при ориентации на конкретную платформу.

## <a name="examples"></a>Примеры

Добавление ссылки на проект:

`dotnet add app/app.csproj reference lib/lib.csproj`

Добавление нескольких ссылок на проект:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`
