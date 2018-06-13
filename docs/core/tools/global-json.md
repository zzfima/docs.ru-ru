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
ms.locfileid: "33209974"
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
