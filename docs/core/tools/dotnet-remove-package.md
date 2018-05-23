---
title: Команда dotnet remove package — CLI .NET Core
description: Команду dotnet remove package удобно использовать для удаления ссылки на пакет NuGet в проекте.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 6a18be1a853119be245623e8fa0a0e44ed819e8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="fa208-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="fa208-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fa208-104">name</span><span class="sxs-lookup"><span data-stu-id="fa208-104">Name</span></span>

<span data-ttu-id="fa208-105">`dotnet remove package` — удаляет ссылку на пакет из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="fa208-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fa208-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fa208-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="fa208-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="fa208-107">Description</span></span>

<span data-ttu-id="fa208-108">Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.</span><span class="sxs-lookup"><span data-stu-id="fa208-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="fa208-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fa208-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="fa208-110">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="fa208-110">Specifies the project file.</span></span> <span data-ttu-id="fa208-111">Если он не указан, команда будет искать текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="fa208-111">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="fa208-112">Удаляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="fa208-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="fa208-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa208-113">Options</span></span>

`-h|--help`

<span data-ttu-id="fa208-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="fa208-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="fa208-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa208-115">Examples</span></span>

<span data-ttu-id="fa208-116">Удаляет пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="fa208-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`
