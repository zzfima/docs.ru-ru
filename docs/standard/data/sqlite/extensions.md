---
title: Расширения
ms.date: 12/13/2019
description: Узнайте, как загружать расширения SQLite.
ms.openlocfilehash: a85b1227be4274dd20156d2475d6d2d68e250f99
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901300"
---
# <a name="extensions"></a>Расширения

SQLite поддерживает загрузку расширений во время выполнения. Расширения включают такие возможности, как дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.

.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, таких как ссылочные пакеты NuGet. Увы, SQLite не может использовать эту логику; Он напрямую вызывает API платформы для загрузки библиотек. Поэтому может потребоваться изменить путь, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH переменные среды перед загрузкой расширений SQLite. В GitHub есть [Пример](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , демонстрирующий Поиск двоичных файлов для текущей среды выполнения внутри пакета NuGet, на который указывает ссылка.

Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft. Data. SQLite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>См. также:

* [Расширения, загружаемые во время выполнения](https://www.sqlite.org/loadext.html)
