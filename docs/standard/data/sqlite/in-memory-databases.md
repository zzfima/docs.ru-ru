---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных в памяти S'Lite.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391212"
---
# <a name="in-memory-databases"></a>Базы данных в памяти

Базы данных памяти S'Lite — это базы данных, хранящиеся исключительно в памяти, а не на диске. Используйте специальное имя `:memory:` источника данных для создания базы данных в памяти. При закрытии соединения база данных удаляется. При `:memory:`использовании каждое соединение создает свою собственную базу данных.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Общие базы данных в памяти

Базы данных в памяти могут быть `Mode=Memory` `Cache=Shared` разделены между несколькими соединениями с помощью и в строке соединения. Ключевое `Data Source` слово используется для привить базе данных в памяти имя. Строки подключения с использованием одного и того же имени будут получать доступ к той же базе данных в памяти. База данных сохраняется до тех пор, пока по крайней мере одно подключение к ней остается открытым. [Пример,](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) демонстрирующий это, доступен на GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
