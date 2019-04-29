---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 6ae4712fb280418ad8cf17cd68a7bbcd9cf3b8a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785285"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)
Формирует ссылки на сущность в наборе сущностей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор CREATEREF используется для формирования ссылок на сущность в наборе сущностей. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
