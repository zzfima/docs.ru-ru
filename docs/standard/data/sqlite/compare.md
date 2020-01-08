---
title: Сравнение с System. Data. SQLite
ms.date: 12/13/2019
description: Описывает некоторые различия между библиотеками Microsoft. Data. SQLite и System. Data. SQLite.
ms.openlocfilehash: dee90c132b108f2c876c0d8becc1b02035a47b61
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450282"
---
# <a name="comparison-to-systemdatasqlite"></a>Сравнение с System. Data. SQLite

В 2005 Роберт Симпсон создал System. Data. SQLite, поставщик SQLite для ADO.NET 2,0. В 2010 команда SQLite заняла обслуживание и разработку проекта. Также стоит отметить, что команда Mono Развилка код в 2007 как Mono. Data. SQLite. System. Data. SQLite имеет долгий журнал и превратился в стабильный и полнофункциональный поставщик ADO.NET с помощью инструментов Visual Studio. Новые выпуски продолжат поставлять сборки, совместимые с каждой версией .NET Framework обратно в версии 2,0 и даже .NET Compact Framework 3,5.

Первая версия .NET Core (выпущенная в 2016) была единственной, простой, современной и кросс-платформенной реализацией .NET. Устаревшие интерфейсы API и API с более современными альтернативными вариантами были намеренно удалены. ADO.NET не включал какие-либо интерфейсы API набора данных (включая DataTable и DataAdapter).

Группа Entity Framework была в некоторой степени знакома с базой кода System. Data. SQLite. Брице Ламбсон, участник команды EF, ранее помогал команде SQLite добавить поддержку Entity Framework версий 5 и 6. Брице также поэкспериментировать с собственной реализацией поставщика SQLite ADO.NET в то же время, когда планируется выполнение .NET Core. После длительного обсуждения Группа Entity Framework решила создать Microsoft. Data. SQLite на основе прототипа Брице. Это позволит им создавать новые упрощенные и современные реализации, которые будут согласованы с целями .NET Core.

В качестве примера того, что мы имеем в виду более современных, здесь приведен код для создания [определяемой пользователем функции](user-defined-functions.md) в System. Data. SQLite и Microsoft. Data. SQLite.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

В 2017 .NET Core 2,0 изменила стратегию. Было принято решение о том, что совместимость с .NET Framework была крайне важной для успешной работы .NET Core. Многие из удаленных API, включая API набора данных, были добавлены обратно. Как и для многих других, этот незаблокированный компонент System. Data. SQLite также позволяет перенести его в .NET Core. Исходная цель Microsoft. Data. SQLite — облегченная и современная, однако все еще остается. Дополнительные сведения об интерфейсах API ADO.NET, не реализованных в Microsoft. Data. SQLite, см. в разделе [ограничения ADO.NET](adonet-limitations.md) .

При добавлении новых функций в Microsoft. Data. SQLite учитывается структура System. Data. SQLite. Мы пытаемся, по возможности, уменьшить изменения между двумя, чтобы упростить переход между ними.

## <a name="data-types"></a>Типы данных

Крупнейшим различием между Microsoft. Data. SQLite и System. Data. SQLite является обработка типов данных. Как описано в разделе [типы данных](types.md), Microsoft. Data. SQLite не пытается скрыть базовую разрешающую часть SQLite, что позволяет указать любую произвольную строку в качестве типа столбца и имеет четыре примитивных типа: integer, Real, Text и BLOB.

System. Data. SQLite применяет дополнительную семантику к типам столбцов, сопоставляя их непосредственно с типами .NET. Это дает поставщику более строго типизированное поведение, но имеет некоторые грубые края. Например, им пришлось ввести новую инструкцию SQL (типы), чтобы указать типы столбцов выражений в инструкциях SELECT.

## <a name="connection-strings"></a>Строки подключения

Microsoft. Data. SQLite имеет гораздо меньше ключевых слов [строки подключения](connection-strings.md) . В следующей таблице показаны альтернативные варианты, которые можно использовать вместо.

| Ключевое слово          | Альтернатива                                         |
| ---------------- | --------------------------------------------------- |
| Размер кэша       | Отправить `PRAGMA cache_size = <pages>`                  |
| Время ожидания по умолчанию  | Использование свойства DefaultTimeout в Склитеконнектион |
| фаилифмиссинг    | Использование `Mode=ReadWrite`                                |
| фуллури          | Использование ключевого слова источника данных                         |
| Режим ведения журнала     | Отправить `PRAGMA journal_mode = <mode>`                 |
| Формат прежних версий    | Отправить `PRAGMA legacy_file_format = 1`                |
| Максимальное число страниц   | Отправить `PRAGMA max_page_count = <pages>`              |
| Размер страницы        | Отправить `PRAGMA page_size = <bytes>`                   |
| Только чтение        | Использование `Mode=ReadOnly`                                 |
| Synchronous      | Отправить `PRAGMA synchronous = <mode>`                  |
| URI-код              | Использование ключевого слова источника данных                         |
| UseUTF16Encoding | Отправить `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Авторизация

Microsoft. Data. SQLite не имеет API, предоставляющего обратный вызов авторизации SQLite. Чтобы отправить отзыв об этой функции, используйте [#13835](https://github.com/aspnet/EntityFrameworkCore/issues/13835) выпуска.

## <a name="data-change-notifications"></a>Уведомления об изменении данных

Microsoft. Data. SQLite не имеет интерфейсов API, предоставляя уведомления об изменении данных SQLite. Чтобы отправить отзыв об этой функции, используйте [#13827](https://github.com/aspnet/EntityFrameworkCore/issues/13827) выпуска.

## <a name="virtual-table-modules"></a>Модули виртуальной таблицы

Microsoft. Data. SQLite не имеет API для создания виртуальных модулей таблиц. Чтобы отправить отзыв об этой функции, используйте [#13823](https://github.com/aspnet/EntityFrameworkCore/issues/13823) выпуска.

## <a name="see-also"></a>См. также:

* [Типы данных](types.md)
* [Строки подключения](connection-strings.md)
* [Шифрование](encryption.md)
* [Ограничения ADO.NET](adonet-limitations.md)
* [Ограничения Dapper](dapper-limitations.md)
