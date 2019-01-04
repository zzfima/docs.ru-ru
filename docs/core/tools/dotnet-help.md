---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 12/04/2018
ms.openlocfilehash: 44274b698ed83bd3cdb58787f433eeb5c555bc6d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168961"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="3c1b5-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="3c1b5-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="3c1b5-104">name</span><span class="sxs-lookup"><span data-stu-id="3c1b5-104">Name</span></span>

<span data-ttu-id="3c1b5-105">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="3c1b5-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3c1b5-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3c1b5-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="3c1b5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3c1b5-107">Description</span></span>

<span data-ttu-id="3c1b5-108">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="3c1b5-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="3c1b5-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3c1b5-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="3c1b5-110">Имя команды интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3c1b5-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="3c1b5-111">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="3c1b5-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="3c1b5-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c1b5-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="3c1b5-113">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="3c1b5-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="3c1b5-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c1b5-114">Examples</span></span>

* <span data-ttu-id="3c1b5-115">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="3c1b5-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```