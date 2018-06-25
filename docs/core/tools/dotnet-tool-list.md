---
title: Команда dotnet tool list — .NET Core CLI
description: Команда dotnet tool list показывает указанное глобальное средство .NET Core на вашем компьютере.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 5f4793cd37c3a8df06eb6930ad9f381ac70d4e67
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696729"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="4261f-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4261f-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="4261f-104">name</span><span class="sxs-lookup"><span data-stu-id="4261f-104">Name</span></span>

<span data-ttu-id="4261f-105">`dotnet tool list` — выводит все [глобальные средства .NET Core](global-tools.md), установленные в каталоге по умолчанию на вашем компьютере или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="4261f-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4261f-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4261f-106">Synopsis</span></span>

```
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="4261f-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4261f-107">Description</span></span>

<span data-ttu-id="4261f-108">Команда `dotnet tool list` позволяет просмотреть все глобальные средства .NET Core, установленные на уровне пользователя на компьютере (для текущего профиля пользователя) или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="4261f-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="4261f-109">Эта команда выводит имя пакета, установленную версию и команду глобального средства.</span><span class="sxs-lookup"><span data-stu-id="4261f-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="4261f-110">Чтобы использовать эту команду, укажите вывод средств на уровне пользователя с помощью параметра `--global` или укажите другой путь с помощью параметра `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4261f-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="4261f-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="4261f-111">Options</span></span>

`-g|--global`

<span data-ttu-id="4261f-112">Выводит глобальные средства на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4261f-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="4261f-113">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4261f-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="4261f-114">Если вы не укажете этот параметр, укажите параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4261f-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="4261f-115">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="4261f-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="4261f-116">Задает пользовательское расположение для глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="4261f-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="4261f-117">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="4261f-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="4261f-118">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="4261f-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="4261f-119">Если вы не укажете этот параметр, укажите параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="4261f-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="4261f-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="4261f-120">Examples</span></span>

<span data-ttu-id="4261f-121">Выводит все глобальные средства, установленные на уровне пользователя на вашем компьютере (для текущего профиля пользователя):</span><span class="sxs-lookup"><span data-stu-id="4261f-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="4261f-122">Выводит глобальные средства в определенной папке Windows:</span><span class="sxs-lookup"><span data-stu-id="4261f-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="4261f-123">Выводит глобальные средства в определенной папке Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="4261f-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="4261f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4261f-124">See also</span></span>

[<span data-ttu-id="4261f-125">Глобальные средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="4261f-125">.NET Core Global Tools</span></span>](global-tools.md)