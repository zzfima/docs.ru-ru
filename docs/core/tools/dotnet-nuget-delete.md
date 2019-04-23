---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612632"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="05025-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="05025-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="05025-104">name</span><span class="sxs-lookup"><span data-stu-id="05025-104">Name</span></span>

<span data-ttu-id="05025-105">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="05025-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="05025-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="05025-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="05025-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="05025-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="05025-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="05025-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="05025-109">Описание</span><span class="sxs-lookup"><span data-stu-id="05025-109">Description</span></span>

<span data-ttu-id="05025-110">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="05025-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="05025-111">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="05025-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="05025-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="05025-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="05025-113">Имя/идентификатор удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="05025-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="05025-114">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="05025-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="05025-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="05025-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="05025-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="05025-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="05025-117">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="05025-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="05025-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="05025-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="05025-119">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="05025-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="05025-120">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="05025-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="05025-121">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="05025-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="05025-122">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="05025-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="05025-123">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="05025-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="05025-124">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="05025-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="05025-125">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="05025-125">Specifies the server URL.</span></span> <span data-ttu-id="05025-126">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="05025-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="05025-127">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="05025-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="05025-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="05025-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="05025-129">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="05025-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="05025-130">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="05025-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="05025-131">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="05025-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="05025-132">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="05025-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="05025-133">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="05025-133">Specifies the server URL.</span></span> <span data-ttu-id="05025-134">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="05025-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="05025-135">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="05025-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="05025-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="05025-136">Examples</span></span>

* <span data-ttu-id="05025-137">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="05025-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="05025-138">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="05025-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```