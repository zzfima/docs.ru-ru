---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как использовать параметры S'L.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401205"
---
# <a name="parameters"></a>Параметры

Параметры используются для защиты от атак на впрыски с Помощью СЗЛ. Вместо того, чтобы совмещать пользовательский ввод с операторами S'L, используйте параметры, чтобы гарантировать, что входные данные только когда-либо рассматриваются как буквальное значение и никогда не выполняются. В S'Lite параметры, как правило, допускаются в любом месте, буквальные допустимые в заявлениях S'L.

Параметры могут быть префиксированы либо `:`, `@`или `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Прослеживать [типы данных](types.md) для получения подробной информации о том, как значения .NET отображаются с значениями S'Lite.

## <a name="truncation"></a>Усечение

Используйте <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> свойство для усечения значений TEXT и BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Альтернативные типы

Иногда можно использовать альтернативный тип S'Lite. Сделайте это, <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> установив свойство.

Можно использовать следующие отображения альтернативного типа. Для карт по умолчанию [см.](types.md)

| Значение          | SqliteType | Remarks          |
| -------------- | ---------- | ---------------- |
| CHAR           | Целое число    | UTF-16           |
| Дата и время       | Real       | Джулиан день значение |
| DateTimeOffset | Real       | Джулиан день значение |
| Guid           | BLOB-объект       |                  |
| TimeSpan       | Real       | В дни          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Параметры вывода

S'Lite не поддерживает параметры вывода. Вместо этого значения возврата в результатах запроса.

## <a name="see-also"></a>См. также раздел

* [Типы данных](types.md)
