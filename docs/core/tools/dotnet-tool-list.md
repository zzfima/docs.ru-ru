---
title: Команда dotnet tool list
description: Команда dotnet tool list выводит список средств .NET Core, установленных на компьютере.
ms.date: 02/14/2020
ms.openlocfilehash: f231dcfe64a925f75f948d508e7a2d83befd9a00
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156989"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="be83e-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="be83e-103">dotnet tool list</span></span>

<span data-ttu-id="be83e-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="be83e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="be83e-105">name</span><span class="sxs-lookup"><span data-stu-id="be83e-105">Name</span></span>

<span data-ttu-id="be83e-106">`dotnet tool list` — выводит все [средства .NET Core](global-tools.md) указанного типа, установленных на компьютере в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="be83e-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="be83e-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="be83e-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="be83e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="be83e-108">Description</span></span>

<span data-ttu-id="be83e-109">Команда `dotnet tool list` позволяет получить список всех установленных на компьютере глобальных, установочных и локальных средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="be83e-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="be83e-110">Эта команда выводит имя пакета, установленную версию и команду средства.</span><span class="sxs-lookup"><span data-stu-id="be83e-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="be83e-111">Чтобы использовать эту команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="be83e-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="be83e-112">Глобальное средство, установленное в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be83e-112">A global tool installed in the default location.</span></span> <span data-ttu-id="be83e-113">Использование параметра `--global`</span><span class="sxs-lookup"><span data-stu-id="be83e-113">Use the `--global` option</span></span>
* <span data-ttu-id="be83e-114">Глобальное средство, установленное в пользовательском расположении.</span><span class="sxs-lookup"><span data-stu-id="be83e-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="be83e-115">Использовать параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="be83e-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="be83e-116">Локальное средство.</span><span class="sxs-lookup"><span data-stu-id="be83e-116">A local tool.</span></span> <span data-ttu-id="be83e-117">Пропуск параметров `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="be83e-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="be83e-118">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="be83e-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="be83e-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="be83e-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="be83e-120">Выводит глобальные средства на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="be83e-120">Lists user-wide global tools.</span></span> <span data-ttu-id="be83e-121">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="be83e-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="be83e-122">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="be83e-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="be83e-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="be83e-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="be83e-124">Задает пользовательское расположение для глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="be83e-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="be83e-125">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="be83e-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="be83e-126">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="be83e-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="be83e-127">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="be83e-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="be83e-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="be83e-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="be83e-129">Выводит все глобальные средства, установленные на уровне пользователя на вашем компьютере (для текущего профиля пользователя).</span><span class="sxs-lookup"><span data-stu-id="be83e-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="be83e-130">Выводит глобальные средства в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="be83e-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="be83e-131">Выводит глобальные средства в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="be83e-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="be83e-132">Выводит все локальные средства, доступные в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="be83e-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="be83e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="be83e-133">See also</span></span>

- [<span data-ttu-id="be83e-134">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="be83e-134">.NET Core tools</span></span>](global-tools.md)
