---
title: Команда dotnet tool uninstall — .NET Core CLI
description: Команда dotnet tool uninstall удаляет указанное глобальное средство .NET Core с компьютера.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 93a43e19df4c7f220ac1e2d2db397cba4d791e83
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43738183"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="b97d0-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="b97d0-103">dotnet tool uninstall</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="b97d0-104">name</span><span class="sxs-lookup"><span data-stu-id="b97d0-104">Name</span></span>

<span data-ttu-id="b97d0-105">`dotnet tool uninstall` — удаляет указанное [глобальное средство .NET Core](global-tools.md) с компьютера.</span><span class="sxs-lookup"><span data-stu-id="b97d0-105">`dotnet tool uninstall` - Uninstalls the specified [.NET Core Global Tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b97d0-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b97d0-106">Synopsis</span></span>

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="b97d0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b97d0-107">Description</span></span>

<span data-ttu-id="b97d0-108">Команда `dotnet tool uninstall` позволяет удалить глобальные средства .NET Core с компьютера.</span><span class="sxs-lookup"><span data-stu-id="b97d0-108">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core Global Tools from your machine.</span></span> <span data-ttu-id="b97d0-109">Чтобы использовать эту команду, укажите, что хотите удалить средство на уровне пользователя, с помощью параметра `--global`, или укажите путь к расположению средства с помощью параметра `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="b97d0-109">To use the command, you either have to specify that you want to remove a user-wide tool using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="b97d0-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b97d0-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="b97d0-111">Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET Core, которое вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="b97d0-111">Name/ID of the NuGet package that contains the .NET Core Global Tool to uninstall.</span></span> <span data-ttu-id="b97d0-112">Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="b97d0-112">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="b97d0-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="b97d0-113">Options</span></span>

`-g|--global`

<span data-ttu-id="b97d0-114">Указывает, что средство будет удалено из установки на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="b97d0-114">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="b97d0-115">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="b97d0-115">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="b97d0-116">Если вы не укажете этот параметр, укажите параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="b97d0-116">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="b97d0-117">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="b97d0-117">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="b97d0-118">Указывает место, откуда будет удалено глобальное средство.</span><span class="sxs-lookup"><span data-stu-id="b97d0-118">Specifies the location where to uninstall the Global Tool.</span></span> <span data-ttu-id="b97d0-119">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="b97d0-119">PATH can be absolute or relative.</span></span> <span data-ttu-id="b97d0-120">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="b97d0-120">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="b97d0-121">Если вы не укажете этот параметр, укажите параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="b97d0-121">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="b97d0-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="b97d0-122">Examples</span></span>

<span data-ttu-id="b97d0-123">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="b97d0-123">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool uninstall -g dotnetsay`

<span data-ttu-id="b97d0-124">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенной папки Windows:</span><span class="sxs-lookup"><span data-stu-id="b97d0-124">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Windows folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="b97d0-125">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенной папки Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="b97d0-125">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Linux/macOS folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="b97d0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b97d0-126">See also</span></span>

* [<span data-ttu-id="b97d0-127">Глобальные средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="b97d0-127">.NET Core Global Tools</span></span>](global-tools.md)