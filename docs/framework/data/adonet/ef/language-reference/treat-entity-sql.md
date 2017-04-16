---
title: "TREAT (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# TREAT (Entity SQL)
Обрабатывает объект некоторого базового типа, как объект указанного производного типа.  
  
## Синтаксис  
  
```  
  
TREAT (expression as type)  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее сущность.  
  
> [!NOTE]
>  Тип указанного выражения должен быть подтипом указанного типа данных, либо тип данных должен быть подтипом типа выражения.  
  
 `type`  
 Тип сущности. Для типа должно быть указано пространство имен.  
  
> [!NOTE]
>  Указанное выражение должно быть подтипом указанного типа данных, либо тип данных должен быть подтипом данного выражения.  
  
## Возвращаемое значение  
 Значение указанного типа данных.  
  
## Заметки  
 Оператор TREAT предназначен для приведения связанных классов к базовому типу. Например, если тип `Employee` является производным от типа `Person`, а «p» относится к типу `Person`, то выражение `TREAT(p AS NamespaceName.Employee)` приводит общий экземпляр типа `Person` к типу `Employee`. Иными словами, он позволяет обрабатывать «p» как тип `Employee`.  
  
 Оператор TREAT используется в сценариях наследования, в которых можно выполнить запрос наподобие следующего.  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 Этот запрос приводит сущности `Person` к типу `Employee`. Если значение «p» фактически не относится к типу `Employee`, то выражение имеет значение `null`.  
  
> [!NOTE]
>  Указанное выражение ```Employee``` должно быть подтипом заданного типа данных `Person`, либо тип данных должен быть подтипом данного выражения. В противном случае это выражение вызовет ошибку во время компиляции.  
  
 Следующая таблица показывает, каким образом оператор TREAT работает с некоторыми стандартными и не очень часто используемыми конструкциями. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Шаблон|Поведение|  
|------------|---------------|  
|`TREAT (null AS EntityType)`|Возвращает `DbNull`.|  
|`TREAT (null AS ComplexType)`|Создает исключение.|  
|`TREAT (null AS RowType)`|Создает исключение\/|  
|`TREAT (EntityType AS EntityType)`|Возвращает значение `EntityType` или `null`.|  
|`TREAT (ComplexType AS ComplexType)`|Создает исключение.|  
|`TREAT (RowType AS RowType)`|Создает исключение.|  
  
## Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор TREAT используется для преобразования объекта типа Course в коллекцию объектов типа OnsiteCourse. Запрос основан на [модели School](http://msdn.microsoft.com/ru-ru/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Допускающие значения null структурированные типы](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)