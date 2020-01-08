---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite в памяти.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450468"
---
# <a name="in-memory-databases"></a>Базы данных в памяти

Базы данных SQLite в памяти — это базы данных, которые полностью хранятся в памяти, а не на диске. Используйте имя файла специального источника данных `:memory:` для создания базы данных в памяти. Когда соединение закрывается, база данных удаляется. При использовании `:memory:`каждое соединение создает собственную базу данных.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Совместное использование баз данных в памяти

Базы данных в памяти могут совместно использоваться несколькими подключениями с помощью `Mode=Memory` и `Cache=Shared` в строке подключения. Ключевое слово `Data Source` используется для присвоения имени базе данных в памяти. Строки подключения, использующие одно и то же имя, будут обращаться к одной и той же базе данных в памяти. База данных сохраняется, пока по крайней мере одно подключение к ней остается открытым. [Пример](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) , демонстрирующий это, можно найти на сайте GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
