---
title: "Получение и изменение данных в ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Получение и изменение данных в ADO.NET
Основной функцией любого приложения базы данных является соединение с источником данных и извлечение данных, которые он содержит.  Поставщики данных .NET Framework ADO.NET обеспечивают взаимодействие между приложением и источником данных, позволяя выполнять команды и получать данные с помощью **DataReader** или **DataAdapter**.  Ключевой функцией любого приложения базы данных является возможность обновления данных, хранимых в базе данных.  В ADO.NET обновление данных включает использование **DataAdapter** и <xref:System.Data.DataSet>, а также объектов **Command**. Обновление может включать использование транзакций.  
  
## В этом подразделе  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 Описывается установка подключения к источнику данных и работа с событиями подключения.  
  
 [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)  
 Содержит разделы, в которых описываются различные аспекты использования строк подключения, в том числе ключевых слов строки подключения, сведения о безопасности, их хранение и извлечение.  
  
 [Организация пулов соединений](../../../../docs/framework/data/adonet/connection-pooling.md)  
 Описывает пул соединений для поставщиков данных платформы .NET Framework.  
  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 Содержит разделы, в которых описывается создание команд и построителей команд, настройка параметров и выполнение команд для извлечения и изменения данных.  
  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 Содержит разделы, в которых описываются объекты DataReader, DataAdapter, параметры, обработка событий объекта и выполнение пакетных операций.  
  
 [Транзакции и параллелизм](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 Содержит разделы, в которых описывается выполнение локальных транзакций, распределенных транзакций и работа с оптимистичным параллелизмом.  
  
 [Получение значений идентификаторов или автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Содержит пример сопоставления значений, созданных для столбца **identity** таблицы [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] или для поля **Autonumber** таблицы Microsoft Access, со столбцом строки, вставленной в таблицу.  Рассматривается слияние значений идентификаторов в объекте `DataTable`.  
  
 [Получение двоичных данных](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Описывается извлечение двоичных данных или крупных структур данных с помощью метода `CommandBehavior`.`SequentialAccess` для изменения поведения по умолчанию объекта `DataReader`.  
  
 [Изменение данных с помощью хранимых процедур](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Описывается использование входных и выходных параметров хранимой процедуры для вставки строки в базу данных с возвратом нового значения идентификатора.  
  
 [Получение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Описывает получение доступных баз данных или каталогов, таблиц и представлений базы данных, существующих ограничений для таблиц и других сведений о схеме из источника данных.  
  
 [Объекты DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Описывается модель фабрики поставщика и демонстрируется использование базовых классов в пространстве имен `System.Data.Common`.  
  
 [Трассировка данных в ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Описывается, как в ADO.NET реализованы встроенные функции трассировки данных.  
  
 [Счетчики производительности](../../../../docs/framework/data/adonet/performance-counters.md)  
 Описываются счетчики производительности, доступные для `SqlClient` и `OracleClient`.  
  
 [Асинхронное программирование](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Описывает поддержку [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] для асинхронного программирования.  
  
 [Поддержка потоковой передачи SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Описывает, как создавать приложения с потоком данных из [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] без полной загрузки в память.  
  
## См. также  
 [Сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)   
 [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Защита приложений ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)