---
title: "Команда dotnet-sln | Документы Майкрософт"
description: "Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их."
keywords: "dotnet-sln, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 84c2a9cab36dcfa76f90d75c83f4988ba441b0a8
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-sln"></a>dotnet-sln

## <a name="name"></a>Имя

`dotnet-sln` — изменяет файл решений .NET Core.

## <a name="synopsis"></a>Краткий обзор

```
dotnet sln [<solution_name>] add <project> <project>
dotnet sln [<solution_name>] add **/**
dotnet sln [<solution_name>] remove <project> <project>
dotnet sln [<solution_name>] remove **/**
dotnet sln [<solution_name>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.

## <a name="commands"></a>Команды

`add <project>`

`add **/*`

Добавляет один или несколько проектов в файл решений. Шаблон глобализации поддерживается в терминалах на основе Unix или Linux.

`remove <project>`

`remove **/*`

Удаляет один или несколько проектов из файла решений. Шаблон глобализации поддерживается в терминалах на основе Unix или Linux.

`list`

Перечисляет все проекты в файле решений.

## <a name="arguments"></a>Аргументы

`solution_name`

Используемый файл решений. Если он не указан, команда будет искать текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Добавление проекта в решение:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Добавление проекта в решение в текущем каталоге:

`dotnet sln add todo-app.csproj`

Удаление проекта из решения:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Добавление нескольких проектов в решение с помощью шаблона глобализации:

`dotnet sln add **/**/*.fsproj`

