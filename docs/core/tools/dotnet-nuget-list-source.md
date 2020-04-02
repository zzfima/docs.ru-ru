---
title: Команда dotnet nuget list source
description: Команда dotnet nuget list source выводит список всех существующих источников в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148498"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="eeb78-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="eeb78-103">dotnet nuget list source</span></span>

<span data-ttu-id="eeb78-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="eeb78-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="eeb78-105">name</span><span class="sxs-lookup"><span data-stu-id="eeb78-105">Name</span></span>

<span data-ttu-id="eeb78-106">`dotnet nuget list source` — перечисляет все настроенные источники NuGet.</span><span class="sxs-lookup"><span data-stu-id="eeb78-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="eeb78-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eeb78-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="eeb78-108">Описание</span><span class="sxs-lookup"><span data-stu-id="eeb78-108">Description</span></span>

<span data-ttu-id="eeb78-109">Команда `dotnet nuget list source` перечисляет все существующие источники из файлов конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="eeb78-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="eeb78-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="eeb78-110">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="eeb78-111">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="eeb78-111">The NuGet configuration file.</span></span> <span data-ttu-id="eeb78-112">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="eeb78-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="eeb78-113">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="eeb78-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="eeb78-114">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="eeb78-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format`**

  <span data-ttu-id="eeb78-115">Формат выходных данных команды list: `Detailed` (по умолчанию) и `Short`.</span><span class="sxs-lookup"><span data-stu-id="eeb78-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="eeb78-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="eeb78-116">Examples</span></span>

- <span data-ttu-id="eeb78-117">Список настроенных источников из текущего каталога:</span><span class="sxs-lookup"><span data-stu-id="eeb78-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="eeb78-118">См. также</span><span class="sxs-lookup"><span data-stu-id="eeb78-118">See also</span></span>

- [<span data-ttu-id="eeb78-119">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="eeb78-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="eeb78-120">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="eeb78-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
