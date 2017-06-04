---
title: "Как выполнить запрос, возвращающий результаты RefType | Microsoft Docs"
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
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как выполнить запрос, возвращающий результаты RefType
В этом подразделе показано выполнение команды для концептуальной модели с помощью объекта <xref:System.Data.EntityClient.EntityCommand>, а также получение результатов <xref:System.Data.Metadata.Edm.RefType> с помощью <xref:System.Data.EntityClient.EntityDataReader>.  
  
### Выполнение кода в этом примере  
  
1.  Добавьте [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) к проекту и настройте проект на использование [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Для получения дополнительной информации см. [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Пример  
 В этом примере выполняется запрос, который возвращает результаты <xref:System.Data.Metadata.Edm.RefType>.  Если следующий запрос передан в качестве аргумента функции `ExectueRefTypeQuery`, то функция возвращает ссылку на сущность:  
  
 [!code-csharp[DP EntityServices Concepts#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#ref2)]
 [!code-sql[DP EntityServices Concepts#REF2](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref2)]  
  
 Передавая параметризованный запрос, подобный следующему, добавьте объекты <xref:System.Data.EntityClient.EntityParameter> к свойству <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> объекта <xref:System.Data.EntityClient.EntityCommand>.  
  
 [!code-csharp[DP EntityServices Concepts#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#ref3)]
 [!code-sql[DP EntityServices Concepts#REF3](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Поставщик EntityClient для платформы Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)