---
title: "Определения типов (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Определения типов (Entity SQL)
Определение типа используется в операторе объявления встроенной функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## Примечания  
 Оператор объявления для встроенной функции состоит из ключевого слова [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md), за которым следует идентификатор, представляющий имя функции \(например, «MyAvg»\), и список определений параметров в скобках \(например, «dues Collection\(Decimal\)»\).  
  
 Список определений параметров содержит ноль или более определений параметров.  Каждое определение параметра состоит из идентификатора \(имя параметра для функции, например «dues»\), за которым следует определение типа \(например, «Collection\(Decimal\)»\).  
  
 Определения типов могут представлять:  
  
-   Тип идентификатора \(например, «Int32» или «AdventureWorks.Order»\).  
  
-   Ключевое слово `COLLECTION`, за которым следует определение другого типа в скобках \(например, «Collection\(AdventureWorks.Order\)»\).  
  
-   Ключевое слово ROW, за которым следует список определений свойств в скобках \(например, «Row\(x AdventureWorks.Order\)»\).  Определения свойств имеют следующий формат: «`identifier type_definition`, `identifier type_definition`, ...».  
  
-   Ключевое слово REF, за которым следует тип идентификатора в скобках \(например, «Ref\(AdventureWorks.Order\)»\).  Для оператора определения типа REF требуется присутствие типа сущности в качестве аргумента.  В качестве аргумента нельзя указать тип\-примитив.  
  
 Определения типов также можно вкладывать друг в друга \(например, «Collection\(Row\(x Ref\(AdventureWorks.Order\)\)\)»\).  
  
 Определения типов имеют следующие параметры:  
  
-   `IdentifierName supported_type`или  
  
-   `IdentifierName` COLLECTION\(`type_definition`\), или  
  
-   `IdentifierName` ROW\(`property_definition`\), или  
  
-   `IdentifierName` REF\(`supported_entity_type`\)  
  
 Параметр, определяющий свойство, \- `IdentifierName type_definition`.  
  
 Поддерживаются все типы в текущем пространстве имен.  Включаются как типы\-примитивы, так и типы сущностей.  
  
 В поддерживаемые типы сущностей входят только типы сущностей текущего пространства имен.  Сюда не входят типы\-примитивы.  
  
## Примеры  
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
  
## См. также  
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)