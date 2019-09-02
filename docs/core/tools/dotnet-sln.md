---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 06/13/2018
ms.openlocfilehash: 3f18d6a2851d955d07cecc0cbc4c161cf0ec3e08
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202788"
---
# <a name="dotnet-sln"></a><span data-ttu-id="9d109-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="9d109-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9d109-104">name</span><span class="sxs-lookup"><span data-stu-id="9d109-104">Name</span></span>

<span data-ttu-id="9d109-105">`dotnet sln` — изменяет файл решений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d109-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9d109-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9d109-106">Synopsis</span></span>

```console
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9d109-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="9d109-107">Description</span></span>

<span data-ttu-id="9d109-108">Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.</span><span class="sxs-lookup"><span data-stu-id="9d109-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="9d109-109">Для использования команды `dotnet sln` файл решения должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="9d109-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="9d109-110">Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9d109-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```console
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="9d109-111">Команды</span><span class="sxs-lookup"><span data-stu-id="9d109-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="9d109-112">Добавляет один или несколько проектов в файл решений.</span><span class="sxs-lookup"><span data-stu-id="9d109-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="9d109-113">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="9d109-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="9d109-114">Удаляет один или несколько проектов из файла решений.</span><span class="sxs-lookup"><span data-stu-id="9d109-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="9d109-115">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="9d109-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="9d109-116">Перечисляет все проекты в файле решения.</span><span class="sxs-lookup"><span data-stu-id="9d109-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="9d109-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9d109-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="9d109-118">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="9d109-118">Solution file to use.</span></span> <span data-ttu-id="9d109-119">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="9d109-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="9d109-120">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="9d109-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="9d109-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d109-121">Options</span></span>

`-h|--help`

<span data-ttu-id="9d109-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="9d109-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="9d109-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d109-123">Examples</span></span>

<span data-ttu-id="9d109-124">Добавление проекта C# в решение:</span><span class="sxs-lookup"><span data-stu-id="9d109-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="9d109-125">Удаление проекта C# из решения:</span><span class="sxs-lookup"><span data-stu-id="9d109-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="9d109-126">Добавление нескольких проектов C# в решение:</span><span class="sxs-lookup"><span data-stu-id="9d109-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="9d109-127">Удаление нескольких проектов C# из решения:</span><span class="sxs-lookup"><span data-stu-id="9d109-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="9d109-128">Добавление нескольких проектов C# в решение с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="9d109-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="9d109-129">Удаление нескольких проектов C# из решения с помощью шаблона глобализации:</span><span class="sxs-lookup"><span data-stu-id="9d109-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="9d109-130">Глобализация — это скорее функция командной оболочки, а не функция CLI.</span><span class="sxs-lookup"><span data-stu-id="9d109-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="9d109-131">Чтобы успешно развернуть файлы, нужно использовать оболочку, которая поддерживает глобализацию.</span><span class="sxs-lookup"><span data-stu-id="9d109-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="9d109-132">Дополнительные сведения о глобализации см. в разделе [Википедии](https://en.wikipedia.org/wiki/Glob_(programming)).</span><span class="sxs-lookup"><span data-stu-id="9d109-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
