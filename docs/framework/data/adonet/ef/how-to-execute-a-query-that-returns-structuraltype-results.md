---
title: "Как выполнить запрос, возвращающий результаты типа StructuralType | Microsoft Docs"
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
  - "jsharp"
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как выполнить запрос, возвращающий результаты типа StructuralType
В этом подразделе показано выполнение команды для концептуальной модели с помощью объекта <xref:System.Data.EntityClient.EntityCommand>, а также получение результатов <xref:System.Data.Metadata.Edm.StructuralType> с помощью <xref:System.Data.EntityClient.EntityDataReader>.  Классы <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> и <xref:System.Data.Metadata.Edm.ComplexType> являются производными класса <xref:System.Data.Metadata.Edm.StructuralType>.  
  
### Выполнение кода в этом примере  
  
1.  Добавьте [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) к проекту и настройте проект на использование [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Для получения дополнительной информации см. [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Пример  
 В этом примере выполняется запрос, который возвращает результаты <xref:System.Data.Metadata.Edm.EntityType>.  При передаче следующего запроса в качестве аргумента функции `ExecuteStructuralTypeQuery` функция отобразит подробные сведения о `Products`:  
  
 [!code-csharp[DP EntityServices Concepts#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#selectproduct)]
 [!code-sql[DP EntityServices Concepts#SelectProduct](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#selectproduct)]  
  
 Передавая параметризованный запрос, подобный следующему, добавьте объекты <xref:System.Data.EntityClient.EntityParameter> к свойству <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> объекта <xref:System.Data.EntityClient.EntityCommand>.  
  
 [!code-csharp[DP EntityServices Concepts#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#greater_or_equals)]
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Поставщик EntityClient для платформы Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)