---
title: Команда dotnet tool install — .NET Core CLI
description: Команда dotnet tool install устанавливает указанное глобальное средство .NET Core на компьютер.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43418725"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="db51f-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="db51f-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="db51f-104">name</span><span class="sxs-lookup"><span data-stu-id="db51f-104">Name</span></span>

<span data-ttu-id="db51f-105">`dotnet tool install` устанавливает указанное [глобальное средство .NET Core](global-tools.md) на компьютер.</span><span class="sxs-lookup"><span data-stu-id="db51f-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="db51f-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="db51f-106">Synopsis</span></span>

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="db51f-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="db51f-107">Description</span></span>

<span data-ttu-id="db51f-108">Команда `dotnet tool install` предоставляет способ установки глобальных средств .NET Core на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db51f-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="db51f-109">Чтобы использовать эту команду, укажите установку уровня пользователя с помощью параметра `--global` или укажите путь к месту установки с помощью параметра `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="db51f-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="db51f-110">Глобальные средства устанавливаются в следующие каталоги по умолчанию при выборе параметра `-g` (или `--global`):</span><span class="sxs-lookup"><span data-stu-id="db51f-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="db51f-111">Операционная система</span><span class="sxs-lookup"><span data-stu-id="db51f-111">OS</span></span>          | <span data-ttu-id="db51f-112">Путь</span><span class="sxs-lookup"><span data-stu-id="db51f-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="db51f-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="db51f-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="db51f-114">Windows</span><span class="sxs-lookup"><span data-stu-id="db51f-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="db51f-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="db51f-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="db51f-116">Имя или идентификатор пакета NuGet, который содержит устанавливаемое глобальное средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="db51f-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="db51f-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="db51f-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="db51f-118">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="db51f-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="db51f-119">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="db51f-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="db51f-120">Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для установки средства.</span><span class="sxs-lookup"><span data-stu-id="db51f-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="db51f-121">По умолчанию пакет SDK для .NET Core пытается выбрать наиболее подходящую версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db51f-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="db51f-122">Указывает, что установка происходит на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="db51f-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="db51f-123">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="db51f-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="db51f-124">Если вы не укажете этот параметр, укажите параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="db51f-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="db51f-125">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="db51f-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="db51f-126">Указывает место установки глобального средства.</span><span class="sxs-lookup"><span data-stu-id="db51f-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="db51f-127">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="db51f-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="db51f-128">Если путь не существует, команда пытается создать его.</span><span class="sxs-lookup"><span data-stu-id="db51f-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="db51f-129">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="db51f-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="db51f-130">Если вы не укажете этот параметр, укажите параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="db51f-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="db51f-131">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="db51f-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="db51f-132">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="db51f-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="db51f-133">Версия средства для установки.</span><span class="sxs-lookup"><span data-stu-id="db51f-133">The version of the tool to install.</span></span> <span data-ttu-id="db51f-134">По умолчанию устанавливается последняя стабильная версия пакета.</span><span class="sxs-lookup"><span data-stu-id="db51f-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="db51f-135">Используйте этот параметр для установки предварительной версии или предыдущей версии средства.</span><span class="sxs-lookup"><span data-stu-id="db51f-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="db51f-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="db51f-136">Examples</span></span>

<span data-ttu-id="db51f-137">Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в расположении по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="db51f-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="db51f-138">Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в определенную папку Windows:</span><span class="sxs-lookup"><span data-stu-id="db51f-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="db51f-139">Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в определенную папку Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="db51f-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="db51f-140">Устанавливает версию 2.0.0 глобального средства [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="db51f-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="db51f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="db51f-141">See also</span></span>

* [<span data-ttu-id="db51f-142">Глобальные средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="db51f-142">.NET Core Global Tools</span></span>](global-tools.md)