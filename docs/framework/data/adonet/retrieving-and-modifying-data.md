---
title: "Извлечение и изменение данных в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 35de20b1cb35fdcd87a653f1ac202c01d345c317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Извлечение и изменение данных в ADO.NET
Основной функцией любого приложения базы данных является соединение с источником данных и извлечение данных, которые он содержит. Поставщики данных .NET Framework для ADO.NET служат в качестве моста между приложением и источником данных, что позволяет выполнять команды и получать данные с помощью **DataReader** или **DataAdapter** . Ключевой функцией любого приложения базы данных является возможность обновления данных, хранимых в базе данных. В ADO.NET обновление данных включает использование **DataAdapter** и <xref:System.Data.DataSet>, и **команда** объектов; может также включать использование транзакций.  
  
## <a name="in-this-section"></a>Содержание  
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
  
 [Извлечение идентификации или значений автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Пример сопоставления значений, созданных для **удостоверение** столбца в [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] таблицы или для **Autonumber** в таблицы Microsoft Access, со столбцом вставленной строки в таблице. Рассматривается слияние значений идентификаторов в объекте `DataTable`.  
  
 [Получение двоичных данных](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Описывается извлечение двоичных данных или крупных структур данных с помощью `CommandBehavior`.`SequentialAccess` для изменения поведения по умолчанию `DataReader`.  
  
 [Изменение данных с помощью хранимых процедур](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Описывается использование входных и выходных параметров хранимой процедуры для вставки строки в базу данных с возвратом нового значения идентификатора.  
  
 [Получение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Описывает получение доступных баз данных или каталогов, таблиц и представлений базы данных, существующих ограничений для таблиц и других сведений о схеме из источника данных.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Описывается модель фабрики поставщика и демонстрируется использование базовых классов в пространстве имен `System.Data.Common`.  
  
 [Трассировка данных в ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Описывается, как в ADO.NET реализованы встроенные функции трассировки данных.  
  
 [Счетчики производительности](../../../../docs/framework/data/adonet/performance-counters.md)  
 Описываются счетчики производительности, доступные для `SqlClient` и `OracleClient`.  
  
 [Асинхронное программирование](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Описывает поддержку [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] для асинхронного программирования.  
  
 [Поддержка потоковой передачи SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Описывает, как создавать приложения с потоком данных из [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] без полной загрузки в память.  
  
## <a name="see-also"></a>См. также  
 [Сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Защита приложений ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
