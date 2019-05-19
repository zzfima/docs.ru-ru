---
title: Команда dotnet remove package
description: Команду dotnet remove package удобно использовать для удаления ссылки на пакет NuGet в проекте.
ms.date: 05/29/2018
ms.openlocfilehash: cbdeacff78ef20c9a73010e10a771a724b23792e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632436"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="06d1f-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="06d1f-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="06d1f-104">name</span><span class="sxs-lookup"><span data-stu-id="06d1f-104">Name</span></span>

<span data-ttu-id="06d1f-105">`dotnet remove package` — удаляет ссылку на пакет из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="06d1f-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="06d1f-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06d1f-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="06d1f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="06d1f-107">Description</span></span>

<span data-ttu-id="06d1f-108">Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.</span><span class="sxs-lookup"><span data-stu-id="06d1f-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="06d1f-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="06d1f-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="06d1f-110">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="06d1f-110">Specifies the project file.</span></span> <span data-ttu-id="06d1f-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="06d1f-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="06d1f-112">Удаляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="06d1f-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="06d1f-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="06d1f-113">Options</span></span>

`-h|--help`

<span data-ttu-id="06d1f-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="06d1f-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="06d1f-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="06d1f-115">Examples</span></span>

<span data-ttu-id="06d1f-116">Удаляет пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="06d1f-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`
