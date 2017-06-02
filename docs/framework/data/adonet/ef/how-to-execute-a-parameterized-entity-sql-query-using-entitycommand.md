---
title: "Как выполнить параметризованный запрос Entity SQL, использующий команды EntityCommand | Microsoft Docs"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как выполнить параметризованный запрос Entity SQL, использующий команды EntityCommand
В этом разделе показано выполнение запроса [!INCLUDE[esql](../../../../../includes/esql-md.md)] с параметрами с помощью объекта <xref:System.Data.EntityClient.EntityCommand>.  
  
### Выполнение кода в этом примере  
  
1.  Добавьте [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) к проекту и настройте проект на использование [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Для получения дополнительной информации см. [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Пример  
 Следующий пример показывает, как создать строку запроса с двумя параметрами.  Затем создается объект <xref:System.Data.EntityClient.EntityCommand>, добавляются два параметра в коллекцию <xref:System.Data.EntityClient.EntityParameter> этого объекта <xref:System.Data.EntityClient.EntityCommand> и совершается проход по элементам коллекции объектов `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## См. также  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/ru-ru/42048f03-c65c-4d98-b50a-3e7d537a63e8)   
 [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)