---
title: Команда dotnet nuget locals
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 3fdd7d946b08b4c18cfaeb65013de259b927a7fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503682"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="bdb11-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="bdb11-103">dotnet nuget locals</span></span>

<span data-ttu-id="bdb11-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="bdb11-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bdb11-105">Имя</span><span class="sxs-lookup"><span data-stu-id="bdb11-105">Name</span></span>

<span data-ttu-id="bdb11-106">`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.</span><span class="sxs-lookup"><span data-stu-id="bdb11-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bdb11-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bdb11-107">Synopsis</span></span>

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="bdb11-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="bdb11-108">Description</span></span>

<span data-ttu-id="bdb11-109">Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="bdb11-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="bdb11-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bdb11-110">Arguments</span></span>

- **`CACHE_LOCATION`**

  <span data-ttu-id="bdb11-111">Расположение кэша для вывода или очищения.</span><span class="sxs-lookup"><span data-stu-id="bdb11-111">The cache location to list or clear.</span></span> <span data-ttu-id="bdb11-112">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="bdb11-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="bdb11-113">`all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="bdb11-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="bdb11-114">`http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="bdb11-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="bdb11-115">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="bdb11-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="bdb11-116">`global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов.</span><span class="sxs-lookup"><span data-stu-id="bdb11-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="bdb11-117">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="bdb11-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="bdb11-118">`temp` — указывает, что определенная операция применяется только к временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="bdb11-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="bdb11-119">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="bdb11-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="bdb11-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdb11-120">Options</span></span>

- **`--force-english-output`**

  <span data-ttu-id="bdb11-121">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="bdb11-121">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bdb11-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="bdb11-122">Prints out a short help for the command.</span></span>

- **`-c|--clear`**

  <span data-ttu-id="bdb11-123">Параметр clear очищает кэш указанного типа.</span><span class="sxs-lookup"><span data-stu-id="bdb11-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="bdb11-124">Содержимое каталогов кэша удаляется рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="bdb11-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="bdb11-125">Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша.</span><span class="sxs-lookup"><span data-stu-id="bdb11-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="bdb11-126">Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="bdb11-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

- **`-l|--list`**

  <span data-ttu-id="bdb11-127">Параметр list используется для отображения расположения кэша указанного типа.</span><span class="sxs-lookup"><span data-stu-id="bdb11-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="bdb11-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="bdb11-128">Examples</span></span>

- <span data-ttu-id="bdb11-129">Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="bdb11-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all –l
  ```

- <span data-ttu-id="bdb11-130">Отображает путь к локальному каталогу кэша HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="bdb11-130">Displays the path for the local http-cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

- <span data-ttu-id="bdb11-131">Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="bdb11-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

- <span data-ttu-id="bdb11-132">Очищает все файлы в локальном каталоге кэша глобальных пакетов:</span><span class="sxs-lookup"><span data-stu-id="bdb11-132">Clears all files in local global-packages cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

- <span data-ttu-id="bdb11-133">Очищает все файлы в локальном каталоге временного кэша:</span><span class="sxs-lookup"><span data-stu-id="bdb11-133">Clears all files in local temporary cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a><span data-ttu-id="bdb11-134">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="bdb11-134">Troubleshooting</span></span>

<span data-ttu-id="bdb11-135">Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="bdb11-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
