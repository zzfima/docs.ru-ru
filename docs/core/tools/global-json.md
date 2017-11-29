---
title: "Справочник global.json"
description: "Просмотрите схему для файла global.json, которая допускает настройку версии средств .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="globaljson-reference"></a><span data-ttu-id="9cb35-104">Справочник global.json</span><span class="sxs-lookup"><span data-stu-id="9cb35-104">global.json reference</span></span>

<span data-ttu-id="9cb35-105">С помощью свойства `sdk` в файле *global.json* можно выбрать используемую версию средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cb35-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="9cb35-106">Средства интерфейса командной строки .NET Core будут искать этот файл в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="9cb35-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="9cb35-107">sdk</span><span class="sxs-lookup"><span data-stu-id="9cb35-107">sdk</span></span>
<span data-ttu-id="9cb35-108">Тип данных: Object</span><span class="sxs-lookup"><span data-stu-id="9cb35-108">Type: Object</span></span>

<span data-ttu-id="9cb35-109">Конкретные сведения о пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="9cb35-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="9cb35-110">version</span><span class="sxs-lookup"><span data-stu-id="9cb35-110">version</span></span>
<span data-ttu-id="9cb35-111">Тип данных: String</span><span class="sxs-lookup"><span data-stu-id="9cb35-111">Type: String</span></span>

<span data-ttu-id="9cb35-112">Версия пакета SDK для использования.</span><span class="sxs-lookup"><span data-stu-id="9cb35-112">The version of the SDK to use.</span></span>

<span data-ttu-id="9cb35-113">Например:</span><span class="sxs-lookup"><span data-stu-id="9cb35-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
