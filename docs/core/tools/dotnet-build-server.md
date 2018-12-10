---
title: Команда dotnet build-server — .NET Core CLI
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125682"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="ccad2-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ccad2-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="ccad2-104">name</span><span class="sxs-lookup"><span data-stu-id="ccad2-104">Name</span></span>

<span data-ttu-id="ccad2-105">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="ccad2-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ccad2-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ccad2-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="ccad2-107">Команды</span><span class="sxs-lookup"><span data-stu-id="ccad2-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="ccad2-108">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="ccad2-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="ccad2-109">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="ccad2-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="ccad2-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccad2-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="ccad2-111">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ccad2-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="ccad2-112">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ccad2-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="ccad2-113">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="ccad2-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="ccad2-114">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="ccad2-114">Shuts down the VB/C# compiler build server.</span></span>