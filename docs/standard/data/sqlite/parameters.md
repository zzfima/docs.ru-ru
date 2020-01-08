---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как использовать параметры SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450426"
---
# <a name="parameters"></a>Параметры

Параметры используются для защиты от атак путем внедрения кода SQL. Вместо сцепления вводимых пользователем данных с инструкциями SQL используйте параметры, чтобы гарантировать, что входные данные всегда рассматриваются как литеральное значение и никогда не выполняются. В SQLite параметры обычно разрешены в любом месте, где допускается использование литерала в инструкциях SQL.

Для параметров можно использовать префикс `:`, `@`или `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Сведения о том, как значения .NET сопоставляются со значениями SQLite, см. в разделе [типы данных](types.md) .

## <a name="truncation"></a>Усечение

Используйте свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> для усечения значений текста и больших двоичных объектов.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Альтернативные типы

Иногда может потребоваться использовать альтернативный тип SQLite. Это можно сделать, задав свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.

Можно использовать следующие альтернативные сопоставления типов. Сопоставления по умолчанию см. в разделе [типы данных](types.md).

| {2&gt;Value&lt;2}          | склитетипе | Заметки          |
| -------------- | ---------- | ---------------- |
| Char           | Целое число    | UTF-16           |
| DateTime       | Real       | Значение юлианского дня |
| DateTimeOffset | Real       | Значение юлианского дня |
| Идентификатор GUID           | Большой двоичный объект       |                  |
| TimeSpan       | Real       | В днях          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Параметры вывода

SQLite не поддерживает выходные параметры. Вместо этого возвращаются значения в результатах запроса.

## <a name="see-also"></a>См. также:

* [Типы данных](types.md)
