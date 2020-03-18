---
title: Команда dotnet nuget delete
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0950f03c0986bde17ae3e2e7170d402ea8222853
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733118"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="7d2cb-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="7d2cb-103">dotnet nuget delete</span></span>

<span data-ttu-id="7d2cb-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="7d2cb-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="7d2cb-105">Имя</span><span class="sxs-lookup"><span data-stu-id="7d2cb-105">Name</span></span>

<span data-ttu-id="7d2cb-106">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7d2cb-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7d2cb-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7d2cb-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d2cb-108">Description</span></span>

<span data-ttu-id="7d2cb-109">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="7d2cb-110">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="7d2cb-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7d2cb-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="7d2cb-112">Имя/идентификатор удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="7d2cb-113">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="7d2cb-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d2cb-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="7d2cb-115">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="7d2cb-116">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="7d2cb-117">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="7d2cb-118">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="7d2cb-119">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="7d2cb-120">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="7d2cb-121">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="7d2cb-122">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="7d2cb-123">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-123">Specifies the server URL.</span></span> <span data-ttu-id="7d2cb-124">Поддерживаемые URL-адреса для nuget.org: `https://www.nuget.org`, `https://www.nuget.org/api/v3` и `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="7d2cb-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="7d2cb-125">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="7d2cb-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="7d2cb-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="7d2cb-126">Examples</span></span>

* <span data-ttu-id="7d2cb-127">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="7d2cb-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="7d2cb-128">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="7d2cb-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
