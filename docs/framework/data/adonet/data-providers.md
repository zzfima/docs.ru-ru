---
title: Поставщики данных .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: f821088375bf1df01e75de5e0c226334baca113f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074031"
---
# <a name="net-framework-data-providers"></a>Поставщики данных .NET Framework
Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] используется для установления соединения с базой данных, выполнения команд и получения результатов. Эти результаты обрабатываются непосредственно, помещаются в <xref:System.Data.DataSet> , чтобы по мере необходимости они были доступны для пользователей вместе с данными из нескольких источников, либо распределяются между уровнями. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщики данных являются упрощенными и создают минимальный уровень между источником данных и кода, повышая производительность без ущерба для функциональных возможностей.  
  
 В следующей таблице приведен список поставщиков данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных|Описание|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server|Предоставляет доступ к данным для Microsoft SQL Server. Использует пространство имен <xref:System.Data.SqlClient> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для OLE DB|Для источников данных OLE DB. Использует пространство имен <xref:System.Data.OleDb> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для ODBC|Для источников данных ODBC. Использует пространство имен <xref:System.Data.Odbc> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для Oracle|Для источников данных Oracle. Источник данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle поддерживает клиентское программное обеспечение версии 8.1.7 и старше и использует пространство имен <xref:System.Data.OracleClient> .|  
|EntityClient - поставщик|Предоставляет доступ к данным для приложений модели EDM (Entity Data Model). Использует пространство имен <xref:System.Data.EntityClient> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server Compact 4.0.|Предоставляет доступ к данным для Microsoft SQL Server Compact 4.0. Использует пространство имен [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Основные объекты поставщиков данных .NET Framework  
 В следующей таблице приведены четыре основных объекта, из которых состоит поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  
  
|Object|Описание|  
|------------|-----------------|  
|`Connection`|Устанавливает соединение с конкретным источником данных. Базовым классом для всех объектов `Connection` является <xref:System.Data.Common.DbConnection> .|  
|`Command`|Выполняет команду в источнике данных. Обеспечивает доступность `Parameters` и может выполнять команды в области `Transaction` из `Connection`. Базовым классом для всех объектов `Command` является <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Считывает из источника данных однопроходный поток данных только для чтения. Базовым классом для всех объектов `DataReader` является <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Заполняет `DataSet` и выполняет обновления в источнике данных. Базовым классом для всех объектов `DataAdapter` является <xref:System.Data.Common.DbDataAdapter> .|  
  
 Кроме приведенных выше основных классов поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] содержит классы, представленные в следующей таблице.  
  
|Object|Описание|  
|------------|-----------------|  
|`Transaction`|Прикрепляет команды к транзакциям в источнике данных. Базовым классом для всех объектов `Transaction` является <xref:System.Data.Common.DbTransaction> . ADO.NET также поддерживает транзакции, использующие классы в пространстве имен <xref:System.Transactions> .|  
|`CommandBuilder`|Объект помощника, автоматически формирующий свойства команд `DataAdapter` или извлекающий сведения о параметрах из хранимой процедуры и заполняющий коллекцию `Parameters` объекта `Command` . Базовым классом для всех объектов `CommandBuilder` является <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Объект помощника, обеспечивающий простой способ создания и управления содержимым строки соединения, которую используют объекты `Connection` . Базовым классом для всех объектов `ConnectionStringBuilder` является <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Определяет входные, выходные и возвращаемые значения параметров для команд и хранимых процедур. Базовым классом для всех объектов `Parameter` является <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Возвращается при возникновении ошибки в источнике данных. Для ошибок клиентов поставщики данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] вызывают исключение [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Базовым классом для всех объектов `Exception` является <xref:System.Data.Common.DbException> .|  
|`Error`|Отображает сведения, относящиеся к предупреждениям и ошибкам, возвращенным источником данных.|  
|`ClientPermission`|Атрибуты управления доступом, поставляемые с кодом поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Базовым классом для всех объектов `ClientPermission` является <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Поставщик данных .NET framework для SQL Server (SqlClient)  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server (SqlClient) использует собственный протокол для взаимодействия с SQL Server. Это простой и высокопроизводительный он оптимизирован для доступа к SQL Server напрямую, не добавляя к слою OLE DB и Open Database Connectivity (ODBC). На рисунке ниже сравнивается [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для SQL Server с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для OLE DB. Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB связывается с источником данных OLE DB с помощью компонента службы OLE DB, предоставляющим пулы соединений и службы транзакций, и поставщиком OLE DB для источника данных.  
  
> [!NOTE]
>  Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC имеет схожую архитектуру с поставщиком данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB. Например, он вызывает компонент службы ODBC.  
  
 ![Поставщики данных](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Сравнение поставщика данных .NET Framework для SQL Server и поставщика данных .NET Framework для OLE DB  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для классов SQL Server находится в <xref:System.Data.SqlClient> пространства имен.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для SQL Server, по умолчанию автоматически задействуется в транзакции и получает сведения о транзакциях из служб компонентов Windows или <xref:System.Transactions>. Дополнительные сведения см. в разделе [транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.SqlClient` .  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Поставщик данных .NET Framework для OLE DB  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB (OleDb) обеспечивает доступ к данным с помощью собственной реализации OLE DB через COM-взаимодействие. Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB по умолчанию автоматически задействуется в транзакции и получает сведения о транзакциях из служб компонентов Windows. Дополнительные сведения см. в разделе [транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 В следующей таблице представлены поставщики данных, протестированные на совместимость с [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Драйвер|Поставщик|  
|------------|--------------|  
|SQLOLEDB|Поставщик Microsoft OLE DB для SQL Server|  
|MSDAORA|Поставщик Microsoft OLE DB для Oracle|  
|Microsoft.Jet.OLEDB.4.0|Поставщик OLE DB для Microsoft Jet|  
  
> [!NOTE]
>  Использование базы данных Access (Jet) в качестве источника данных для многопоточных приложений, например приложений [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , не рекомендуется. Если требуется использовать Jet в качестве источника данных для приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , нужно понимать, что приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , связывающиеся с базой данных Access, могут столкнуться с проблемами соединения.  
  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB не поддерживает интерфейсы OLE DB версии 2.5. Поставщики OLE DB, которым требуется поддержка интерфейсов OLE DB 2.5, будут работать неправильно с поставщиками данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB. Это относится к поставщику OLE DB для Exchange (Майкрософт) и поставщику Microsoft OLE DB для публикаций в Интернете.  
  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB не работает с поставщиком OLE DB для ODBC (MSDASQL). Для доступа к источнику данных ODBC с помощью [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]используется поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для классов OLE DB находится в <xref:System.Data.OleDb> пространства имен. Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.OleDb` .  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Поставщик данных .NET Framework для ODBC  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC (Odbc) использует для доступа к данным собственный диспетчер драйверов ODBC. Поставщик данных ODBC поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций поставщик данных ODBC по умолчанию автоматически задействуется в транзакции и получает сведения о транзакциях из служб компонентов Windows. Дополнительные сведения см. в разделе [транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 В следующей таблице представлены драйверы ODBC, протестированные на совместимость с [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Драйвер|  
|------------|  
|SQL Server|  
|Microsoft ODBC для Oracle|  
|Драйвер Microsoft Access (*.mdb)|  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для классов ODBC находится в <xref:System.Data.Odbc> пространства имен.  
  
 Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.Odbc` .  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC требует MDAC 2.6 или более поздней версии, рекомендуется MDAC 2.8 с пакетом обновления 1 (SP1). Компоненты MDAC 2.8 с пакетом обновления 1 (SP1) можно скачать на веб-сайте [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173)(центр разработчиков средств доступа к данным и их хранения).  
  
## <a name="net-framework-data-provider-for-oracle"></a>Поставщик данных .NET Framework для Oracle  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle (OracleClient) обеспечивает доступ к источникам данных Oracle через клиентское ПО Oracle для связи. Поставщик данных поддерживает клиентское ПО Oracle версии 8.1.7 или более поздней версии. Поставщик данных поддерживает как локальные, так и распределенные транзакции. Дополнительные сведения см. в разделе [транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle требует установки в системе клиентского ПО Oracle для связи (версии 8.1.7 или более поздней) до того, как можно будет соединяться с источником данных Oracle.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для классов Oracle находится в <xref:System.Data.OracleClient> пространства имен и содержится в `System.Data.OracleClient.dll` сборки. При компиляции приложения, использующего этот источник данных, необходимо ссылаться как на `System.Data.dll` , так и на `System.Data.OracleClient.dll` .  
  
 Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.OracleClient` .  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>Выбор поставщика данных платформы .NET Framework  
 Использование поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] может повысить производительность, возможности и целостность приложения, в зависимости от структуры приложения и источника данных. В следующей таблице приведены преимущества и ограничения каждого источника данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  
  
|Поставщик|Примечания|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server|Рекомендуется для одноуровневых приложений, использующих Microsoft SQL Server.<br /><br /> Рекомендуется для одноуровневых приложений, использующих Microsoft Database Engine (MSDE) или SQL Server.<br /><br /> Рекомендуется использовать поставщик OLE DB для SQL Server (SQLOLEDB) с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для OLE DB.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для OLE DB|Для SQL Server [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для SQL Server, рекомендуется вместо этого поставщика.<br /><br /> Рекомендуется для одноуровневых приложений, использующих базы данных Microsoft Access. Базы данных Microsoft Access не рекомендуется использовать для приложений среднего уровня.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для ODBC|Рекомендуется для приложений среднего уровня и одноуровневых приложений, использующих источники данных ODBC.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Поставщик данных для Oracle|Рекомендуется для приложений среднего уровня и одноуровневых приложений, использующих источники данных Oracle.|  
  
## <a name="entityclient-provider"></a>EntityClient - поставщик  
 Поставщик EntityClient используется для доступа к данным на основе модели EDM (Entity Data Model). В отличие от других поставщиков данных .NET этот поставщик не взаимодействует с источником данных непосредственно. Вместо этого для взаимодействия с соответствующим поставщиком данных используется язык Entity SQL. Дополнительные сведения см. в разделе [поставщик EntityClient для Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
