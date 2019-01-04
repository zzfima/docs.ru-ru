---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 827d295d7a52b6c9c82adbcf3d25281bd1cc98fd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168316"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="ba66c-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ba66c-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ba66c-104">name</span><span class="sxs-lookup"><span data-stu-id="ba66c-104">Name</span></span>

<span data-ttu-id="ba66c-105">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="ba66c-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ba66c-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ba66c-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ba66c-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ba66c-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ba66c-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ba66c-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="ba66c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ba66c-109">Description</span></span>

<span data-ttu-id="ba66c-110">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="ba66c-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="ba66c-111">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="ba66c-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="ba66c-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ba66c-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="ba66c-113">Имя/идентификатор удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="ba66c-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="ba66c-114">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="ba66c-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="ba66c-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba66c-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ba66c-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ba66c-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="ba66c-117">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ba66c-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="ba66c-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ba66c-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="ba66c-119">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="ba66c-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="ba66c-120">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ba66c-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="ba66c-121">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="ba66c-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="ba66c-122">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="ba66c-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="ba66c-123">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ba66c-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="ba66c-124">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="ba66c-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="ba66c-125">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="ba66c-125">Specifies the server URL.</span></span> <span data-ttu-id="ba66c-126">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="ba66c-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="ba66c-127">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="ba66c-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ba66c-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ba66c-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="ba66c-129">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ba66c-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="ba66c-130">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ba66c-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="ba66c-131">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="ba66c-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="ba66c-132">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="ba66c-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="ba66c-133">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="ba66c-133">Specifies the server URL.</span></span> <span data-ttu-id="ba66c-134">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="ba66c-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="ba66c-135">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="ba66c-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="ba66c-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="ba66c-136">Examples</span></span>

* <span data-ttu-id="ba66c-137">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="ba66c-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="ba66c-138">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="ba66c-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```