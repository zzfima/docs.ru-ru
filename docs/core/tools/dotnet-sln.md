---
title: "Команда dotnet sln — CLI .NET Core"
description: "Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: deb66ff52074630616c7be47f1a9751246db501d
ms.sourcegitcommit: 70dcc89737127e4d5f20500242409b687e51b07e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2018
---
# <a name="dotnet-sln"></a><span data-ttu-id="71285-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="71285-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="71285-104">name</span><span class="sxs-lookup"><span data-stu-id="71285-104">Name</span></span>

<span data-ttu-id="71285-105">`dotnet sln` — изменяет файл решений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71285-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="71285-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="71285-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="71285-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="71285-107">Description</span></span>

<span data-ttu-id="71285-108">Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.</span><span class="sxs-lookup"><span data-stu-id="71285-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="71285-109">Команды</span><span class="sxs-lookup"><span data-stu-id="71285-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="71285-110">Добавляет один или несколько проектов в файл решений.</span><span class="sxs-lookup"><span data-stu-id="71285-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="71285-111">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="71285-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="71285-112">Удаляет один или несколько проектов из файла решений.</span><span class="sxs-lookup"><span data-stu-id="71285-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="71285-113">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="71285-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="71285-114">Перечисляет все проекты в файле решения.</span><span class="sxs-lookup"><span data-stu-id="71285-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="71285-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="71285-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="71285-116">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="71285-116">Solution file to use.</span></span> <span data-ttu-id="71285-117">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="71285-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="71285-118">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="71285-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="71285-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="71285-119">Options</span></span>

`-h|--help`

<span data-ttu-id="71285-120">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="71285-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="71285-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="71285-121">Examples</span></span>

<span data-ttu-id="71285-122">Добавление проекта C# в решение:</span><span class="sxs-lookup"><span data-stu-id="71285-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="71285-123">Удаление проекта C# из решения:</span><span class="sxs-lookup"><span data-stu-id="71285-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="71285-124">Добавление нескольких проектов C# в решение:</span><span class="sxs-lookup"><span data-stu-id="71285-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="71285-125">Удаление нескольких проектов C# из решения:</span><span class="sxs-lookup"><span data-stu-id="71285-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="71285-126">Добавление нескольких проектов C# в решение с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="71285-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="71285-127">Удаление нескольких проектов C# из решения с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="71285-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
