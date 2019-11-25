---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191820"
---
# <a name="dotnet-sln"></a><span data-ttu-id="51139-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="51139-103">dotnet sln</span></span>

<span data-ttu-id="51139-104">**Эта статья относится к ✓** SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="51139-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="51139-105">name</span><span class="sxs-lookup"><span data-stu-id="51139-105">Name</span></span>

<span data-ttu-id="51139-106">`dotnet sln` — изменяет файл решений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51139-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="51139-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51139-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="51139-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="51139-108">Description</span></span>

<span data-ttu-id="51139-109">Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.</span><span class="sxs-lookup"><span data-stu-id="51139-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="51139-110">Для использования команды `dotnet sln` файл решения должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="51139-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="51139-111">Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="51139-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="51139-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51139-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="51139-113">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="51139-113">The solution file to use.</span></span> <span data-ttu-id="51139-114">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="51139-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="51139-115">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="51139-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="51139-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="51139-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="51139-117">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="51139-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="51139-118">Команды</span><span class="sxs-lookup"><span data-stu-id="51139-118">Commands</span></span>

### `add`

<span data-ttu-id="51139-119">Добавляет один или несколько проектов в файл решений.</span><span class="sxs-lookup"><span data-stu-id="51139-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="51139-120">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51139-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="51139-121">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51139-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="51139-122">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="51139-122">The solution file to use.</span></span> <span data-ttu-id="51139-123">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="51139-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="51139-124">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="51139-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="51139-125">Путь к проекту, который необходимо добавить в решение.</span><span class="sxs-lookup"><span data-stu-id="51139-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="51139-126">Добавьте несколько проектов с разделением пробелами.</span><span class="sxs-lookup"><span data-stu-id="51139-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="51139-127">Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки UNIX/Linux правильно обрабатываются командой `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="51139-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="51139-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="51139-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="51139-129">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="51139-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="51139-130">Поместите проекты в корень решения, и вам не нужно будет создавать папку решения.</span><span class="sxs-lookup"><span data-stu-id="51139-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="51139-131">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="51139-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="51139-132">Путь к папке назначения решения, в которую будут добавлены проекты.</span><span class="sxs-lookup"><span data-stu-id="51139-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="51139-133">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="51139-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="51139-134">Удаляет один или несколько проектов из файла решений.</span><span class="sxs-lookup"><span data-stu-id="51139-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="51139-135">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51139-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="51139-136">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51139-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="51139-137">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="51139-137">The solution file to use.</span></span> <span data-ttu-id="51139-138">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="51139-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="51139-139">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="51139-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="51139-140">Путь к проекту, который необходимо удалить из решения.</span><span class="sxs-lookup"><span data-stu-id="51139-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="51139-141">Удалите несколько проектов с разделением пробелами.</span><span class="sxs-lookup"><span data-stu-id="51139-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="51139-142">Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="51139-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="51139-143">Параметры</span><span class="sxs-lookup"><span data-stu-id="51139-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="51139-144">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="51139-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="51139-145">Перечисляет все проекты в файле решения.</span><span class="sxs-lookup"><span data-stu-id="51139-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="51139-146">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51139-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a><span data-ttu-id="51139-147">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51139-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="51139-148">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="51139-148">The solution file to use.</span></span> <span data-ttu-id="51139-149">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="51139-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="51139-150">Если файлов решений в каталоге несколько, нужно указать один.</span><span class="sxs-lookup"><span data-stu-id="51139-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="51139-151">Параметры</span><span class="sxs-lookup"><span data-stu-id="51139-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="51139-152">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="51139-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="51139-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="51139-153">Examples</span></span>

<span data-ttu-id="51139-154">Добавление проекта C# в решение:</span><span class="sxs-lookup"><span data-stu-id="51139-154">Add a C# project to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

<span data-ttu-id="51139-155">Удаление проекта C# из решения:</span><span class="sxs-lookup"><span data-stu-id="51139-155">Remove a C# project from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

<span data-ttu-id="51139-156">Добавление нескольких проектов C# в решение:</span><span class="sxs-lookup"><span data-stu-id="51139-156">Add multiple C# projects to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="51139-157">Удаление нескольких проектов C# из решения:</span><span class="sxs-lookup"><span data-stu-id="51139-157">Remove multiple C# projects from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="51139-158">Добавление нескольких проектов C# в решение с помощью стандартной маски (только Unix/Linux):</span><span class="sxs-lookup"><span data-stu-id="51139-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

<span data-ttu-id="51139-159">Удаление нескольких проектов C# из решения с помощью стандартной маски (только Unix/Linux):</span><span class="sxs-lookup"><span data-stu-id="51139-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
