---
title: "Типы данных SQL Server и ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Типы данных SQL Server и ADO.NET
В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных.  Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server \(<xref:System.Data.SqlClient>\) предоставляет типизированные методы доступа для работы с данными SQL Server.  Для указания типов данных <xref:System.Data.SqlClient.SqlParameter> можно использовать перечисления классов <xref:System.Data.SqlDbType>.  
  
 Дополнительные сведения и таблицу с описанием сопоставлений типов данных SQL Server и .NET Framework приведены см. разделе [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).  
  
 В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес\-потребностей по работе с датами и временем, структурированными, частично структурированными и неструктурированными данными.  Новые типы данных описаны в электронной документации по SQL Server 2008.  
  
 Типы данных SQL Server, которые можно использовать в приложениях, зависят от используемой версии SQL Server.  Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.  
  
 **Электронная документация по SQL Server**  
  
1.  [Типы данных \(ядро СУБД\)](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## В этом подразделе  
 [SqlTypes и DataSet](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 Описывается поддержка типов для объекта `SqlTypes` в объекте `DataSet`.  
  
 [Обработка значений NULL](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 Демонстрируется работа со значениями NULL и тройственной логикой.  
  
 [Сравнение значений GUID и uniqueidentifier](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.  
  
 [Данные даты и времени](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 Описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.  
  
 [Большие, определяемые пользователем типы](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 Демонстрируется извлечение данных из определяемых пользователем типов данных большого размера, появившихся в SQL Server 2008.  
  
 [XML\-данные в SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 Описание работы с данными XML, извлеченными из SQL Server.  
  
## Ссылка  
 <xref:System.Data.DataSet>  
 Описывает класс `DataSet` и все его члены.  
  
 <xref:System.Data.SqlTypes>  
 Описывает пространство имен `SqlTypes` и все его элементы.  
  
 <xref:System.Data.SqlDbType>  
 Описывает перечисление `SqlDbType` и все его члены.  
  
 <xref:System.Data.DbType>  
 Описывает перечисление `DbType` и все его члены.  
  
## См. также  
 [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)   
 [Настройка параметров и типы данных параметров](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)   
 [Возвращающие табличное значение параметры](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)   
 [Двоичные данные и данные большого размера SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)