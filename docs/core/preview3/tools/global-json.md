---
title: "Справочник по файлу global.json | Microsoft Docs"
description: "Справочник global.json"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 97a9ee85025c15e21d4a7cbdce31d35d3894e7d6

---

# <a name="globaljson-reference-tooling-preview-4"></a>Справочник по файлу global.json (предварительная версия 4 инструментов)

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [Справочник по файлу global.json](../../tools/global-json.md).

Файл global.json по-прежнему присутствует в командной строке .NET Core (предварительная версия 4). При этом он используется не для определения метаданных решения, как в предыдущих выпусках, а для разрешения выбора используемой версии CLI с помощью свойства `sdk`. 

В справочнике это учитывается. 

## <a name="sdk"></a>sdk
Тип данных: Object

Конкретные сведения о пакете SDK.

### <a name="version"></a>version
Тип данных: String

Версия пакета SDK для использования.

Например:

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```


<!--HONumber=Jan17_HO3-->


