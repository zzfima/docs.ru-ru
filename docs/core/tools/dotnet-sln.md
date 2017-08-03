---
title: "Команда dotnet-sln — CLI .NET Core"
description: "Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их."
keywords: "dotnet-sln, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 04/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 606929fbcafddf47abf5da6d3c8ce97d5af06909
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-sln"></a>dotnet-sln

## <a name="name"></a>Имя

`dotnet-sln` — изменяет файл решений .NET Core.

## <a name="synopsis"></a>Краткий обзор

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.

## <a name="commands"></a>Команды

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

Добавляет один или несколько проектов в файл решений. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

Удаляет один или несколько проектов из файла решений. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

`list`

Перечисляет все проекты в файле решений.

## <a name="arguments"></a>Аргументы

`SOLUTION_NAME`

Используемый файл решений. Если он не указан, команда ищет текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Добавление проекта C# в решение:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Удаление проекта C# из решения:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Добавление нескольких проектов C# в решение:

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

Удаление нескольких проектов C# из решения:

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

Добавление нескольких проектов C# в решение с помощью шаблона глобализации:

`dotnet sln todo.sln add **/*.csproj`

Удаление нескольких проектов C# из решения с помощью шаблона глобализации:

`dotnet sln todo.sln remove **/*.csproj`

