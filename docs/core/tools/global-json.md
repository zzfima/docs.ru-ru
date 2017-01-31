---
title: "Справочник по файлу global.json | Microsoft Docs"
description: "Справочник global.json"
keywords: .NET, .NET Core
author: aL3891
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: e8c8123f2c46e506990375172d1be642653d4996

---

# <a name="globaljson-reference"></a>Справочник global.json

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Информацию об инструментах .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017 см. в статье [Справочник по файлу global.json (предварительная версия 4 инструментов)](../preview3/tools/global-json.md).

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



<!--HONumber=Jan17_HO3-->


