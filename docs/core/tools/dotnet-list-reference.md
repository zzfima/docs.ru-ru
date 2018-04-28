---
title: Команда dotnet list reference — CLI .NET Core
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 946d3d523443fbe673b95dba95dbca327fde1699
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="b6fac-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b6fac-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b6fac-104">name</span><span class="sxs-lookup"><span data-stu-id="b6fac-104">Name</span></span>

<span data-ttu-id="b6fac-105">`dotnet list reference` — перечисляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="b6fac-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b6fac-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b6fac-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="b6fac-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b6fac-107">Description</span></span>

<span data-ttu-id="b6fac-108">Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.</span><span class="sxs-lookup"><span data-stu-id="b6fac-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="b6fac-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b6fac-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b6fac-110">Указывает файл проекта, используемый для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="b6fac-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="b6fac-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="b6fac-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="b6fac-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6fac-112">Options</span></span>

`-h|--help`

<span data-ttu-id="b6fac-113">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="b6fac-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b6fac-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="b6fac-114">Examples</span></span>

<span data-ttu-id="b6fac-115">Перечисление ссылок на проекты для указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="b6fac-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="b6fac-116">Перечисление ссылок на проекты для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="b6fac-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`
