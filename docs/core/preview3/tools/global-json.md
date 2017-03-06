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
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: b814bfc79c2fcd0fd15b9494c18c6d0443a70fb1

---

# <a name="globaljson-reference-net-core-tools-rc4"></a>Справочник по global.json (версия-кандидат 4 средств .NET Core)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [Справочник по файлу global.json](../../tools/global-json.md).

Файл global.json по-прежнему присутствует в версии-кандидате 4 командной строки .NET Core. При этом он используется не для определения метаданных решения, как в предыдущих выпусках, а для разрешения выбора используемой версии CLI с помощью свойства `sdk`. 

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


<!--HONumber=Feb17_HO2-->


