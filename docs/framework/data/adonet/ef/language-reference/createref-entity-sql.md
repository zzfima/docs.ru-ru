---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 3659f2c0690b00e728630c6e77308ba9d424bb1b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833926"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)
Формирует ссылки на сущность в наборе сущностей.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Аргументы  
 `entityset_identifier`  
 Идентификатор набора сущностей, а не строковый литерал.  
  
 `row_typed_expression`  
 Выражение типа строки таблицы, соответствующее свойствам ключа типа сущности.  
  
## <a name="remarks"></a>Примечания  
 Выражение`row_typed_expression` должно быть структурно эквивалентно типу ключа для данной сущности. Это значит, что оно должно иметь такое же число и типы полей, расположенные в том же порядке, как и ключи сущности.  
  
 В приведенном далее примере Orders и BadOrders являются наборами сущностей типа Order, и предполагается, что идентификатор Id является единственным свойством ключа для типа Order. Этот пример иллюстрирует, как можно сформировать ссылку на сущность в наборе сущностей BadOrders. Отметим, что ссылка может быть висячей.  Это значит, что в действительности ссылка может не указывать на конкретную сущность. В этом случае оператор `DEREF` для этой ссылки возвратит значение null.  
  
```sql  
SELECT CreateRef(LOB.BadOrders, row(o.Id))
FROM LOB.Orders AS o
```  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор CREATEREF используется для формирования ссылок на сущность в наборе сущностей. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CREATEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#createref)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по Entity SQL](entity-sql-reference.md)
- [DEREF](deref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [REF](ref-entity-sql.md)
