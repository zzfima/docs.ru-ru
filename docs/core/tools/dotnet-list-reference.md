---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 06/26/2019
ms.openlocfilehash: 496cbcd8fa4d921e30b363904ad0273bd5ebacd5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733219"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="c929c-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c929c-103">dotnet list reference</span></span>

<span data-ttu-id="c929c-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c929c-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="c929c-105">name</span><span class="sxs-lookup"><span data-stu-id="c929c-105">Name</span></span>

<span data-ttu-id="c929c-106">`dotnet list reference` — перечисляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="c929c-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c929c-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c929c-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="c929c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c929c-108">Description</span></span>

<span data-ttu-id="c929c-109">Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="c929c-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="c929c-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c929c-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="c929c-111">Указывает файл проекта или решения, используемый для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="c929c-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="c929c-112">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="c929c-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="c929c-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="c929c-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c929c-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c929c-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c929c-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="c929c-115">Examples</span></span>

* <span data-ttu-id="c929c-116">Перечисление ссылок на проекты для указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="c929c-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="c929c-117">Перечисление ссылок на проекты для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c929c-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
