---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117763"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="b5edd-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="b5edd-103">dotnet build-server</span></span>

<span data-ttu-id="b5edd-104">**Эта статья относится к ✓** SDK для .NET Core 2.1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="b5edd-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="b5edd-105">name</span><span class="sxs-lookup"><span data-stu-id="b5edd-105">Name</span></span>

<span data-ttu-id="b5edd-106">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="b5edd-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b5edd-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b5edd-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="b5edd-108">Команды</span><span class="sxs-lookup"><span data-stu-id="b5edd-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="b5edd-109">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="b5edd-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="b5edd-110">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="b5edd-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="b5edd-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5edd-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="b5edd-112">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="b5edd-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="b5edd-113">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b5edd-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="b5edd-114">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="b5edd-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="b5edd-115">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="b5edd-115">Shuts down the VB/C# compiler build server.</span></span>
