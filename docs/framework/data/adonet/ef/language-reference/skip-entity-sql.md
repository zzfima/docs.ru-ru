---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 75140384823588b8f6785de00b0ab3cd17314a3f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319339"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)

Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы. Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.

## <a name="syntax"></a>Синтаксис

```sql
[ SKIP n ]
```

## <a name="arguments"></a>Аргументы

`n` \
Число элементов, которые нужно пропустить.

## <a name="remarks"></a>Заметки

Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP. Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.

> [!NOTE]
> Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым. Его следует переписать, заменив выражение TOP выражением LIMIT.

> [!NOTE]
> В SQL Server 2000 использование инструкции SKIP с предложением ORDER BY в неключевых столбцах может привести к возврату неверных результатов. Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк. Это происходит из-за преобразования SKIP для SQL Server 2000. Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

Запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в статье « [инструкции. Просмотр результатов запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) » использует оператор ORDER BY с ПАРАМЕТРом Skip, чтобы указать порядок сортировки, используемый для объектов, возвращаемых инструкцией SELECT.

## <a name="see-also"></a>См. также

- [ORDER BY](order-by-entity-sql.md)
- [Пошаговое руководство. Просмотр результатов запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Разбивка на страницы](paging-entity-sql.md)
- [TOP](top-entity-sql.md)
