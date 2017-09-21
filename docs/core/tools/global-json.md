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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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

Например:

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

