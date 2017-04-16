---
title: "ISNULL (Entity SQL) | Microsoft Docs"
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
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ISNULL (Entity SQL)
Определяет, имеет ли выражение запроса значение null.  
  
## Синтаксис  
  
```  
  
expression IS [ NOT ] NULL  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение запроса. Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.  
  
 NOT  
 Логически инвертирует результат EDM.Boolean для IS NULL.  
  
## Возвращаемое значение  
 Значение `true`, если выражение `expression` возвращает значение NULL, либо значение `false` \- в противном случае.  
  
## Заметки  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Шаблон|Поведение|  
|------------|---------------|  
|null IS NULL|Возвращает `true`.|  
|TREAT \(null AS EntityType\) IS NULL|Возвращает `true`.|  
|TREAT \(null AS ComplexType\) IS NULL|Вызывает ошибку.|  
|TREAT \(null AS RowType\) IS NULL|Вызывает ошибку.|  
|EntityType IS NULL|Возвращает значение `true` или `false`.|  
|ComplexType IS NULL|Вызывает ошибку.|  
|RowType IS NULL|Вызывает ошибку.|  
  
## Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор IS NOT NULL определяет, отличается ли выражение запроса от NULL. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)