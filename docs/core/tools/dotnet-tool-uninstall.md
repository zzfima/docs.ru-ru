---
title: Команда dotnet tool uninstall
description: Команда dotnet tool uninstall удаляет указанное средство .NET Core с компьютера.
ms.date: 02/14/2020
ms.openlocfilehash: 82dad0206d9c3e2ef0f41c353f4a608f10e4f127
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543447"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="09ba5-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="09ba5-103">dotnet tool uninstall</span></span>

<span data-ttu-id="09ba5-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="09ba5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="09ba5-105">name</span><span class="sxs-lookup"><span data-stu-id="09ba5-105">Name</span></span>

<span data-ttu-id="09ba5-106">`dotnet tool uninstall` — удаляет указанное [средство .NET Core](global-tools.md) с компьютера.</span><span class="sxs-lookup"><span data-stu-id="09ba5-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="09ba5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="09ba5-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="09ba5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="09ba5-108">Description</span></span>

<span data-ttu-id="09ba5-109">Команда `dotnet tool uninstall` позволяет удалить средства .NET Core с компьютера.</span><span class="sxs-lookup"><span data-stu-id="09ba5-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="09ba5-110">Чтобы использовать команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="09ba5-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="09ba5-111">Чтобы удалить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="09ba5-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="09ba5-112">Чтобы удалить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="09ba5-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="09ba5-113">Чтобы удалить локальный инструмент, пропустите параметры `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="09ba5-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="09ba5-114">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="09ba5-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="09ba5-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="09ba5-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="09ba5-116">Имя или идентификатор пакета NuGet, который содержит удаляемое средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09ba5-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="09ba5-117">Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="09ba5-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="09ba5-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="09ba5-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="09ba5-119">Указывает, что средство будет удалено из установки на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="09ba5-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="09ba5-120">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="09ba5-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="09ba5-121">Пропуск `--global` и `--tool-path` означает, что удаляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="09ba5-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="09ba5-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="09ba5-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="09ba5-123">Указывает место, откуда будет удалено средство.</span><span class="sxs-lookup"><span data-stu-id="09ba5-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="09ba5-124">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="09ba5-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="09ba5-125">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="09ba5-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="09ba5-126">Пропуск `--global` и `--tool-path` означает, что удаляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="09ba5-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span> 

## <a name="examples"></a><span data-ttu-id="09ba5-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="09ba5-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="09ba5-128">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="09ba5-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="09ba5-129">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенного каталога Windows.</span><span class="sxs-lookup"><span data-stu-id="09ba5-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="09ba5-130">Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенного каталога Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="09ba5-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="09ba5-131">Удаляет локальный инструмент [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="09ba5-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="09ba5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="09ba5-132">See also</span></span>

- [<span data-ttu-id="09ba5-133">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="09ba5-133">.NET Core tools</span></span>](global-tools.md)
