---
title: Команда dotnet msbuild — CLI .NET Core
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 9e6f8b3063b4cd2a3a36cae8839d6f83e0466e03
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="93280-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="93280-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="93280-104">name</span><span class="sxs-lookup"><span data-stu-id="93280-104">Name</span></span>

<span data-ttu-id="93280-105">`dotnet msbuild` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="93280-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="93280-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="93280-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="93280-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="93280-107">Description</span></span>

<span data-ttu-id="93280-108">Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.</span><span class="sxs-lookup"><span data-stu-id="93280-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="93280-109">Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="93280-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="93280-110">Все параметры одинаковы.</span><span class="sxs-lookup"><span data-stu-id="93280-110">The options are all the same.</span></span> <span data-ttu-id="93280-111">Для получения сведений о различных параметрах см. раздел [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="93280-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="93280-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="93280-112">Examples</span></span>

<span data-ttu-id="93280-113">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="93280-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="93280-114">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="93280-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="93280-115">Запустите цель публикации и публикацию для RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="93280-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="93280-116">Весь проект со всеми целевыми объектами, включенными в пакет SDK:</span><span class="sxs-lookup"><span data-stu-id="93280-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`
