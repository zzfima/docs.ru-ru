---
title: Типы данных SQL Server и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 9baffc7a439c851ead7ec0e12899adf418174e22
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979863"
---
# <a name="sql-server-data-types-and-adonet"></a>Типы данных SQL Server и ADO.NET
В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных. Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server. Для указания типов данных <xref:System.Data.SqlDbType> можно использовать перечисления классов <xref:System.Data.SqlClient.SqlParameter>.  
  
 Дополнительные сведения и таблица с описанием сопоставлений типов данных между типами данных SQL Server и .NET Framework см. в разделе [SQL Server сопоставления типов данных](../sql-server-data-type-mappings.md).  
  
 В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей по работе с датами и временем, структурированными, частично структурированными и неструктурированными данными. Новые типы данных описаны в электронной документации по SQL Server 2008.  
  
 Типы данных SQL Server, которые можно использовать в приложениях, зависят от используемой версии SQL Server. Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.  
  
 **Электронная документация по SQL Server**  
  
1. [Типы данных (ядро СУБД)](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Типы SqlType и набор данных](sqltypes-and-the-dataset.md)  
 Описывается поддержка типов для объекта `SqlTypes` в объекте `DataSet`.  
  
 [Обработка значений NULL](handling-null-values.md)  
 Демонстрируется работа со значениями NULL и тройственной логикой.  
  
 [Сравнение значений идентификатора GUID и uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.  
  
 [Данные даты и времени](date-and-time-data.md)  
 Описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.  
  
 [Большие определяемые пользователем типы](large-udts.md)  
 Демонстрируется извлечение данных из определяемых пользователем типов данных большого размера, появившихся в SQL Server 2008.  
  
 [Данные XML в SQL Server](xml-data-in-sql-server.md)  
 Описание работы с данными XML, извлеченными из SQL Server.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Data.DataSet>  
 Описывает класс `DataSet` и все его члены.  
  
 <xref:System.Data.SqlTypes>  
 Описывает пространство имен `SqlTypes` и все его элементы.  
  
 <xref:System.Data.SqlDbType>  
 Описывает перечисление `SqlDbType` и все его члены.  
  
 <xref:System.Data.DbType>  
 Описывает перечисление `DbType` и все его члены.  
  
## <a name="see-also"></a>См. также:

- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Возвращающие табличное значение параметры](table-valued-parameters.md)
- [Двоичные данные и данные большого объема SQL Server](sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
