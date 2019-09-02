---
title: Команда dotnet nuget locals
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0cf025f91a7582fafc401799cd1d8b933b087535
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202463"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="3bce1-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="3bce1-103">dotnet nuget locals</span></span>

<span data-ttu-id="3bce1-104">**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3bce1-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="3bce1-105">name</span><span class="sxs-lookup"><span data-stu-id="3bce1-105">Name</span></span>

<span data-ttu-id="3bce1-106">`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.</span><span class="sxs-lookup"><span data-stu-id="3bce1-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3bce1-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3bce1-107">Synopsis</span></span>

```console
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3bce1-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="3bce1-108">Description</span></span>

<span data-ttu-id="3bce1-109">Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="3bce1-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="3bce1-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3bce1-110">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="3bce1-111">Расположение кэша для вывода или очищения.</span><span class="sxs-lookup"><span data-stu-id="3bce1-111">The cache location to list or clear.</span></span> <span data-ttu-id="3bce1-112">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="3bce1-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="3bce1-113">`all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="3bce1-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="3bce1-114">`http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="3bce1-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="3bce1-115">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="3bce1-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="3bce1-116">`global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов.</span><span class="sxs-lookup"><span data-stu-id="3bce1-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="3bce1-117">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="3bce1-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="3bce1-118">`temp` — указывает, что определенная операция применяется только к временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="3bce1-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="3bce1-119">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="3bce1-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="3bce1-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bce1-120">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="3bce1-121">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="3bce1-121">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3bce1-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="3bce1-122">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="3bce1-123">Параметр clear очищает кэш указанного типа.</span><span class="sxs-lookup"><span data-stu-id="3bce1-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="3bce1-124">Содержимое каталогов кэша удаляется рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="3bce1-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="3bce1-125">Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша.</span><span class="sxs-lookup"><span data-stu-id="3bce1-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="3bce1-126">Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="3bce1-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="3bce1-127">Параметр list используется для отображения расположения кэша указанного типа.</span><span class="sxs-lookup"><span data-stu-id="3bce1-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="3bce1-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="3bce1-128">Examples</span></span>

* <span data-ttu-id="3bce1-129">Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="3bce1-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals –l all
  ```

* <span data-ttu-id="3bce1-130">Отображает путь к локальному каталогу кэша HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="3bce1-130">Displays the path for the local http-cache directory:</span></span>

  ```console
  dotnet nuget locals --list http-cache
  ```

* <span data-ttu-id="3bce1-131">Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="3bce1-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals --clear all
  ```

* <span data-ttu-id="3bce1-132">Очищает все файлы в локальном каталоге кэша глобальных пакетов:</span><span class="sxs-lookup"><span data-stu-id="3bce1-132">Clears all files in local global-packages cache directory:</span></span>

  ```console
  dotnet nuget locals -c global-packages
  ```

* <span data-ttu-id="3bce1-133">Очищает все файлы в локальном каталоге временного кэша:</span><span class="sxs-lookup"><span data-stu-id="3bce1-133">Clears all files in local temporary cache directory:</span></span>

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a><span data-ttu-id="3bce1-134">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="3bce1-134">Troubleshooting</span></span>

<span data-ttu-id="3bce1-135">Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="3bce1-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
