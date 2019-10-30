---
title: Включение уведомлений запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 84048a3fba2b32b1ae745160e2b405c04b738c65
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040228"
---
# <a name="enabling-query-notifications"></a>Включение уведомлений запросов
Приложения, в которых используются уведомления о запросах, имеют общий набор требований. Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.  
  
 Чтобы использовать уведомления о запросах, необходимо:  
  
- включить уведомления о запросах для используемой базы данных;  
  
- убедиться, что идентификатор пользователя, используемый для подключения к базе данных, имеет необходимые права доступа;  
  
- использовать объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>;  
  
- предоставить код для обработки уведомления, если отслеживаемые данные изменяются.  
  
## <a name="query-notifications-requirements"></a>Требования к уведомлениям о запросах  
 Уведомления о запросах поддерживаются только для инструкций SELECT, удовлетворяющих списку конкретных требований. В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server, посвященные компоненту Service Broker и уведомлениям о запросах.  
  
 **Документация по SQL Server**  
  
- [Создание запроса для уведомления](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Вопросы безопасности для Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Безопасность и защита (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Вопросы безопасности для служб Notification Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Разрешения уведомления о запросах](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Вопросы международного использования для Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Рекомендации по проектированию решений (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [Информационный центр для разработчиков Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Руководством разработчика (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Включение уведомлений о запросах для запуска примеров кода  
 Чтобы включить Service Broker базы данных **AdventureWorks** с помощью SQL Server Management Studio, выполните следующую инструкцию TRANSACT-SQL:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Для правильной работы образцов уведомлений о запросах на сервере базы данных необходимо выполнить следующие инструкции Transact-SQL.  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Права доступа для уведомлений о запросах  
 Пользователи, которые выполняют команды, требующие уведомления, должны иметь на сервере право доступа к базе данных SUBSCRIBE QUERY NOTIFICATIONS.  
  
 Для кода на стороне клиента, который выполняется в условиях частичного уровня доверия, требуется право доступа <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 В следующем коде создается объект <xref:System.Data.SqlClient.SqlClientPermission> и состояние <xref:System.Security.Permissions.PermissionState> устанавливается в значение <xref:System.Security.Permissions.PermissionState.Unrestricted>. Метод <xref:System.Security.CodeAccessPermission.Demand%2A> вызовет исключение <xref:System.Security.SecurityException> во время выполнения, если всем вызывающим объектам, находящимся выше в стеке вызова, не предоставили этого права доступа.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Выбор объекта уведомления  
 API-интерфейс уведомлений о запросах предусматривает два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>. В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>. В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.  
  
### <a name="using-sqldependency"></a>Использование объекта SqlDependency  
 Чтобы использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений. Объекты компонента Service Broker, такие как очередь уведомлений, являются стандартными.  
  
 Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, представляя данные в виде аргументов событий. Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных. Это статический метод, который нужно вызывать только один раз во время инициализации приложения для каждого необходимого соединения с базой данных. При завершении приложения для каждого установленного соединения зависимости следует вызвать метод `Stop`.  
  
### <a name="using-sqlnotificationrequest"></a>Использование SqlNotificationRequest  
 В отличие от этого, <xref:System.Data.Sql.SqlNotificationRequest> требует от программиста самостоятельно реализовывать всю инфраструктуру прослушивания. Кроме того, должны быть определены все основные объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью. Такой подход с реализацией вручную удобен, когда в приложении требуется использовать особые сообщения уведомлений или режимы уведомлений, либо если приложение является частью большего приложения компонента Service Broker.  
  
## <a name="see-also"></a>См. также

- [Уведомления запросов в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
