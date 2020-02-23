---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503775"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="f4fd6-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="f4fd6-103">dotnet build-server</span></span>

<span data-ttu-id="f4fd6-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f4fd6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f4fd6-105">name</span><span class="sxs-lookup"><span data-stu-id="f4fd6-105">Name</span></span>

<span data-ttu-id="f4fd6-106">`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f4fd6-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f4fd6-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="f4fd6-108">Команды</span><span class="sxs-lookup"><span data-stu-id="f4fd6-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="f4fd6-109">Завершает работу серверов сборки, запущенных командой dotnet.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="f4fd6-110">По умолчанию все серверы завершают работу.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="f4fd6-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4fd6-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f4fd6-112">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="f4fd6-113">Завершает работу сервера сборки MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="f4fd6-114">Завершает работу сервера сборки Razor.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="f4fd6-115">Завершает работу сервера сборки компилятора VB/C#.</span><span class="sxs-lookup"><span data-stu-id="f4fd6-115">Shuts down the VB/C# compiler build server.</span></span>
