---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 04/24/2019
ms.openlocfilehash: 491ac37e7f75f930423b3c7e43e3c090ec1ed07d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754288"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="7998f-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="7998f-103">dotnet build-server</span></span>

<span data-ttu-id="7998f-104">**Эта статья относится к ✓** SDK для .NET Core 2.1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="7998f-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="7998f-105">name</span><span class="sxs-lookup"><span data-stu-id="7998f-105">Name</span></span>

<span data-ttu-id="7998f-106">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="7998f-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7998f-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7998f-107">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="7998f-108">Команды</span><span class="sxs-lookup"><span data-stu-id="7998f-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="7998f-109">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="7998f-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="7998f-110">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="7998f-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="7998f-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="7998f-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="7998f-112">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7998f-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="7998f-113">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="7998f-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="7998f-114">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="7998f-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="7998f-115">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="7998f-115">Shuts down the VB/C# compiler build server.</span></span>