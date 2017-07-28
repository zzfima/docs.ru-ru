---
title: "Включение уведомлений о запросах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Включение уведомлений о запросах
Приложения, в которых используются уведомления о запросах, имеют общий набор требований.  Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.  
  
 Чтобы использовать уведомления о запросах, необходимо:  
  
-   включить уведомления о запросах для используемой базы данных;  
  
-   убедиться, что идентификатор пользователя, используемый для подключения к базе данных, имеет необходимые права доступа;  
  
-   использовать объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>;  
  
-   предоставить код для обработки уведомления, если отслеживаемые данные изменяются.  
  
## Требования к уведомлениям о запросах  
 Уведомления о запросах поддерживаются только для инструкций SELECT, удовлетворяющих списку конкретных требований.  В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server, посвященные компоненту Service Broker и уведомлениям о запросах.  
  
 **Электронная документация по SQL Server**  
  
-   [Создание запроса для уведомлений](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [Факторы безопасности, которые следует учитывать при работе с компонентом Service Broker](http://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [Безопасность и защита \(компонент Service Broker\)](http://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [Вопросы безопасности служб Notification Services](http://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [Разрешения уведомления о запросе](http://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [Вопросы международного использования компонента Service Broker](http://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [Вопросы проектирования решений \(компонент Service Broker\)](http://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [Справочный центр разработчика для компонента Service Broker](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [Руководство разработчика \(компонент Service Broker\)](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## Включение уведомлений о запросах для запуска примеров кода  
 Чтобы включить компонент Service Broker для базы данных **AdventureWorks** с помощью среды SQL Server Management Studio, выполните следующую инструкцию Transact\-SQL:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Для правильной работы образцов уведомлений о запросах на сервере базы данных необходимо выполнить следующие инструкции Transact\-SQL.  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## Права доступа для уведомлений о запросах  
 Пользователи, которые выполняют команды, требующие уведомления, должны иметь на сервере право доступа к базе данных SUBSCRIBE QUERY NOTIFICATIONS.  
  
 Для кода на стороне клиента, который выполняется в условиях частичного уровня доверия, требуется право доступа <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 В следующем коде создается объект <xref:System.Data.SqlClient.SqlClientPermission> и состояние <xref:System.Security.Permissions.PermissionState> устанавливается в значение <xref:System.Security.Permissions.PermissionState>.  Метод <xref:System.Security.CodeAccessPermission.Demand%2A> вызовет исключение <xref:System.Security.SecurityException> во время выполнения, если всем вызывающим объектам, находящимся выше в стеке вызова, не предоставили этого права доступа.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## Выбор объекта уведомления  
 API\-интерфейс уведомлений о запросах предусматривает два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>.  В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>.  В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.  
  
### Использование объекта SqlDependency  
 Чтобы использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений.  Объекты компонента Service Broker, такие как очередь уведомлений, являются стандартными.  
  
 Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, представляя данные в виде аргументов событий.  Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных.  Это статический метод, который нужно вызывать только один раз во время инициализации приложения для каждого необходимого соединения с базой данных.  При завершении приложения для каждого установленного соединения зависимости следует вызвать метод `Stop`.  
  
### Использование SqlNotificationRequest  
 В отличие от этого, <xref:System.Data.Sql.SqlNotificationRequest> требует от программиста самостоятельно реализовывать всю инфраструктуру прослушивания.  Кроме того, должны быть определены все основные объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью.  Такой подход с реализацией вручную удобен, когда в приложении требуется использовать особые сообщения уведомлений или режимы уведомлений, либо если приложение является частью большего приложения компонента Service Broker.  
  
## См. также  
 [Уведомления о запросах в SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)