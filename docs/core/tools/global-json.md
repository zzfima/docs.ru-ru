---
title: "Справочник global.json | .NET Core"
description: "Справочник global.json"
keywords: .NET, .NET Core
author: aL3891
ms.author: mairaw
manager: wpickett
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 6f3a46284bd5820520739577919fa202f5b784d7
ms.openlocfilehash: 2353a22ea41c3fbf5700ba40da5cdb89b5bf2872

---

# <a name="globaljson-reference"></a>Справочник global.json

Файл global.json используется в проектах .NET Core для определения метаданных решения. Этот файл используется при вызове команды [dotnet-restore](dotnet-restore.md) для восстановления зависимостей проекта .NET Core.
В этом справочном разделе приводится список свойств, которые можно определить в файле global.json.

## <a name="projects"></a>проекты
Тип данных: String[]

Указывает, в каких папках система сборки должна искать проекты при разрешении зависимостей. Система сборки будет вести поиск только в дочерних папках верхнего уровня.

Например:

```json
{
    "projects": [ "src", "test" ]
}
```

## <a name="packages"></a>пакеты
Тип данных: String

Расположение для хранения пакетов.

Например:
```json
{
    "packages": "packages-dir"
}
```

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



<!--HONumber=Nov16_HO1-->


