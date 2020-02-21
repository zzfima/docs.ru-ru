---
title: Обзор
ms.date: 12/13/2019
description: Общие сведения о Microsoft.Data.Sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543603"
---
# <a name="microsoftdatasqlite-overview"></a>Общие сведения о Microsoft.Data.Sqlite

Microsoft.Data.Sqlite — это упрощенный поставщик [ADO.NET](../../../framework/data/adonet/index.md) для SQLite. На основе этой библиотеки построен поставщик [Entity Framework Core](/ef/core/) для SQLite. Тем не менее, ее также можно использовать независимо или с другими библиотеками доступа к данным.

## <a name="installation"></a>Установка

Последняя стабильная версия доступна на сайте [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

### <a name="net-core-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Использование

В этой библиотеке реализуются общие абстракции ADO.NET для подключений, команд, модулей чтения данных и других элементов.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>См. также

* [Строки подключения](connection-strings.md)
* [Справочник по интерфейсам API](/dotnet/api/?view=msdata-sqlite-3.0)
* [Синтаксис SQL](https://www.sqlite.org/lang.html)
