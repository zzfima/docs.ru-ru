---
title: Расширения
ms.date: 12/13/2019
description: Узнайте, как загружать расширения SQLite.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777375"
---
# <a name="extensions"></a>Расширения

SQLite поддерживает загрузку расширений во время выполнения. Расширения включают такие возможности, как дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.

.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, таких как ссылочные пакеты NuGet. Увы, SQLite не может использовать эту логику; Он напрямую вызывает API платформы для загрузки библиотек. По этой причине приложению может потребоваться изменить путь, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH переменные среды перед загрузкой расширений SQLite. В GitHub есть [Пример](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , демонстрирующий Поиск двоичных файлов для текущей среды выполнения внутри пакета NuGet, на который указывает ссылка.

Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft. Data. SQLite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>См. также:

* [Расширения, загружаемые во время выполнения](https://www.sqlite.org/loadext.html)
