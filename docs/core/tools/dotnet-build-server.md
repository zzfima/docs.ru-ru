---
title: Команда dotnet build-server — .NET Core CLI
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 929b8d74aa5f3f0ad73b108be8a5bf22f86e30d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696258"
---
# <a name="dotnet-build"></a><span data-ttu-id="aa790-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="aa790-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="aa790-104">name</span><span class="sxs-lookup"><span data-stu-id="aa790-104">Name</span></span>

<span data-ttu-id="aa790-105">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="aa790-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="aa790-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aa790-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="aa790-107">Команды</span><span class="sxs-lookup"><span data-stu-id="aa790-107">Commands</span></span>

`shutdown`

<span data-ttu-id="aa790-108">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="aa790-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="aa790-109">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="aa790-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="aa790-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa790-110">Options</span></span>

`-h|--help`

<span data-ttu-id="aa790-111">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="aa790-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="aa790-112">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="aa790-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="aa790-113">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="aa790-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="aa790-114">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="aa790-114">Shuts down the VB/C# compiler build server.</span></span>
