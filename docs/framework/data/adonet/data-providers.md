---
title: Поставщики данных .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 2c986aab33f2c4dcefb5924ea61e8b9f6b3c50a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347814"
---
# <a name="net-framework-data-providers"></a>Поставщики данных .NET Framework
Поставщик данных .NET Framework используется для подключения к базе данных, исполнения команд и получения результатов. Эти результаты обрабатываются непосредственно, помещаются в <xref:System.Data.DataSet> , чтобы по мере необходимости они были доступны для пользователей вместе с данными из нескольких источников, либо распределяются между уровнями. .NET Framework поставщики данных являются облегченными, создавая минимальный уровень между источником данных и кодом, повышая производительность без ущерба для функциональности.  
  
 В следующей таблице перечислены поставщики данных, которые включены в .NET Framework.  
  
|Поставщик данных .NET Framework|Описание|  
|-------------------------------------------------------------------------------|-----------------|  
|Поставщик данных .NET Framework для SQL Server|Предоставляет доступ к данным для Microsoft SQL Server. Использует пространство имен <xref:System.Data.SqlClient> .|  
|Поставщик данных .NET Framework для OLE DB|Для источников данных OLE DB. Использует пространство имен <xref:System.Data.OleDb> .|  
|Поставщик данных .NET Framework для ODBC|Для источников данных ODBC. Использует пространство имен <xref:System.Data.Odbc> .|  
|Поставщик данных .NET Framework для Oracle|Для источников данных Oracle. Поставщик данных .NET Framework для Oracle поддерживает клиентское программное обеспечение Oracle версии 8.1.7 и более поздних версий и использует пространство имен <xref:System.Data.OracleClient>.|  
|EntityClient - поставщик|Предоставляет доступ к данным для приложений модели EDM (Entity Data Model). Использует пространство имен <xref:System.Data.EntityClient> .|  
|Поставщик данных .NET Framework для SQL Server Compact 4,0.|Предоставляет доступ к данным для Microsoft SQL Server Compact 4,0. Использует пространство имен [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Основные объекты поставщиков данных .NET Framework  
 В следующей таблице приведены четыре основных объекта, которые составляют поставщик данных .NET Framework.  
  
|Объект служб|Описание|  
|------------|-----------------|  
|`Connection`|Устанавливает соединение с конкретным источником данных. Базовым классом для всех объектов `Connection` является <xref:System.Data.Common.DbConnection> .|  
|`Command`|Выполняет команду в источнике данных. Обеспечивает доступность `Parameters` и может выполнять команды в области `Transaction` из `Connection`. Базовым классом для всех объектов `Command` является <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Считывает из источника данных однопроходный поток данных только для чтения. Базовым классом для всех объектов `DataReader` является <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Заполняет `DataSet` и выполняет обновления в источнике данных. Базовым классом для всех объектов `DataAdapter` является <xref:System.Data.Common.DbDataAdapter> .|  
  
 Помимо основных классов, перечисленных в таблице выше в этом документе, .NET Framework поставщик данных также содержит классы, перечисленные в следующей таблице.  
  
|Объект служб|Описание|  
|------------|-----------------|  
|`Transaction`|Прикрепляет команды к транзакциям в источнике данных. Базовым классом для всех объектов `Transaction` является <xref:System.Data.Common.DbTransaction> . ADO.NET также поддерживает транзакции, использующие классы в пространстве имен <xref:System.Transactions> .|  
|`CommandBuilder`|Объект помощника, автоматически формирующий свойства команд `DataAdapter` или извлекающий сведения о параметрах из хранимой процедуры и заполняющий коллекцию `Parameters` объекта `Command` . Базовым классом для всех объектов `CommandBuilder` является <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Объект помощника, обеспечивающий простой способ создания и управления содержимым строки соединения, которую используют объекты `Connection` . Базовым классом для всех объектов `ConnectionStringBuilder` является <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Определяет входные, выходные и возвращаемые значения параметров для команд и хранимых процедур. Базовым классом для всех объектов `Parameter` является <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Возвращается при возникновении ошибки в источнике данных. Для ошибки, возникшей на клиенте, .NET Framework поставщики данных вызывают исключение .NET Framework. Базовым классом для всех объектов `Exception` является <xref:System.Data.Common.DbException> .|  
|`Error`|Отображает сведения, относящиеся к предупреждениям и ошибкам, возвращенным источником данных.|  
|`ClientPermission`|Для .NET Framework атрибуты управления доступом к коду поставщика данных. Базовым классом для всех объектов `ClientPermission` является <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Поставщик данных .NET Framework для SQL Server (SqlClient)  
 Поставщик данных .NET Framework для SQL Server (SqlClient) использует собственный протокол для взаимодействия с SQL Server. Он является легковесным и хорошо работает, поскольку он оптимизирован для прямого доступа к SQL Server без добавления OLE DB или уровня ODBC. На следующем рисунке отличие .NET Framework поставщика данных для SQL Server с .NET Frameworkным поставщиком данных для OLE DB. Поставщик данных .NET Framework для OLE DB взаимодействует с OLE DBным источником данных через компонент службы OLE DB, который предоставляет службы пулов соединений и транзакций, а также поставщик OLE DB для источника данных.  
  
> [!NOTE]
> Поставщик данных .NET Framework для ODBC имеет схожую архитектуру с поставщиком данных .NET Framework для OLE DB; Например, он вызывает компонент службы ODBC.  
  
 ![Поставщики данных](./media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Сравнение поставщика данных .NET Framework для SQL Server и поставщика данных .NET Framework для OLE DB  
  
 Поставщик данных .NET Framework для SQL Server классов находится в пространстве имен <xref:System.Data.SqlClient>.  
  
 Поставщик данных .NET Framework для SQL Server поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций поставщик данных .NET Framework для SQL Server по умолчанию автоматически закрепляется в транзакции и получает сведения о транзакциях из служб компонентов Windows или <xref:System.Transactions>. Дополнительные сведения см. в разделе [Transactions and Concurrency](transactions-and-concurrency.md).  
  
 Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.SqlClient` .  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Поставщик данных .NET Framework для OLE DB  
 Поставщик данных .NET Framework для OLE DB (OleDb) использует собственные OLE DB через COM-взаимодействие для обеспечения доступа к данным. Поставщик данных .NET Framework для OLE DB поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций поставщик данных .NET Framework для OLE DB по умолчанию автоматически закрепляется в транзакции и получает сведения о транзакциях из служб компонентов Windows. Дополнительные сведения см. в разделе [Transactions and Concurrency](transactions-and-concurrency.md).  
  
 В следующей таблице показаны поставщики, которые были протестированы с помощью ADO.NET.  
  
|Драйвер|Поставщик|  
|------------|--------------|  
|SQLOLEDB|Поставщик OLE DB Майкрософт для SQL Server|  
|MSDAORA|Поставщик Microsoft OLE DB для Oracle|  
|Microsoft.Jet.OLEDB.4.0|Поставщик OLE DB для Microsoft Jet|  
  
> [!NOTE]
> Использовать базу данных Access (Jet) в качестве источника данных для многопоточных приложений, таких как приложения ASP.NET, не рекомендуется. Если необходимо использовать Jet в качестве источника данных для приложения ASP.NET, следует понимать, что приложения ASP.NET, подключающиеся к базе данных Access, могут столкнуться с проблемами подключения.  
  
 Поставщик данных .NET Framework для OLE DB не поддерживает интерфейсы OLE DB версии 2,5. Поставщики OLE DB, требующие поддержки интерфейсов OLE DB 2,5, не будут правильно работать с поставщиком данных .NET Framework для OLE DB. Это относится к поставщику OLE DB для Exchange (Майкрософт) и поставщику Microsoft OLE DB для публикаций в Интернете.  
  
 Поставщик данных .NET Framework для OLE DB не работает с поставщиком OLE DB для ODBC (MSDASQL). Чтобы получить доступ к источнику данных ODBC с помощью ADO.NET, используйте поставщик данных .NET Framework для ODBC.  
  
 Поставщик данных .NET Framework для OLE DB классов находится в пространстве имен <xref:System.Data.OleDb>. Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.OleDb` .  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Поставщик данных .NET Framework для ODBC  
 Поставщик данных .NET Framework для ODBC (ODBC) использует собственный диспетчер драйверов ODBC (DM) для обеспечения доступа к данным. Поставщик данных ODBC поддерживает как локальные, так и распределенные транзакции. Для распределенных транзакций поставщик данных ODBC по умолчанию автоматически задействуется в транзакции и получает сведения о транзакциях из служб компонентов Windows. Дополнительные сведения см. в разделе [Transactions and Concurrency](transactions-and-concurrency.md).  
  
 В следующей таблице приведены драйверы ODBC, протестированные с помощью ADO.NET.  
  
|Драйвер|  
|------------|  
|SQL Server|  
|Microsoft ODBC для Oracle|  
|Драйвер Microsoft Access (*.mdb)|  
  
 Поставщик данных .NET Framework для классов ODBC находится в пространстве имен <xref:System.Data.Odbc>.  
  
 Следующий пример кода показывает, как включать в приложения пространство имен `System.Data.Odbc` .  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
> Поставщик данных .NET Framework для ODBC требует наличия MDAC 2,6 или более поздней версии, и рекомендуется использовать MDAC 2,8 SP1. Загрузить MDAC 2,8 с пакетом обновления 1 (SP1) можно в [центре загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=5793).
  
## <a name="net-framework-data-provider-for-oracle"></a>Поставщик данных .NET Framework для Oracle  
 Поставщик данных .NET Framework для Oracle (OracleClient) обеспечивает доступ к источникам данных Oracle через клиентское по Oracle Software Connectivity. Поставщик данных поддерживает клиентское ПО Oracle версии 8.1.7 или более поздней версии. Поставщик данных поддерживает как локальные, так и распределенные транзакции. Дополнительные сведения см. в разделе [Transactions and Concurrency](transactions-and-concurrency.md).  
  
 Для работы поставщика данных .NET Framework для Oracle требуется клиентское программное обеспечение Oracle (версия 8.1.7 или более поздняя) в системе, прежде чем можно будет подключиться к источнику данных Oracle.  
  
 Поставщик данных .NET Framework для классов Oracle расположен в пространстве имен <xref:System.Data.OracleClient> и содержится в сборке `System.Data.OracleClient.dll`. При компиляции приложения, использующего этот источник данных, необходимо ссылаться как на `System.Data.dll` , так и на `System.Data.OracleClient.dll` .  
  
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
 В зависимости от структуры и источника данных для приложения выбранный поставщик данных .NET Framework может повысить производительность, возможности и целостность приложения. В следующей таблице описаны преимущества и ограничения каждого поставщика данных .NET Framework.  
  
|Поставщик|Примечания|  
|--------------|-----------|  
|Поставщик данных .NET Framework для SQL Server|Рекомендуется для приложений среднего уровня, использующих Microsoft SQL Server.<br /><br /> Рекомендуется для одноуровневых приложений, использующих Microsoft ядро СУБД (MSDE) или SQL Server.<br /><br /> Рекомендуется использовать поставщик OLE DB для SQL Server (SQLOLEDB) с .NET Frameworkным поставщиком данных для OLE DB.|  
|Поставщик данных .NET Framework для OLE DB|Для SQL Server рекомендуется использовать поставщик данных .NET Framework для SQL Server вместо этого поставщика.<br /><br /> Рекомендуется для одноуровневых приложений, использующих базы данных Microsoft Access. Базы данных Microsoft Access не рекомендуется использовать для приложений среднего уровня.|  
|Поставщик данных .NET Framework для ODBC|Рекомендуется для приложений среднего уровня и одноуровневых приложений, использующих источники данных ODBC.|  
|Поставщик данных .NET Framework для Oracle|Рекомендуется для приложений среднего уровня и одноуровневых приложений, использующих источники данных Oracle.|  
  
## <a name="entityclient-provider"></a>EntityClient - поставщик  
 Поставщик EntityClient используется для доступа к данным на основе модели EDM (Entity Data Model). В отличие от других поставщиков данных .NET этот поставщик не взаимодействует с источником данных непосредственно. Вместо этого для взаимодействия с соответствующим поставщиком данных используется язык Entity SQL. Дополнительные сведения см. [в разделе Поставщик EntityClient для Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об ADO.NET](ado-net-overview.md)
- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
