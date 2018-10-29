---
title: Команда dotnet nuget-delete — CLI .NET Core
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: f4aa027a465c4adea1de13853063d03e8e295411
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180885"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="637fa-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="637fa-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="637fa-104">name</span><span class="sxs-lookup"><span data-stu-id="637fa-104">Name</span></span>

<span data-ttu-id="637fa-105">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="637fa-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="637fa-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="637fa-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="637fa-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="637fa-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="637fa-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="637fa-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="637fa-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="637fa-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="637fa-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="637fa-110">Description</span></span>

<span data-ttu-id="637fa-111">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="637fa-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="637fa-112">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="637fa-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="637fa-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="637fa-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="637fa-114">Имя/идентификатор удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="637fa-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="637fa-115">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="637fa-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="637fa-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="637fa-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="637fa-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="637fa-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="637fa-118">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="637fa-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="637fa-119">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="637fa-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="637fa-120">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-120">The API key for the server.</span></span>

<span data-ttu-id="637fa-121">`--no-service-endpoint` Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="637fa-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="637fa-122">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="637fa-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="637fa-123">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-123">Specifies the server URL.</span></span> <span data-ttu-id="637fa-124">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="637fa-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="637fa-125">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="637fa-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="637fa-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="637fa-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="637fa-127">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="637fa-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="637fa-128">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="637fa-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="637fa-129">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="637fa-130">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="637fa-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="637fa-131">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-131">Specifies the server URL.</span></span> <span data-ttu-id="637fa-132">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="637fa-132">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="637fa-133">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="637fa-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="637fa-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="637fa-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="637fa-135">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="637fa-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="637fa-136">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="637fa-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="637fa-137">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="637fa-138">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="637fa-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="637fa-139">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="637fa-139">Specifies the server URL.</span></span> <span data-ttu-id="637fa-140">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="637fa-140">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="637fa-141">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="637fa-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="637fa-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="637fa-142">Examples</span></span>

<span data-ttu-id="637fa-143">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="637fa-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="637fa-144">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="637fa-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
