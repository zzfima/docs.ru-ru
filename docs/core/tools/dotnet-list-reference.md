---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 12/03/2018
ms.openlocfilehash: d22ea27f8e8f6b94d763e44a6d8644f814663797
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169837"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="52f81-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="52f81-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="52f81-104">name</span><span class="sxs-lookup"><span data-stu-id="52f81-104">Name</span></span>

<span data-ttu-id="52f81-105">`dotnet list reference` — перечисляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="52f81-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52f81-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52f81-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="52f81-107">Описание</span><span class="sxs-lookup"><span data-stu-id="52f81-107">Description</span></span>

<span data-ttu-id="52f81-108">Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="52f81-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="52f81-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="52f81-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="52f81-110">Указывает файл проекта, используемый для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="52f81-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="52f81-111">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="52f81-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="52f81-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="52f81-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="52f81-113">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="52f81-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="52f81-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="52f81-114">Examples</span></span>

* <span data-ttu-id="52f81-115">Перечисление ссылок на проекты для указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="52f81-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="52f81-116">Перечисление ссылок на проекты для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="52f81-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```