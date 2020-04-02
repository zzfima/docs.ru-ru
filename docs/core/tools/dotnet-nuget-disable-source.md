---
title: Команда dotnet nuget disable source
description: Команда dotnet nuget disable source отключает существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 5aa16c842bcddeead180fdeec3d9dcdda33f7ed9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148480"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="55ec8-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="55ec8-103">dotnet nuget disable source</span></span>

<span data-ttu-id="55ec8-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="55ec8-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="55ec8-105">name</span><span class="sxs-lookup"><span data-stu-id="55ec8-105">Name</span></span>

<span data-ttu-id="55ec8-106">`dotnet nuget disable source` — отключение источника NuGet.</span><span class="sxs-lookup"><span data-stu-id="55ec8-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55ec8-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="55ec8-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile]
dotnet nuget disable source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="55ec8-108">Описание</span><span class="sxs-lookup"><span data-stu-id="55ec8-108">Description</span></span>

<span data-ttu-id="55ec8-109">Команда `dotnet nuget disable source` отключает существующий источник в файлах конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="55ec8-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="55ec8-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="55ec8-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="55ec8-111">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="55ec8-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="55ec8-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="55ec8-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="55ec8-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="55ec8-113">The NuGet configuration file.</span></span> <span data-ttu-id="55ec8-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="55ec8-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="55ec8-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="55ec8-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="55ec8-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="55ec8-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="55ec8-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="55ec8-117">Examples</span></span>

- <span data-ttu-id="55ec8-118">Отключите источник с именем `mySource`:</span><span class="sxs-lookup"><span data-stu-id="55ec8-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="55ec8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="55ec8-119">See also</span></span>

- [<span data-ttu-id="55ec8-120">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="55ec8-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="55ec8-121">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="55ec8-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
