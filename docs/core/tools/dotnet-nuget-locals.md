---
title: Команда dotnet nuget locals
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: d0f1c7c2e0b233c214cc48d026c19755fc047bfa
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170760"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="789f6-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="789f6-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="789f6-104">name</span><span class="sxs-lookup"><span data-stu-id="789f6-104">Name</span></span>

<span data-ttu-id="789f6-105">`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.</span><span class="sxs-lookup"><span data-stu-id="789f6-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="789f6-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="789f6-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="789f6-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="789f6-107">Description</span></span>

<span data-ttu-id="789f6-108">Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="789f6-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="789f6-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="789f6-109">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="789f6-110">Расположение кэша для вывода или очищения.</span><span class="sxs-lookup"><span data-stu-id="789f6-110">The cache location to list or clear.</span></span> <span data-ttu-id="789f6-111">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="789f6-111">It accepts one of the following values:</span></span>

  * <span data-ttu-id="789f6-112">`all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="789f6-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="789f6-113">`http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="789f6-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="789f6-114">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="789f6-114">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="789f6-115">`global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов.</span><span class="sxs-lookup"><span data-stu-id="789f6-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="789f6-116">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="789f6-116">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="789f6-117">`temp` — указывает, что определенная операция применяется только к временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="789f6-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="789f6-118">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="789f6-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="789f6-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="789f6-119">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="789f6-120">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="789f6-120">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="789f6-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="789f6-121">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="789f6-122">Параметр clear очищает кэш указанного типа.</span><span class="sxs-lookup"><span data-stu-id="789f6-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="789f6-123">Содержимое каталогов кэша удаляется рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="789f6-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="789f6-124">Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша.</span><span class="sxs-lookup"><span data-stu-id="789f6-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="789f6-125">Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="789f6-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="789f6-126">Параметр list используется для отображения расположения кэша указанного типа.</span><span class="sxs-lookup"><span data-stu-id="789f6-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="789f6-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="789f6-127">Examples</span></span>

* <span data-ttu-id="789f6-128">Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="789f6-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals –l all
  ```

* <span data-ttu-id="789f6-129">Отображает путь к локальному каталогу кэша HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="789f6-129">Displays the path for the local http-cache directory:</span></span>

  ```console
  dotnet nuget locals --list http-cache
  ```

* <span data-ttu-id="789f6-130">Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="789f6-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals --clear all
  ```

* <span data-ttu-id="789f6-131">Очищает все файлы в локальном каталоге кэша глобальных пакетов:</span><span class="sxs-lookup"><span data-stu-id="789f6-131">Clears all files in local global-packages cache directory:</span></span>

  ```console
  dotnet nuget locals -c global-packages
  ```

* <span data-ttu-id="789f6-132">Очищает все файлы в локальном каталоге временного кэша:</span><span class="sxs-lookup"><span data-stu-id="789f6-132">Clears all files in local temporary cache directory:</span></span>

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a><span data-ttu-id="789f6-133">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="789f6-133">Troubleshooting</span></span>

<span data-ttu-id="789f6-134">Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="789f6-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>