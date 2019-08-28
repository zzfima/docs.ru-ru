---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: b6335086ce5b61cf23db2bf967d1a82f322e83b3
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043622"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)

Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы. Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.

## <a name="syntax"></a>Синтаксис

```
[ SKIP n ]
```

## <a name="arguments"></a>Аргументы

`n` \
Число элементов, которые нужно пропустить.

## <a name="remarks"></a>Примечания

Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP. Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.

> [!NOTE]
> Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым. Его следует переписать, заменив выражение TOP выражением LIMIT.

> [!NOTE]
> В SQL Server 2000 использование инструкции SKIP с предложением ORDER BY в неключевых столбцах может привести к возврату неверных результатов. Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк. Это происходит из-за преобразования SKIP для SQL Server 2000. Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:
>
> `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Запрос в[процедуре: На странице в результатах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) запроса для указания порядка сортировки объектов, возвращаемых инструкцией SELECT, используется оператор ORDER BY с параметром SKIP.

## <a name="see-also"></a>См. также

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Практическое руководство. Страница с результатами запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Разбивка на страницы](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
