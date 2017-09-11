---
title: "Команда dotnet remove reference — CLI .NET Core"
description: "Команду dotnet remove reference удобно использовать для удаления ссылок между проектами."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 7cb84c2dc7fc4d16b00bd6459132390ab80131f3
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="e80f6-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="e80f6-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e80f6-105">Имя</span><span class="sxs-lookup"><span data-stu-id="e80f6-105">Name</span></span>

<span data-ttu-id="e80f6-106">`dotnet remove reference` — удаляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="e80f6-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e80f6-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e80f6-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="e80f6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e80f6-108">Description</span></span>

<span data-ttu-id="e80f6-109">Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.</span><span class="sxs-lookup"><span data-stu-id="e80f6-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="e80f6-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e80f6-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="e80f6-111">Файл целевого проекта.</span><span class="sxs-lookup"><span data-stu-id="e80f6-111">Target project file.</span></span> <span data-ttu-id="e80f6-112">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="e80f6-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="e80f6-113">Удаляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="e80f6-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="e80f6-114">Вы можете указать один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="e80f6-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="e80f6-115">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="e80f6-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="e80f6-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="e80f6-116">Options</span></span>

`-h|--help`

<span data-ttu-id="e80f6-117">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e80f6-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e80f6-118">Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e80f6-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="e80f6-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="e80f6-119">Examples</span></span>

<span data-ttu-id="e80f6-120">Удаление ссылки на проект из указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="e80f6-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="e80f6-121">Удаление нескольких ссылок на проекты из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e80f6-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="e80f6-122">Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:</span><span class="sxs-lookup"><span data-stu-id="e80f6-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`

