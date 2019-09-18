---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990465"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="04805-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="04805-103">dotnet help reference</span></span>

<span data-ttu-id="04805-104">**Эта статья относится к ✓** SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="04805-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="04805-105">name</span><span class="sxs-lookup"><span data-stu-id="04805-105">Name</span></span>

<span data-ttu-id="04805-106">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="04805-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="04805-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04805-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="04805-108">Описание</span><span class="sxs-lookup"><span data-stu-id="04805-108">Description</span></span>

<span data-ttu-id="04805-109">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="04805-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="04805-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="04805-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="04805-111">Имя команды интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04805-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="04805-112">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="04805-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="04805-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="04805-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="04805-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="04805-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="04805-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="04805-115">Examples</span></span>

* <span data-ttu-id="04805-116">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="04805-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
