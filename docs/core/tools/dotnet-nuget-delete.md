---
title: "Команда dotnet nuget-delete — CLI .NET Core"
description: "Команда dotnet-nuget-delete удаляет пакет с сервера или из списка."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 65fe52f07ed823b4f7518c5b1f2da1f7a61b0371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="de328-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="de328-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="de328-104">Имя</span><span class="sxs-lookup"><span data-stu-id="de328-104">Name</span></span>

<span data-ttu-id="de328-105">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="de328-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="de328-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="de328-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="de328-107">Описание</span><span class="sxs-lookup"><span data-stu-id="de328-107">Description</span></span>

<span data-ttu-id="de328-108">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="de328-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="de328-109">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="de328-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="de328-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="de328-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="de328-111">Удаляемый пакет.</span><span class="sxs-lookup"><span data-stu-id="de328-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="de328-112">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="de328-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="de328-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="de328-113">Options</span></span>

`-h|--help`

<span data-ttu-id="de328-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="de328-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="de328-115">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="de328-115">Specifies the server URL.</span></span> <span data-ttu-id="de328-116">Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="de328-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="de328-117">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="de328-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="de328-118">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="de328-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="de328-119">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="de328-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="de328-120">Принудительно отображает выходные данные командной строки на английском языке.</span><span class="sxs-lookup"><span data-stu-id="de328-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="de328-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="de328-121">Examples</span></span>

<span data-ttu-id="de328-122">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="de328-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="de328-123">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="de328-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`