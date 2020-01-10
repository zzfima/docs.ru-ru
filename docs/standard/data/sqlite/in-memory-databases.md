---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite в памяти.
ms.openlocfilehash: 16a9b6536fbfede203c24b757e96e28e7c49dc05
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777412"
---
# <a name="in-memory-databases"></a>Базы данных в памяти

Базы данных SQLite в памяти — это базы данных, которые полностью хранятся в памяти, а не на диске. Используйте имя файла специального источника данных `:memory:` для создания базы данных в памяти. Когда соединение закрывается, база данных удаляется. При использовании `:memory:`каждое соединение создает собственную базу данных.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Совместное использование баз данных в памяти

Базы данных в памяти могут совместно использоваться несколькими подключениями с помощью `Mode=Memory` и `Cache=Shared` в строке подключения. Ключевое слово `Data Source` используется для присвоения имени базе данных в памяти. Строки подключения, использующие одно и то же имя, будут обращаться к одной и той же базе данных в памяти. База данных сохраняется, пока по крайней мере одно подключение к ней остается открытым. [Пример](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) , демонстрирующий это, можно найти на сайте GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
