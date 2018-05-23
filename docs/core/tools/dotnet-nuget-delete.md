---
title: Команда dotnet nuget-delete — CLI .NET Core
description: Команда dotnet-nuget-delete удаляет пакет с сервера или из списка.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 639ade54bfed5eb2de89bdb3b7f451393b4be187
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="053a5-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="053a5-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="053a5-104">name</span><span class="sxs-lookup"><span data-stu-id="053a5-104">Name</span></span>

<span data-ttu-id="053a5-105">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="053a5-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="053a5-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="053a5-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="053a5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="053a5-107">Description</span></span>

<span data-ttu-id="053a5-108">Команда `dotnet nuget delete` удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="053a5-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="053a5-109">Для [nuget.org](https://www.nuget.org/) команда удаляет пакет из списка.</span><span class="sxs-lookup"><span data-stu-id="053a5-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="053a5-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="053a5-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="053a5-111">Удаляемый пакет.</span><span class="sxs-lookup"><span data-stu-id="053a5-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="053a5-112">Версия удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="053a5-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="053a5-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="053a5-113">Options</span></span>

`-h|--help`

<span data-ttu-id="053a5-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="053a5-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="053a5-115">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="053a5-115">Specifies the server URL.</span></span> <span data-ttu-id="053a5-116">Поддерживаемые URL-адреса для nuget.org: `http://www.nuget.org`, `http://www.nuget.org/api/v3` и `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="053a5-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="053a5-117">Для частных каналов замените имя узла (например, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="053a5-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="053a5-118">Не запрашивает у пользователя данные или подтверждения.</span><span class="sxs-lookup"><span data-stu-id="053a5-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="053a5-119">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="053a5-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="053a5-120">Принудительно отображает выходные данные командной строки на английском языке.</span><span class="sxs-lookup"><span data-stu-id="053a5-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="053a5-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="053a5-121">Examples</span></span>

<span data-ttu-id="053a5-122">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0:</span><span class="sxs-lookup"><span data-stu-id="053a5-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="053a5-123">Удаляет пакет `Microsoft.AspNetCore.Mvc` версии 1.0, не запрашивая учетные данные или другие входные данные, предоставляемые пользователем:</span><span class="sxs-lookup"><span data-stu-id="053a5-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`