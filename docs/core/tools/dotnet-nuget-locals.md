---
title: Команда dotnet nuget locals — CLI .NET Core
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 799acb92d6ab7439e15c23c9f0b7b572c966adda
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696875"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="24a7e-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="24a7e-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="24a7e-104">name</span><span class="sxs-lookup"><span data-stu-id="24a7e-104">Name</span></span>

<span data-ttu-id="24a7e-105">`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.</span><span class="sxs-lookup"><span data-stu-id="24a7e-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="24a7e-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="24a7e-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="24a7e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="24a7e-107">Description</span></span>

<span data-ttu-id="24a7e-108">Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="24a7e-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="24a7e-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="24a7e-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="24a7e-110">Расположение кэша для вывода или очищения.</span><span class="sxs-lookup"><span data-stu-id="24a7e-110">The cache location to list or clear.</span></span> <span data-ttu-id="24a7e-111">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="24a7e-111">It accepts one of the following values:</span></span>

* <span data-ttu-id="24a7e-112">`all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="24a7e-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="24a7e-113">`http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="24a7e-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="24a7e-114">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="24a7e-114">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="24a7e-115">`global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов.</span><span class="sxs-lookup"><span data-stu-id="24a7e-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="24a7e-116">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="24a7e-116">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="24a7e-117">`temp` — указывает, что определенная операция применяется только к временному кэшу.</span><span class="sxs-lookup"><span data-stu-id="24a7e-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="24a7e-118">Другие расположения кэша не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="24a7e-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="24a7e-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="24a7e-119">Options</span></span>

`--force-english-output`

<span data-ttu-id="24a7e-120">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="24a7e-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="24a7e-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="24a7e-121">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="24a7e-122">Параметр clear очищает кэш указанного типа.</span><span class="sxs-lookup"><span data-stu-id="24a7e-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="24a7e-123">Содержимое каталогов кэша удаляется рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="24a7e-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="24a7e-124">Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша.</span><span class="sxs-lookup"><span data-stu-id="24a7e-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="24a7e-125">Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="24a7e-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

`-l|--list`

<span data-ttu-id="24a7e-126">Параметр list используется для отображения расположения кэша указанного типа.</span><span class="sxs-lookup"><span data-stu-id="24a7e-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="24a7e-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="24a7e-127">Examples</span></span>

<span data-ttu-id="24a7e-128">Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="24a7e-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="24a7e-129">Отображает путь к локальному каталогу кэша HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="24a7e-129">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="24a7e-130">Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):</span><span class="sxs-lookup"><span data-stu-id="24a7e-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="24a7e-131">Очищает все файлы в локальном каталоге кэша глобальных пакетов:</span><span class="sxs-lookup"><span data-stu-id="24a7e-131">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="24a7e-132">Очищает все файлы в локальном каталоге временного кэша:</span><span class="sxs-lookup"><span data-stu-id="24a7e-132">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="24a7e-133">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="24a7e-133">Troubleshooting</span></span>

<span data-ttu-id="24a7e-134">Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="24a7e-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>