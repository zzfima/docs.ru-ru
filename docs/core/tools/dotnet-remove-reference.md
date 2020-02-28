---
title: Команда dotnet remove reference
description: Команду dotnet remove reference удобно использовать для удаления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: fcadf677faaf9281fb019c3c4bb16efc906b1aa1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503620"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="366d7-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="366d7-103">dotnet remove reference</span></span>

<span data-ttu-id="366d7-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="366d7-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="366d7-105">name</span><span class="sxs-lookup"><span data-stu-id="366d7-105">Name</span></span>

<span data-ttu-id="366d7-106">`dotnet remove reference` — удаляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="366d7-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="366d7-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="366d7-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="366d7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="366d7-108">Description</span></span>

<span data-ttu-id="366d7-109">Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.</span><span class="sxs-lookup"><span data-stu-id="366d7-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="366d7-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="366d7-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="366d7-111">Файл целевого проекта.</span><span class="sxs-lookup"><span data-stu-id="366d7-111">Target project file.</span></span> <span data-ttu-id="366d7-112">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="366d7-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="366d7-113">Удаляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="366d7-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="366d7-114">Вы можете указать один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="366d7-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="366d7-115">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="366d7-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="366d7-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="366d7-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="366d7-117">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="366d7-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="366d7-118">Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="366d7-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="366d7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="366d7-119">Examples</span></span>

- <span data-ttu-id="366d7-120">Удаление ссылки на проект из указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="366d7-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="366d7-121">Удаление нескольких ссылок на проекты из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="366d7-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="366d7-122">Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:</span><span class="sxs-lookup"><span data-stu-id="366d7-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
