---
title: Команда dotnet tool update
description: Команда dotnet tool update обновляет указанное глобальное средство .NET Core на вашем компьютере.
ms.date: 05/29/2018
ms.openlocfilehash: bc7edada013c118564d44cbe4542dacb76925692
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516647"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="a5613-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="a5613-103">dotnet tool update</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="a5613-104">name</span><span class="sxs-lookup"><span data-stu-id="a5613-104">Name</span></span>

<span data-ttu-id="a5613-105">`dotnet tool update` обновляет указанное [глобальное средство .NET Core](global-tools.md) на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a5613-105">`dotnet tool update` - Updates the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a5613-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a5613-106">Synopsis</span></span>

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="a5613-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a5613-107">Description</span></span>

<span data-ttu-id="a5613-108">Команда `dotnet tool update` предоставляет способ обновления глобального средства .NET Core на компьютере до последней стабильной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="a5613-108">The `dotnet tool update` command provides a way for you to update .NET Core Global Tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="a5613-109">Команда удаляет и повторно устанавливает средство, эффективно обновляя его.</span><span class="sxs-lookup"><span data-stu-id="a5613-109">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="a5613-110">Чтобы использовать эту команду, укажите, что хотите обновить средство из установки уровня пользователя с помощью параметра `--global`, или укажите путь к месту установки средства с помощью параметра `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="a5613-110">To use the command, you either have to specify that you want to update a tool from a user-wide installation using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="a5613-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a5613-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="a5613-112">Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET Core, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="a5613-112">Name/ID of the NuGet package that contains the .NET Core Global Tool to update.</span></span> <span data-ttu-id="a5613-113">Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="a5613-113">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="a5613-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5613-114">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="a5613-115">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="a5613-115">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="a5613-116">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="a5613-116">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="a5613-117">Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для обновления средства.</span><span class="sxs-lookup"><span data-stu-id="a5613-117">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

`-g|--global`

<span data-ttu-id="a5613-118">Указывает, что обновление предназначено для средства уровня пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5613-118">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="a5613-119">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="a5613-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="a5613-120">Если вы не укажете этот параметр, укажите параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="a5613-120">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="a5613-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a5613-121">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="a5613-122">Указывает место установки глобального средства.</span><span class="sxs-lookup"><span data-stu-id="a5613-122">Specifies the location where the Global Tool is installed.</span></span> <span data-ttu-id="a5613-123">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="a5613-123">PATH can be absolute or relative.</span></span> <span data-ttu-id="a5613-124">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="a5613-124">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="a5613-125">Если вы не укажете этот параметр, укажите параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="a5613-125">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a5613-126">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="a5613-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a5613-127">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a5613-127">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="a5613-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="a5613-128">Examples</span></span>

<span data-ttu-id="a5613-129">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="a5613-129">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool update -g dotnetsay`

<span data-ttu-id="a5613-130">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенной папке Windows:</span><span class="sxs-lookup"><span data-stu-id="a5613-130">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Windows folder:</span></span>

`dotnet tool update dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="a5613-131">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенной папке Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="a5613-131">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Linux/macOS folder:</span></span>

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="a5613-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a5613-132">See also</span></span>

- [<span data-ttu-id="a5613-133">Глобальные средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="a5613-133">.NET Core Global Tools</span></span>](global-tools.md)
