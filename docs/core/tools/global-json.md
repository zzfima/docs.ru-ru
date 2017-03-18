---
title: "Справочник по файлу global.json | Microsoft Docs"
description: "Справочник global.json"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 253b8642ae6fc5308d47552e9addfdbed6813ff1
ms.lasthandoff: 03/07/2017

---

# <a name="globaljson-reference"></a>Справочник global.json

Файл global.json позволяет выбрать используемую версию средств .NET Core с помощью свойства `sdk`. 

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
