---
title: Определения типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 7abbe5dfed005a10955a385cadf12725a9450512
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761159"
---
# <a name="type-definitions-entity-sql"></a>Определения типов (Entity SQL)
Определение типа используется в операторе объявления встроенной функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="remarks"></a>Примечания  
 В операторе объявления для встроенной функции состоит из [ФУНКЦИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) ключевое слово и идентификатор, представляющий имя функции (например, «MyAvg»), следуют в списке определений параметров в скобки (для Пример «dues Collection(Decimal)").  
  
 Список определений параметров содержит ноль или более определений параметров. Каждое определение параметра состоит из идентификатора (имя параметра для функции, например «dues»), за которым следует определение типа (например, «Collection(Decimal)»).  
  
 Определения типов могут представлять:  
  
-   Тип идентификатора (например, «Int32» или «AdventureWorks.Order»).  
  
-   Ключевое слово `COLLECTION`, за которым следует определение другого типа в скобках (например, «Collection(AdventureWorks.Order)»).  
  
-   Ключевое слово ROW, за которым следует список определений свойств в скобках (например, «Row(x AdventureWorks.Order)»). Определения свойств имеют формат, например «`identifier type_definition`, `identifier type_definition`,...».  
  
-   Ключевое слово REF, за которым следует тип идентификатора в скобках (например, «Ref(AdventureWorks.Order)»). Для оператора определения типа REF требуется присутствие типа сущности в качестве аргумента. В качестве аргумента нельзя указать тип-примитив.  
  
 Определения типов также можно вкладывать друг в друга (например, «Collection(Row(x Ref(AdventureWorks.Order)))»).  
  
 Определения типов имеют следующие параметры:  
  
-   `IdentifierName supported_type`или  
  
-   `IdentifierName` COLLECTION(`type_definition`), или  
  
-   `IdentifierName` ROW(`property_definition`), или  
  
-   `IdentifierName` REF(`supported_entity_type`)  
  
 Параметр, определяющий свойство, - `IdentifierName type_definition`.  
  
 Поддерживаются все типы в текущем пространстве имен. Включаются как типы-примитивы, так и типы сущностей.  
  
 В поддерживаемые типы сущностей входят только типы сущностей текущего пространства имен. Сюда не входят типы-примитивы.  
  
## <a name="examples"></a>Примеры  
 Ниже приводится пример простого определения типа.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 Ниже приводится пример определения типа COLLECTION.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 Ниже приводится пример определения типа ROW.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 Ниже приводится пример определения типа REF.  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
