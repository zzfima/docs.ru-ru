---
title: "Типы данных SQL Server и ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a>Типы данных SQL Server и ADO.NET
В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных. Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server. Для указания типов данных <xref:System.Data.SqlDbType> можно использовать перечисления классов <xref:System.Data.SqlClient.SqlParameter>.  
  
 Дополнительные сведения и таблицу с описанием данных введите сопоставления между типами данных .NET Framework и SQL Server см. в разделе [сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).  
  
 В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей по работе с датами и временем, структурированными, частично структурированными и неструктурированными данными. Новые типы данных описаны в электронной документации по SQL Server 2008.  
  
 Типы данных SQL Server, которые можно использовать в приложениях, зависят от используемой версии SQL Server. Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.  
  
 **Электронная документация по SQL Server**  
  
1.  [Типы данных (ядро СУБД)](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a>Содержание  
 [Типы SQLType и набор данных](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 Описывается поддержка типов для объекта `SqlTypes` в объекте `DataSet`.  
  
 [Обработка значений Null](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 Демонстрируется работа со значениями NULL и тройственной логикой.  
  
 [Сравнение GUID и uniqueidentifier значения](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.  
  
 [Данных даты и времени](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 Описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.  
  
 [Больших определяемых пользователем типов](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 Демонстрируется извлечение данных из определяемых пользователем типов данных большого размера, появившихся в SQL Server 2008.  
  
 [XML-данных в SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 Описание работы с данными XML, извлеченными из SQL Server.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.DataSet>  
 Описывает класс `DataSet` и все его члены.  
  
 <xref:System.Data.SqlTypes>  
 Описывает пространство имен `SqlTypes` и все его элементы.  
  
 <xref:System.Data.SqlDbType>  
 Описывает перечисление `SqlDbType` и все его члены.  
  
 <xref:System.Data.DbType>  
 Описывает перечисление `DbType` и все его члены.  
  
## <a name="see-also"></a>См. также  
 [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Настройка параметров и типов данных параметров](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Возвращающие табличные значения параметров](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [Двоичные данные и данные большого объема SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
