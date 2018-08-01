---
title: Команда dotnet build-server — .NET Core CLI
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404337"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="e726b-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="e726b-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="e726b-104">name</span><span class="sxs-lookup"><span data-stu-id="e726b-104">Name</span></span>

<span data-ttu-id="e726b-105">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="e726b-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e726b-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e726b-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="e726b-107">Команды</span><span class="sxs-lookup"><span data-stu-id="e726b-107">Commands</span></span>

`shutdown`

<span data-ttu-id="e726b-108">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="e726b-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="e726b-109">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="e726b-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="e726b-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="e726b-110">Options</span></span>

`-h|--help`

<span data-ttu-id="e726b-111">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e726b-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="e726b-112">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="e726b-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="e726b-113">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="e726b-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="e726b-114">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="e726b-114">Shuts down the VB/C# compiler build server.</span></span>
