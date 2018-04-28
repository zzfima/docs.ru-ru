---
title: Команда dotnet remove reference — CLI .NET Core
description: Команду dotnet remove reference удобно использовать для удаления ссылок между проектами.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 0b7fb2788ccc04b54bf02f0387141d501612c16d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="979bf-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="979bf-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="979bf-104">name</span><span class="sxs-lookup"><span data-stu-id="979bf-104">Name</span></span>

<span data-ttu-id="979bf-105">`dotnet remove reference` — удаляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="979bf-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="979bf-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="979bf-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="979bf-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="979bf-107">Description</span></span>

<span data-ttu-id="979bf-108">Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.</span><span class="sxs-lookup"><span data-stu-id="979bf-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="979bf-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="979bf-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="979bf-110">Файл целевого проекта.</span><span class="sxs-lookup"><span data-stu-id="979bf-110">Target project file.</span></span> <span data-ttu-id="979bf-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="979bf-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="979bf-112">Удаляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="979bf-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="979bf-113">Вы можете указать один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="979bf-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="979bf-114">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="979bf-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="979bf-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="979bf-115">Options</span></span>

`-h|--help`

<span data-ttu-id="979bf-116">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="979bf-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="979bf-117">Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="979bf-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="979bf-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="979bf-118">Examples</span></span>

<span data-ttu-id="979bf-119">Удаление ссылки на проект из указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="979bf-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="979bf-120">Удаление нескольких ссылок на проекты из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="979bf-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="979bf-121">Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:</span><span class="sxs-lookup"><span data-stu-id="979bf-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
