---
title: Команда dotnet help — CLI .NET Core
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 12/04/2018
ms.openlocfilehash: 60d1cc706ca5c78fa3be877bd679888181213e88
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152179"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="40a5a-103">Справочник по команде dotnet help</span><span class="sxs-lookup"><span data-stu-id="40a5a-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="40a5a-104">name</span><span class="sxs-lookup"><span data-stu-id="40a5a-104">Name</span></span>

<span data-ttu-id="40a5a-105">`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="40a5a-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="40a5a-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="40a5a-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="40a5a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="40a5a-107">Description</span></span>

<span data-ttu-id="40a5a-108">Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="40a5a-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="40a5a-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40a5a-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="40a5a-110">Имя команды интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40a5a-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="40a5a-111">Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="40a5a-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="40a5a-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="40a5a-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="40a5a-113">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="40a5a-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="40a5a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="40a5a-114">Examples</span></span>

* <span data-ttu-id="40a5a-115">Открывает страницу документации по команде[dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="40a5a-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```