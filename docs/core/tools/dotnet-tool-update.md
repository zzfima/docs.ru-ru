---
title: Команда dotnet tool update
description: Команда dotnet tool update обновляет указанное средство .NET Core на вашем компьютере.
ms.date: 02/14/2020
ms.openlocfilehash: 497b052a8b9cfa9dca8d80316075fe7565d6b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847824"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="bdafb-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="bdafb-103">dotnet tool update</span></span>

<span data-ttu-id="bdafb-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="bdafb-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bdafb-105">name</span><span class="sxs-lookup"><span data-stu-id="bdafb-105">Name</span></span>

<span data-ttu-id="bdafb-106">`dotnet tool update` обновляет указанное [средство .NET Core](global-tools.md) на компьютер.</span><span class="sxs-lookup"><span data-stu-id="bdafb-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bdafb-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bdafb-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME> <--tool-path>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="bdafb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bdafb-108">Description</span></span>

<span data-ttu-id="bdafb-109">Команда `dotnet tool update` предоставляет способ обновления средства .NET Core на компьютере до последней стабильной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="bdafb-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="bdafb-110">Команда удаляет и повторно устанавливает средство, эффективно обновляя его.</span><span class="sxs-lookup"><span data-stu-id="bdafb-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="bdafb-111">Чтобы использовать команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="bdafb-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="bdafb-112">Чтобы обновить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`</span><span class="sxs-lookup"><span data-stu-id="bdafb-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="bdafb-113">Чтобы обновить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="bdafb-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="bdafb-114">Чтобы обновить локальный инструмент, пропустите параметры `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="bdafb-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="bdafb-115">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="bdafb-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="bdafb-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bdafb-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="bdafb-117">Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET Core, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="bdafb-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="bdafb-118">Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="bdafb-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="bdafb-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdafb-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="bdafb-120">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="bdafb-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="bdafb-121">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="bdafb-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="bdafb-122">Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для обновления средства.</span><span class="sxs-lookup"><span data-stu-id="bdafb-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="bdafb-123">Указывает, что обновление предназначено для средства уровня пользователя.</span><span class="sxs-lookup"><span data-stu-id="bdafb-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="bdafb-124">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="bdafb-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="bdafb-125">Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="bdafb-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bdafb-126">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="bdafb-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="bdafb-127">Указывает место установки глобального средства.</span><span class="sxs-lookup"><span data-stu-id="bdafb-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="bdafb-128">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="bdafb-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="bdafb-129">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="bdafb-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="bdafb-130">Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="bdafb-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="bdafb-131">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="bdafb-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bdafb-132">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bdafb-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="bdafb-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="bdafb-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="bdafb-134">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="bdafb-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="bdafb-135">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="bdafb-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="bdafb-136">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="bdafb-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="bdafb-137">Обновляет локальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), установленное для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="bdafb-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdafb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="bdafb-138">See also</span></span>

- [<span data-ttu-id="bdafb-139">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="bdafb-139">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="bdafb-140">Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="bdafb-140">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="bdafb-141">Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="bdafb-141">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
