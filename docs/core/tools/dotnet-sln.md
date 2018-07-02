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
# <a name="dotnet-sln"></a><span data-ttu-id="89dca-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89dca-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="89dca-104">name</span><span class="sxs-lookup"><span data-stu-id="89dca-104">Name</span></span>

<span data-ttu-id="89dca-105">`dotnet sln` — изменяет файл решений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89dca-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89dca-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="89dca-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="89dca-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="89dca-107">Description</span></span>

<span data-ttu-id="89dca-108">Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.</span><span class="sxs-lookup"><span data-stu-id="89dca-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="89dca-109">Для использования команды `dotnet sln` файл решения должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="89dca-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="89dca-110">Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="89dca-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="89dca-111">Команды</span><span class="sxs-lookup"><span data-stu-id="89dca-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="89dca-112">Добавляет один или несколько проектов в файл решений.</span><span class="sxs-lookup"><span data-stu-id="89dca-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="89dca-113">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="89dca-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="89dca-114">Удаляет один или несколько проектов из файла решений.</span><span class="sxs-lookup"><span data-stu-id="89dca-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="89dca-115">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="89dca-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="89dca-116">Перечисляет все проекты в файле решения.</span><span class="sxs-lookup"><span data-stu-id="89dca-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="89dca-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="89dca-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="89dca-118">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="89dca-118">Solution file to use.</span></span> <span data-ttu-id="89dca-119">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="89dca-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="89dca-120">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="89dca-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="89dca-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="89dca-121">Options</span></span>

`-h|--help`

<span data-ttu-id="89dca-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="89dca-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="89dca-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="89dca-123">Examples</span></span>

<span data-ttu-id="89dca-124">Добавление проекта C# в решение:</span><span class="sxs-lookup"><span data-stu-id="89dca-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="89dca-125">Удаление проекта C# из решения:</span><span class="sxs-lookup"><span data-stu-id="89dca-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="89dca-126">Добавление нескольких проектов C# в решение:</span><span class="sxs-lookup"><span data-stu-id="89dca-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="89dca-127">Удаление нескольких проектов C# из решения:</span><span class="sxs-lookup"><span data-stu-id="89dca-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="89dca-128">Добавление нескольких проектов C# в решение с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="89dca-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="89dca-129">Удаление нескольких проектов C# из решения с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="89dca-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
