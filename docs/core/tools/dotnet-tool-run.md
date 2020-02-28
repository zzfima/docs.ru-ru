---
title: Команда dotnet tool run
description: Команда dotnet tool run вызывает локальное средство.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543830"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="53c9c-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="53c9c-103">dotnet tool run</span></span>

<span data-ttu-id="53c9c-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="53c9c-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="53c9c-105">name</span><span class="sxs-lookup"><span data-stu-id="53c9c-105">Name</span></span>

<span data-ttu-id="53c9c-106">`dotnet tool run` — вызов локального средства.</span><span class="sxs-lookup"><span data-stu-id="53c9c-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="53c9c-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="53c9c-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="53c9c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="53c9c-108">Description</span></span>

<span data-ttu-id="53c9c-109">Команда `dotnet tool run` позволяет выполнить поиск по файлам манифеста средства, которые входят в область текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="53c9c-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="53c9c-110">При нахождении ссылки на указанное средство оно запускается.</span><span class="sxs-lookup"><span data-stu-id="53c9c-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="53c9c-111">См. дополнительные сведения о [запуске локального средства](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="53c9c-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="53c9c-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="53c9c-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="53c9c-113">Имя выполняемой команды в средстве.</span><span class="sxs-lookup"><span data-stu-id="53c9c-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="53c9c-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="53c9c-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="53c9c-115">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="53c9c-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="53c9c-116">Пример</span><span class="sxs-lookup"><span data-stu-id="53c9c-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="53c9c-117">Запуск локального средства `dotnetsay`.</span><span class="sxs-lookup"><span data-stu-id="53c9c-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="53c9c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="53c9c-118">See also</span></span>

- [<span data-ttu-id="53c9c-119">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="53c9c-119">.NET Core tools</span></span>](global-tools.md)
