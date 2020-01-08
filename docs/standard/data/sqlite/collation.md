---
title: Collation
ms.date: 12/13/2019
description: Узнайте, как создать настраиваемую последовательность сортировки.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450288"
---
# <a name="collation"></a>Collation

При сравнении текстовых значений с целью определения порядка и равенства в SQLite используются последовательности сортировки. Можно указать, какие параметры сортировки следует использовать при создании столбцов или по операциям в SQL-запросах. По умолчанию SQLite содержит три последовательности сортировки.

| Collation | Описание                               |
| --------- | ----------------------------------------- |
| RTRIM     | Игнорирует конечные пробелы               |
| CASE    | Без учета регистра для символов ASCII A – Z |
| BINARY    | С учетом регистра. Сравнивает байты напрямую   |

## <a name="custom-collation"></a>Пользовательские параметры сортировки

Можно также определить собственные последовательности сортировки или переопределить встроенные, используя <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>. В следующем примере показано переопределение параметров сортировки в параметре CASE для поддержки символов Юникода. [Полный пример кода](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) доступен на сайте GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like - оператор

Оператор LIKE в SQLite не учитывает параметры сортировки. Реализация по умолчанию имеет ту же семантику, что и параметры сортировки в параметре CASE. Символы ASCII от A до Z не учитывают регистр.

Можно легко сделать оператор LIKE с учетом регистра с помощью следующей инструкции pragma:

```sql
PRAGMA case_sensitive_like = 0
```

Дополнительные сведения о переопределении реализации оператора LIKE см. в разделе [определяемые пользователем функции](user-defined-functions.md) .

## <a name="see-also"></a>См. также:

* [Определяемые пользователем функции](user-defined-functions.md)
* [Синтаксис SQL](https://www.sqlite.org/lang.html)
