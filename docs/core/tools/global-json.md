---
title: Справочник global.json
description: Просмотрите схему для файла global.json, которая допускает настройку версии средств .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="globaljson-reference"></a><span data-ttu-id="ff3c5-103">Справочник global.json</span><span class="sxs-lookup"><span data-stu-id="ff3c5-103">global.json reference</span></span>

<span data-ttu-id="ff3c5-104">С помощью свойства `sdk` в файле *global.json* можно выбрать используемую версию средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ff3c5-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="ff3c5-105">Средства интерфейса командной строки .NET Core будут искать этот файл в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="ff3c5-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="ff3c5-106">sdk</span><span class="sxs-lookup"><span data-stu-id="ff3c5-106">sdk</span></span>
<span data-ttu-id="ff3c5-107">Тип данных: Object</span><span class="sxs-lookup"><span data-stu-id="ff3c5-107">Type: Object</span></span>

<span data-ttu-id="ff3c5-108">Конкретные сведения о пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="ff3c5-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="ff3c5-109">version</span><span class="sxs-lookup"><span data-stu-id="ff3c5-109">version</span></span>
<span data-ttu-id="ff3c5-110">Тип данных: String</span><span class="sxs-lookup"><span data-stu-id="ff3c5-110">Type: String</span></span>

<span data-ttu-id="ff3c5-111">Версия пакета SDK для использования.</span><span class="sxs-lookup"><span data-stu-id="ff3c5-111">The version of the SDK to use.</span></span>

<span data-ttu-id="ff3c5-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="ff3c5-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
