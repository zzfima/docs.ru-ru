---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 06/13/2018
ms.openlocfilehash: a88e22c68f639f2a42e59f9a271e431f04e24a2b
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169148"
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

## <a name="description"></a>Описание

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

> [!NOTE]
> Глобализация — это скорее функция командной оболочки, а не функция CLI. Чтобы успешно развернуть файлы, нужно использовать оболочку, которая поддерживает глобализацию. Дополнительные сведения о глобализации см. в разделе [Википедии](https://en.wikipedia.org/wiki/Glob_(programming)).
