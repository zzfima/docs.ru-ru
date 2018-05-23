---
title: Команда dotnet remove reference — CLI .NET Core
description: Команду dotnet remove reference удобно использовать для удаления ссылок между проектами.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 209f1ad62221e8a80efa161354a2c074d74b7c5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="7edcf-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="7edcf-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7edcf-104">name</span><span class="sxs-lookup"><span data-stu-id="7edcf-104">Name</span></span>

<span data-ttu-id="7edcf-105">`dotnet remove reference` — удаляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="7edcf-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7edcf-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7edcf-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="7edcf-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="7edcf-107">Description</span></span>

<span data-ttu-id="7edcf-108">Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.</span><span class="sxs-lookup"><span data-stu-id="7edcf-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="7edcf-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7edcf-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="7edcf-110">Файл целевого проекта.</span><span class="sxs-lookup"><span data-stu-id="7edcf-110">Target project file.</span></span> <span data-ttu-id="7edcf-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="7edcf-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="7edcf-112">Удаляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="7edcf-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="7edcf-113">Вы можете указать один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="7edcf-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="7edcf-114">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="7edcf-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="7edcf-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="7edcf-115">Options</span></span>

`-h|--help`

<span data-ttu-id="7edcf-116">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7edcf-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7edcf-117">Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="7edcf-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="7edcf-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="7edcf-118">Examples</span></span>

<span data-ttu-id="7edcf-119">Удаление ссылки на проект из указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="7edcf-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="7edcf-120">Удаление нескольких ссылок на проекты из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="7edcf-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="7edcf-121">Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:</span><span class="sxs-lookup"><span data-stu-id="7edcf-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
