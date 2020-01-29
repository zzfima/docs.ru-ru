---
title: Команда dotnet add reference
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
ms.date: 06/26/2019
ms.openlocfilehash: dc8bc01a2bff4f2cf3a8af9efb233448d7de337f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733272"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="87c12-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="87c12-103">dotnet add reference</span></span>

<span data-ttu-id="87c12-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="87c12-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="87c12-105">name</span><span class="sxs-lookup"><span data-stu-id="87c12-105">Name</span></span>

<span data-ttu-id="87c12-106">`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="87c12-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="87c12-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="87c12-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="87c12-108">Описание</span><span class="sxs-lookup"><span data-stu-id="87c12-108">Description</span></span>

<span data-ttu-id="87c12-109">Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект.</span><span class="sxs-lookup"><span data-stu-id="87c12-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="87c12-110">После запуска этой команды в файл проекта добавляются элементы `<ProjectReference>`.</span><span class="sxs-lookup"><span data-stu-id="87c12-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="87c12-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="87c12-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="87c12-112">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="87c12-112">Specifies the project file.</span></span> <span data-ttu-id="87c12-113">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="87c12-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="87c12-114">Добавляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="87c12-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="87c12-115">Укажите один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="87c12-115">Specify one or more projects.</span></span> <span data-ttu-id="87c12-116">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="87c12-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="87c12-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="87c12-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="87c12-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="87c12-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="87c12-119">Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="87c12-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="87c12-120">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="87c12-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="87c12-121">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="87c12-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="87c12-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="87c12-122">Examples</span></span>

- <span data-ttu-id="87c12-123">Добавление ссылки на проект:</span><span class="sxs-lookup"><span data-stu-id="87c12-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="87c12-124">Добавление нескольких ссылок на проекты в проект в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="87c12-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="87c12-125">Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="87c12-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
