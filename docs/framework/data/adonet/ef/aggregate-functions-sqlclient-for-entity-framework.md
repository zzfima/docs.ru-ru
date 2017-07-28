---
title: "Статистические функции (SqlClient для Entity Framework) | Microsoft Docs"
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
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Статистические функции (SqlClient для Entity Framework)
Поставщик данных .NET Framework для SQL Server \(SqlClient\) предоставляет агрегатные функции.  Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение.  Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.  Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.  
  
 В следующей таблице описаны агрегатные функции SqlClient.  
  
|Функция|Описание|  
|-------------|--------------|  
|`AVG(` `expression` `)`|Возвращает среднее значение для значений в коллекции.<br /><br /> Значения NULL не учитываются.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`,  `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]|  
|`CHECKSUM_AGG(` `collection` `)`|Возвращает контрольную сумму значений в коллекции.<br /><br /> Значения NULL не учитываются.<br /><br /> **Аргументы**<br /><br /> Collection \(`Int32`\).<br /><br /> **Возвращаемое значение**<br /><br /> `Int32`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]|  
|`COUNT(` `expression` `)`|Возвращает число элементов в коллекции в виде `Int32`.<br /><br /> **Аргументы**<br /><br /> Тип Collection \(T\), где T — один из следующих типов:<br /><br /> `Guid` \(не возвращен в SQL Server 2000\),<br /><br /> `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` или `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> `Int32`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]|  
|`COUNT_BIG(` `expression` `)`|Возвращает число элементов в коллекции в виде `bigint`.<br /><br /> **Аргументы**<br /><br /> Тип Collection \(T\), где T — один из следующих типов:<br /><br /> `Guid` \(не возвращается в SQL Server 2000\), `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` или `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> `Int64`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]|  
|`MAX(` `expression` `)`|Возвращает максимальное значение, содержащееся в коллекции.<br /><br /> **Аргументы**<br /><br /> Collection \(T\), где T может быть любым из следующих типов: `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]|  
|`MIN(` `expression` `)`|Возвращает минимальное значение в коллекции.<br /><br /> **Аргументы**<br /><br /> Collection \(T\), где T может быть любым из следующих типов: `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`,<br /><br /> `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]|  
|`STDEV(` `expression` `)`|Возвращает статистическое стандартное отклонение всех значений в указанном выражении.<br /><br /> **Аргументы**<br /><br /> Collection \(`Double`\).<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]|  
|`STDEVP(` `expression` `)`|Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.<br /><br /> **Аргументы**<br /><br /> Collection \(`Double`\).<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]|  
|`SUM(` `expression` `)`|Возвращает сумму всех значений в коллекции.<br /><br /> **Аргументы**<br /><br /> Collection \(T\), где T может быть любым из следующих типов: `Int32`, `Int64`, `Double`, `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]|  
|`VAR(` `expression` `)`|Возвращает статистическую дисперсию всех значений в указанном выражении.<br /><br /> **Аргументы**<br /><br /> Collection \(`Double`\).<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]|  
|`VARP(` `expression` `)`|Возвращает статистическую дисперсию совокупности всех значений в указанном выражении.<br /><br /> **Аргументы**<br /><br /> Collection \(`Double`\).<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]|  
  
 Дополнительные сведения об агрегатных функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Агрегатные функции \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=115906)|[Агрегатные функции \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=115903)|[Агрегатные функции \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=115907)|  
  
## См. также  
 [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)   
 [Канонические статистические функции](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)