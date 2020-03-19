---
title: Команда dotnet tool install
description: Команда dotnet tool install устанавливает указанное средство .NET Core на компьютер.
ms.date: 02/14/2020
ms.openlocfilehash: 1e142773d1f981a8dc3b552d5a23d2864cdd82c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146467"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="12ab9-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="12ab9-103">dotnet tool install</span></span>

<span data-ttu-id="12ab9-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="12ab9-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="12ab9-105">name</span><span class="sxs-lookup"><span data-stu-id="12ab9-105">Name</span></span>

<span data-ttu-id="12ab9-106">`dotnet tool install` устанавливает указанное [средство .NET Core](global-tools.md) на компьютер.</span><span class="sxs-lookup"><span data-stu-id="12ab9-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="12ab9-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12ab9-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME> <--tool-path>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="12ab9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="12ab9-108">Description</span></span>

<span data-ttu-id="12ab9-109">Команда `dotnet tool install` предоставляет способ установки средств .NET Core на компьютере.</span><span class="sxs-lookup"><span data-stu-id="12ab9-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="12ab9-110">Чтобы использовать команду, укажите один из следующих параметров установки:</span><span class="sxs-lookup"><span data-stu-id="12ab9-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="12ab9-111">Чтобы установить глобальный инструмент в расположение по умолчанию, используйте параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="12ab9-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="12ab9-112">Чтобы установить глобальный инструмент в расположение, указанное пользователем, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="12ab9-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="12ab9-113">Чтобы установить локальный инструмент, пропустите параметры `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="12ab9-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="12ab9-114">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="12ab9-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="12ab9-115">Глобальные средства устанавливаются в следующие каталоги по умолчанию при выборе параметра `-g` или `--global`:</span><span class="sxs-lookup"><span data-stu-id="12ab9-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="12ab9-116">Операционная система</span><span class="sxs-lookup"><span data-stu-id="12ab9-116">OS</span></span>          | <span data-ttu-id="12ab9-117">Path</span><span class="sxs-lookup"><span data-stu-id="12ab9-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="12ab9-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="12ab9-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="12ab9-119">Windows</span><span class="sxs-lookup"><span data-stu-id="12ab9-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="12ab9-120">Локальные средства добавляются в файл *tool-manifest.json* в каталоге *. config* в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="12ab9-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="12ab9-121">Если файл манифеста еще не существует, создайте его, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="12ab9-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="12ab9-122">Дополнительные сведения см. в разделе [Установка глобального средства](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="12ab9-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="12ab9-123">Аргументы</span><span class="sxs-lookup"><span data-stu-id="12ab9-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="12ab9-124">Имя или идентификатор пакета NuGet, который содержит устанавливаемое средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="12ab9-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="12ab9-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="12ab9-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="12ab9-126">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="12ab9-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="12ab9-127">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="12ab9-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="12ab9-128">Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для установки средства.</span><span class="sxs-lookup"><span data-stu-id="12ab9-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="12ab9-129">По умолчанию пакет SDK для .NET Core пытается выбрать наиболее подходящую версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12ab9-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="12ab9-130">Указывает, что установка происходит на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="12ab9-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="12ab9-131">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="12ab9-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="12ab9-132">Пропуск параметров `--global` и `--tool-path` задает установку локального средства.</span><span class="sxs-lookup"><span data-stu-id="12ab9-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="12ab9-133">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="12ab9-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="12ab9-134">Указывает место установки глобального средства.</span><span class="sxs-lookup"><span data-stu-id="12ab9-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="12ab9-135">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="12ab9-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="12ab9-136">Если путь не существует, команда пытается создать его.</span><span class="sxs-lookup"><span data-stu-id="12ab9-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="12ab9-137">Пропуск параметров `--global` и `--tool-path` задает установку локального средства.</span><span class="sxs-lookup"><span data-stu-id="12ab9-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="12ab9-138">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="12ab9-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="12ab9-139">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="12ab9-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="12ab9-140">Версия средства для установки.</span><span class="sxs-lookup"><span data-stu-id="12ab9-140">The version of the tool to install.</span></span> <span data-ttu-id="12ab9-141">По умолчанию устанавливается последняя стабильная версия пакета.</span><span class="sxs-lookup"><span data-stu-id="12ab9-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="12ab9-142">Используйте этот параметр для установки предварительной версии или предыдущей версии средства.</span><span class="sxs-lookup"><span data-stu-id="12ab9-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="12ab9-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="12ab9-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="12ab9-144">Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12ab9-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="12ab9-145">Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве глобального инструмента в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="12ab9-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="12ab9-146">Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве глобального инструмента в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="12ab9-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="12ab9-147">Устанавливает версию 2.0.0 в качестве глобального средства [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="12ab9-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="12ab9-148">Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве локального средства для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="12ab9-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="12ab9-149">См. также</span><span class="sxs-lookup"><span data-stu-id="12ab9-149">See also</span></span>

- [<span data-ttu-id="12ab9-150">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="12ab9-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="12ab9-151">Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="12ab9-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="12ab9-152">Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="12ab9-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
