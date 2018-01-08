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
ms.workload: dotnetcore
ms.openlocfilehash: c7e64995ed00a6b2df1b7e1dfa43c6bea5cf4535
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="globaljson-reference"></a><span data-ttu-id="18266-104">Справочник global.json</span><span class="sxs-lookup"><span data-stu-id="18266-104">global.json reference</span></span>

<span data-ttu-id="18266-105">С помощью свойства `sdk` в файле *global.json* можно выбрать используемую версию средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18266-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="18266-106">Средства интерфейса командной строки .NET Core будут искать этот файл в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="18266-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="18266-107">sdk</span><span class="sxs-lookup"><span data-stu-id="18266-107">sdk</span></span>
<span data-ttu-id="18266-108">Тип данных: Object</span><span class="sxs-lookup"><span data-stu-id="18266-108">Type: Object</span></span>

<span data-ttu-id="18266-109">Конкретные сведения о пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="18266-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="18266-110">version</span><span class="sxs-lookup"><span data-stu-id="18266-110">version</span></span>
<span data-ttu-id="18266-111">Тип данных: String</span><span class="sxs-lookup"><span data-stu-id="18266-111">Type: String</span></span>

<span data-ttu-id="18266-112">Версия пакета SDK для использования.</span><span class="sxs-lookup"><span data-stu-id="18266-112">The version of the SDK to use.</span></span>

<span data-ttu-id="18266-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="18266-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
