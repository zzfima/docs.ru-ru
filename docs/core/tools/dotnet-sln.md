---
title: Команда dotnet sln — CLI .NET Core
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 65ae402ef5519863886c8cf833598f5314b4bdad
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207820"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet sln` — изменяет файл решений .NET Core.

## <a name="synopsis"></a>Краткий обзор

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Описание:

Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.

Для использования команды `dotnet sln` файл решения должен уже существовать. Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:

```
dotnet new sln
```

## <a name="commands"></a>Команды

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

Добавляет один или несколько проектов в файл решений. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

Удаляет один или несколько проектов из файла решений. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

`list`

Перечисляет все проекты в файле решения.

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
