---
title: Справочник global.json
description: Просмотрите схему для файла global.json, которая допускает настройку версии средств .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a>Справочник global.json

С помощью свойства `sdk` в файле *global.json* можно выбрать используемую версию средств .NET Core.

Средства интерфейса командной строки .NET Core будут искать этот файл в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.

## <a name="sdk"></a>sdk
Тип данных: Object

Конкретные сведения о пакете SDK.

### <a name="version"></a>version
Тип данных: String

Версия пакета SDK для использования.

Пример:

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
