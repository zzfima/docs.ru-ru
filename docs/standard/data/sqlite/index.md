---
title: Обзор
ms.date: 12/13/2019
description: Общие сведения о Microsoft.Data.Sqlite
ms.openlocfilehash: a5dc1366cc0ddfcd5501e26bf2a994456bcd5d98
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75353469"
---
# <a name="microsoftdatasqlite-overview"></a>Общие сведения о Microsoft.Data.Sqlite

Microsoft.Data.Sqlite — это упрощенный поставщик [ADO.NET](../../../framework/data/adonet/index.md) для SQLite. На основе этой библиотеки построен поставщик [Entity Framework Core](/ef/core/) для SQLite. Тем не менее, ее также можно использовать независимо или с другими библиотеками доступа к данным.

## <a name="installation"></a>Установка

Последняя стабильная версия доступна на сайте [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

### <a name="net-core-clitabnetcore-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Использование

В этой библиотеке реализуются общие абстракции ADO.NET для подключений, команд, модулей чтения данных и других элементов.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>См. также

* [Строки подключения](connection-strings.md)
* [Справочник по интерфейсам API](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [Синтаксис SQL](https://www.sqlite.org/lang.html)
