---
title: "Команда dotnet list reference — CLI .NET Core"
description: "Команду dotnet list reference удобно использовать для перечисления ссылок между проектами."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: a4ceadb6d070d7997e75b472624bbe2c1650396d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="40b38-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="40b38-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="40b38-104">name</span><span class="sxs-lookup"><span data-stu-id="40b38-104">Name</span></span>

<span data-ttu-id="40b38-105">`dotnet list reference` — перечисляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="40b38-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="40b38-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="40b38-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="40b38-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="40b38-107">Description</span></span>

<span data-ttu-id="40b38-108">Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.</span><span class="sxs-lookup"><span data-stu-id="40b38-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="40b38-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40b38-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="40b38-110">Указывает файл проекта, используемый для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="40b38-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="40b38-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="40b38-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="40b38-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="40b38-112">Options</span></span>

`-h|--help`

<span data-ttu-id="40b38-113">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="40b38-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="40b38-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="40b38-114">Examples</span></span>

<span data-ttu-id="40b38-115">Перечисление ссылок на проекты для указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="40b38-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="40b38-116">Перечисление ссылок на проекты для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="40b38-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`
