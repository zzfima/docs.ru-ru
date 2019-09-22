---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 08/08/2019
ms.openlocfilehash: 533f2c47fa7ec14d31368538092fec2490234820
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117717"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="75a91-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="75a91-103">dotnet help reference</span></span>

<span data-ttu-id="75a91-104">**Эта статья относится к ✓** SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="75a91-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="75a91-105">name</span><span class="sxs-lookup"><span data-stu-id="75a91-105">Name</span></span>

<span data-ttu-id="75a91-106">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="75a91-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="75a91-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="75a91-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="75a91-108">Описание</span><span class="sxs-lookup"><span data-stu-id="75a91-108">Description</span></span>

<span data-ttu-id="75a91-109">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="75a91-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="75a91-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="75a91-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="75a91-111">Имя команды интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75a91-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="75a91-112">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="75a91-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="75a91-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="75a91-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="75a91-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="75a91-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="75a91-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="75a91-115">Examples</span></span>

* <span data-ttu-id="75a91-116">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="75a91-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
