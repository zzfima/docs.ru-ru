---
title: Новые возможности в ADO.NET
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: 90352d3e3d52430d515460cdcc9b6d177976c0b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191466"
---
# <a name="whats-new-in-adonet"></a>Новые возможности в ADO.NET
В [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] предоставляются следующие новые возможности.  
  
## <a name="sqlclient-data-provider"></a>Поставщик данных SqlClient  
 Следующие функции добавлены в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщик данных для SQL Server в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:  
  
-   Ключевые слова строки подключения ConnectRetryCount и ConnectRetryInterval (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) позволяют управлять возможностью устойчивости бездействующего соединения.  
  
-   Поддержка потоков из SQL Server в приложение поддерживает сценарии, где неструктурированные данные на сервере.  См. в разделе [поддержка потоковой передачи SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md) Дополнительные сведения.  
  
-   Добавлена поддержка для асинхронного программирования.  См. в разделе [асинхронное программирование](../../../../docs/framework/data/adonet/asynchronous-programming.md) Дополнительные сведения.  
  
-   Ошибки соединения теперь будут отображаться в журнале расширенных событий. Дополнительные сведения см. в разделе [Трассировка данных в ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).  
  
-   SqlClient теперь имеет поддержку для SQL Server высокой доступности, аварийного восстановления, AlwaysOn. Дополнительные сведения см. в разделе [поддержка SqlClient для высокого уровня доступности и аварийного восстановления](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
-   Пароль может быть передан как <xref:System.Security.SecureString> при использовании проверки подлинности SQL Server. Дополнительные сведения см. в разделе <xref:System.Data.SqlClient.SqlCredential>.  
  
-   Когда `TrustServerCertificate` имеет значение false и `Encrypt` имеет значение true, имя сервера (или IP-адрес) в SQL Server SSL-сертификата должно совпадать сервера имя (или IP-адрес) указан в строке подключения. В противном случае соединение не будет установлено. Дополнительные сведения см. в описании параметра соединения `Encrypt` в <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
     Если это изменение приведет к тому, что в существующем приложении подключение больше не будет устанавливаться, можно внести исправления в приложение с помощью одного из следующих способов.  
  
    -   Выпустить сертификат, в котором определяется краткое имя в поле общего имени (CN) или в поле альтернативного имени субъекта (SAN). Это решение применимо для зеркального отображения базы данных.  
  
    -   Добавить псевдоним, отображающий краткое имя на полное имя домена.  
  
    -   Использовать полное имя домена в строке подключения.  
  
-   SqlClient поддерживает расширенную защиту. Дополнительные сведения о расширенной защите см. в разделе [подключение к Database Engine с помощью расширенной защиты](https://go.microsoft.com/fwlink/?LinkId=219978).  
  
-   SqlClient поддерживает соединения с базами данных LocalDB. Дополнительные сведения см. в разделе [поддержка SqlClient для LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).  
  
-   `Type System Version=SQL Server 2012;` - это новое значение, которое должно быть передано в свойство соединения `Type System Version`. Значение `Type System Version=Latest;` теперь устарело и заменено эквивалентным `Type System Version=SQL Server 2008;`. Дополнительные сведения см. в разделе <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
-   SqlClient обеспечивает дополнительную поддержку разреженных столбцов - средство, которое было добавлено в SQL Server 2008. Если приложение уже имеет доступ к данным в таблице, в которой используется поддержка разреженных столбцов, должно быть обнаружено повышение производительности. Столбец IsColumnSet в <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> указывает, является ли столбец разреженным столбцом, который является элементом набора столбцов. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Указывает, является ли столбец разреженным (см. в разделе [коллекции схемы SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md) Дополнительные сведения). Дополнительные сведения о разреженных столбцах см. в разделе [Использование разреженных столбцов](https://go.microsoft.com/fwlink/?LinkId=224244).  
  
-   Сборка Microsoft.SqlServer.Types.dll, содержащая типы пространственных данных, была обновлена с переходом от версии 10.0 к версии 11.0. Работа приложений, которые ссылаются на эту сборку, может оканчиваться сбоем. Дополнительные сведения см. в разделе [критические изменения в функциях ядра СУБД](https://go.microsoft.com/fwlink/?LinkId=224367).  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 В [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] добавлены новые интерфейсы API, которые позволяют реализовывать новые сценарии при работе с бета-версией платформы Entity Framework 5.0. Дополнительные сведения об улучшениях и функциях, добавленных в Entity Framework 5.0 см. в разделах: [Новые возможности](https://go.microsoft.com/fwlink/?LinkID=251106) и [Entity Framework выпуски и управление версиями](https://go.microsoft.com/fwlink/?LinkId=234899).  
  
## <a name="see-also"></a>См. также

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Общие сведения об ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)
- [Новые возможности в службах WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
