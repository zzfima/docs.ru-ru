---
title: "Команды и параметры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Команды и параметры
После установки соединения с источником данных при помощи объекта <xref:System.Data.Common.DbCommand> можно выполнять команды и возвращать результаты из источника данных.  Команду можно создать с помощью одного из используемых конструкторов команд для поставщика данных .NET Framework.  Конструкторы могут принимать необязательные аргументы, например инструкцию SQL для выполнения в источнике данных, объект <xref:System.Data.Common.DbConnection> или объект <xref:System.Data.Common.DbTransaction>.  Эти объекты также можно настроить как свойства команды.  При помощи метода <xref:System.Data.Common.DbConnection.CreateCommand%2A> объекта `DbConnection` также можно создать команду для конкретного соединения.  Инструкцию SQL, выполняемую командой, можно настроить с помощью свойства <xref:System.Data.Common.DbCommand.CommandText%2A>.  
  
 У каждого поставщика данных .NET Framework, имеющегося в платформе .NET Framework, есть объект `Command`.  Поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbCommand>, поставщик данных .NET Framework для SQL Server \- объект <xref:System.Data.SqlClient.SqlCommand>, поставщик данных .NET Framework для ODBC \- объект <xref:System.Data.Odbc.OdbcCommand>, а поставщик данных .NET Framework для Oracle \- объект <xref:System.Data.OracleClient.OracleCommand>.  
  
## В этом подразделе  
 [Выполнение команды](../../../../docs/framework/data/adonet/executing-a-command.md)  
 Описание объекта ADO.NET `Command` и его использования для выполнения запросов и команд в источнике данных.  
  
 [Настройка параметров и типы данных параметров](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 Описание работы с параметрами `Command`, включая направление, типы данных и синтаксис параметров.  
  
 [Создание команд с помощью объекта CommandBuilders](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 Описание использования построителей команд для автоматического формирования команд INSERT, UPDATE и DELETE для адаптера `DataAdapter`, у которого имеется команда SELECT с одной таблицей.  
  
 [Получение одиночного значения из базы данных](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 Описывается использование метода `ExecuteScalar` объекта `Command` для возврата из запроса к базе данных одиночного значения.  
  
 [Использование команд для изменения данных](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 Описывается использование поставщика данных для выполнения хранимых процедур или инструкций языка описания данных DDL.  
  
## См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)