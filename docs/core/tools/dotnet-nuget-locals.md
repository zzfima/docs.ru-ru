---
title: Команда dotnet nuget locals — CLI .NET Core
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d0c900a06b00fd5e6b7ad66527c6582483222c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="8dfb8-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="8dfb8-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8dfb8-104">name</span><span class="sxs-lookup"><span data-stu-id="8dfb8-104">Name</span></span>

<span data-ttu-id="8dfb8-105">`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8dfb8-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8dfb8-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="8dfb8-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8dfb8-107">Description</span></span>

<span data-ttu-id="8dfb8-108">Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="8dfb8-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8dfb8-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="8dfb8-110">Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="8dfb8-110">One of the following values:</span></span>

* <span data-ttu-id="8dfb8-111">`all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="8dfb8-112">`http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="8dfb8-113">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="8dfb8-114">`global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="8dfb8-115">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="8dfb8-116">`temp` — указывает, что определенная операция применяется только к временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="8dfb8-117">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="8dfb8-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dfb8-118">Options</span></span>

`-h|--help`

<span data-ttu-id="8dfb8-119">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="8dfb8-120">Параметр clear очищает кэш указанного типа.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="8dfb8-121">Содержимое каталогов кэша удаляется рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="8dfb8-122">Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="8dfb8-123">Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="8dfb8-124">Параметр list используется для отображения расположения кэша указанного типа.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="8dfb8-125">Принудительно отображает выходные данные командной строки на английском языке.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="8dfb8-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="8dfb8-126">Examples</span></span>

<span data-ttu-id="8dfb8-127">Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="8dfb8-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="8dfb8-128">Отображает путь к локальному каталогу кэша HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="8dfb8-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="8dfb8-129">Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="8dfb8-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="8dfb8-130">Очищает все файлы в локальном каталоге кэша глобальных пакетов:</span><span class="sxs-lookup"><span data-stu-id="8dfb8-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="8dfb8-131">Очищает все файлы в локальном каталоге временного кэша:</span><span class="sxs-lookup"><span data-stu-id="8dfb8-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="8dfb8-132">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="8dfb8-132">Troubleshooting</span></span>

<span data-ttu-id="8dfb8-133">Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="8dfb8-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>