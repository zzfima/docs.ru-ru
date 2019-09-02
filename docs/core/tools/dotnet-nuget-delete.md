---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 70316a0baa2cf9923738a53af561b5c77014c3ff
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202573"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="afb7d-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="afb7d-103">dotnet nuget delete</span></span>

<span data-ttu-id="afb7d-104">**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="afb7d-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="afb7d-105">name</span><span class="sxs-lookup"><span data-stu-id="afb7d-105">Name</span></span>

<span data-ttu-id="afb7d-106">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="afb7d-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="afb7d-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="afb7d-107">Synopsis</span></span>

```console
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="afb7d-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="afb7d-108">Description</span></span>

<span data-ttu-id="afb7d-109">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="afb7d-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="afb7d-110">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="afb7d-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="afb7d-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="afb7d-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="afb7d-112">Имя/идентификатор удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="afb7d-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="afb7d-113">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="afb7d-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="afb7d-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="afb7d-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="afb7d-115">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="afb7d-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="afb7d-116">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="afb7d-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="afb7d-117">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="afb7d-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="afb7d-118">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="afb7d-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="afb7d-119">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="afb7d-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="afb7d-120">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="afb7d-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="afb7d-121">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="afb7d-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="afb7d-122">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="afb7d-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="afb7d-123">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="afb7d-123">Specifies the server URL.</span></span> <span data-ttu-id="afb7d-124">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="afb7d-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="afb7d-125">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="afb7d-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="afb7d-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="afb7d-126">Examples</span></span>

* <span data-ttu-id="afb7d-127">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="afb7d-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="afb7d-128">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="afb7d-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
