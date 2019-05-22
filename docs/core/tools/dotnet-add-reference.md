---
title: Команда dotnet-add reference
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631937"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="39013-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="39013-103">dotnet-add reference</span></span>

<span data-ttu-id="39013-104">**Эта статья относится к ✓** SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="39013-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="39013-105">name</span><span class="sxs-lookup"><span data-stu-id="39013-105">Name</span></span>

<span data-ttu-id="39013-106">`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="39013-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="39013-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="39013-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="39013-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="39013-108">Description</span></span>

<span data-ttu-id="39013-109">Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект.</span><span class="sxs-lookup"><span data-stu-id="39013-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="39013-110">После запуска этой команды в файл проекта добавляются элементы [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="39013-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="39013-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="39013-111">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="39013-112">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="39013-112">Specifies the project file.</span></span> <span data-ttu-id="39013-113">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="39013-113">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="39013-114">Добавляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="39013-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="39013-115">Укажите один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="39013-115">Specify one or more projects.</span></span> <span data-ttu-id="39013-116">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="39013-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="39013-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="39013-117">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="39013-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="39013-118">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="39013-119">Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="39013-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="39013-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="39013-120">Examples</span></span>

* <span data-ttu-id="39013-121">Добавление ссылки на проект:</span><span class="sxs-lookup"><span data-stu-id="39013-121">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="39013-122">Добавление нескольких ссылок на проекты в проект в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="39013-122">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="39013-123">Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="39013-123">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
