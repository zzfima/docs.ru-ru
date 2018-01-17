---
title: "Команда dotnet-add reference — CLI .NET Core"
description: "Команду dotnet add reference удобно использовать для добавления ссылок между проектами."
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 9a79468168979a7c89efe48e11175f926e39cf4f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="c6b75-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="c6b75-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c6b75-104">name</span><span class="sxs-lookup"><span data-stu-id="c6b75-104">Name</span></span>

<span data-ttu-id="c6b75-105">`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="c6b75-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c6b75-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c6b75-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="c6b75-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c6b75-107">Description</span></span>

<span data-ttu-id="c6b75-108">Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект.</span><span class="sxs-lookup"><span data-stu-id="c6b75-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="c6b75-109">После запуска этой команды в файл проекта добавляются элементы [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="c6b75-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="c6b75-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c6b75-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c6b75-111">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="c6b75-111">Specifies the project file.</span></span> <span data-ttu-id="c6b75-112">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="c6b75-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="c6b75-113">Добавляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="c6b75-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="c6b75-114">Укажите один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="c6b75-114">Specify one or more projects.</span></span> <span data-ttu-id="c6b75-115">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="c6b75-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="c6b75-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6b75-116">Options</span></span>

`-h|--help`

<span data-ttu-id="c6b75-117">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c6b75-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c6b75-118">Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c6b75-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c6b75-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="c6b75-119">Examples</span></span>

<span data-ttu-id="c6b75-120">Добавление ссылки на проект:</span><span class="sxs-lookup"><span data-stu-id="c6b75-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="c6b75-121">Добавление нескольких ссылок на проекты в проект в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c6b75-121">Add multiple project references to the project in the current directory:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="c6b75-122">Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="c6b75-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
