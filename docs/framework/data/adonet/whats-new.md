---
title: "Новые возможности ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
caps.latest.revision: 25
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 25
---
# Новые возможности ADO.NET
В [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] предоставляются следующие новые возможности.  
  
## Поставщик данных SqlClient  
 Ниже перечислены новые возможности поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
-   Ключевые слова строки подключения ConnectRetryCount и ConnectRetryInterval \(<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>\) позволяют управлять функцией устойчивости бездействующего соединения.  
  
-   Поддержка потоков из [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] в приложение поддерживает сценарии, в которых данные на сервере не структурированы.  Дополнительные сведения см. в разделе [Поддержка потоковой передачи SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md).  
  
-   Добавлена поддержка для асинхронного программирования.  Дополнительные сведения см. в разделе [Асинхронное программирование](../../../../docs/framework/data/adonet/asynchronous-programming.md).  
  
-   Ошибки соединения теперь будут отображаться в журнале расширенных событий.  Для получения дополнительной информации см. [Трассировка данных в ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).  
  
-   SqlClient теперь имеет поддержку высокого уровня доступности для [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], функции аварийного восстановления и AlwaysOn.  Для получения дополнительной информации см. [Поддержка SqlClient для высокого уровня доступности, аварийного восстановления](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
-   Пароли могут быть переданы как <xref:System.Security.SecureString> при использовании проверки подлинности [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  Дополнительные сведения см. в разделе <xref:System.Data.SqlClient.SqlCredential>.  
  
-   При `TrustServerCertificate`, равном false, и `Encrypt`, равном true, имя \(или IP\-адрес\) сервера из SSL\-сертификата [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] должно точно соответствовать имени \(или IP\-адресу\) сервера, указанному в строке подключения.  В противном случае соединение не будет установлено.  Дополнительные сведения см. в описании параметра соединения `Encrypt` в <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
     Если это изменение приведет к тому, что в существующем приложении подключение больше не будет устанавливаться, можно внести исправления в приложение с помощью одного из следующих способов.  
  
    -   Выпустить сертификат, в котором определяется краткое имя в поле общего имени \(CN\) или в поле альтернативного имени субъекта \(SAN\).  Это решение применимо для зеркального отображения базы данных.  
  
    -   Добавить псевдоним, отображающий краткое имя на полное имя домена.  
  
    -   Использовать полное имя домена в строке подключения.  
  
-   SqlClient поддерживает расширенную защиту.  Дополнительные сведения о расширенной защите см. в разделе [Подключение к компоненту Database Engine с помощью расширенной защиты](http://go.microsoft.com/fwlink/?LinkId=219978).  
  
-   SqlClient поддерживает соединения с базами данных LocalDB.  Для получения дополнительной информации см. [Поддержка SqlClient LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).  
  
-   `Type System Version=SQL Server 2012;` \- это новое значение, которое должно быть передано в свойство соединения `Type System Version`.  Значение `Type System Version=Latest;` теперь устарело и заменено эквивалентным `Type System Version=SQL Server 2008;`.  Для получения дополнительной информации см. <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
-   SqlClient обеспечивает дополнительную поддержку разреженных столбцов \- средство, которое было добавлено в SQL Server 2008.  Если приложение уже имеет доступ к данным в таблице, в которой используется поддержка разреженных столбцов, должно быть обнаружено повышение производительности.  Столбец IsColumnSet в <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> указывает, является ли столбец разреженным столбцом, который является элементом набора столбцов.  <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> указывает, является ли столбец разреженным \(дополнительные сведения см. в разделе [Коллекции схем SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)\).  Дополнительные сведения о разреженных столбцах см. в статье [Использование разреженных столбцов](http://go.microsoft.com/fwlink/?LinkId=224244).  
  
-   Сборка Microsoft.SqlServer.Types.dll, содержащая типы пространственных данных, была обновлена с переходом от версии 10.0 к версии 11.0.  Работа приложений, которые ссылаются на эту сборку, может оканчиваться сбоем.  Дополнительные сведения см. в статье [Критические изменения в функциях компонента Database Engine](http://go.microsoft.com/fwlink/?LinkId=224367).  
  
## ADO.NET Entity Framework  
 В [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] добавлены новые интерфейсы API, которые позволяют реализовывать новые сценарии при работе с бета\-версией платформы Entity Framework 5.0.  Дополнительные сведения об улучшениях и возможностях, которые были добавлены в платформу Entity Framework 5.0 см. в следующих разделах: [Новые возможности](http://go.microsoft.com/fwlink/?LinkID=251106) и [Выпуски и управление версиями платформы Entity Framework](http://go.microsoft.com/fwlink/?LinkId=234899).  
  
## См. также  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)   
 [Общие сведения об ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)   
 [What's New in WCF Data Services](http://msdn.microsoft.com/ru-ru/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)