---
title: Включение уведомлений запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: a2227b33c7caacdd04c7bf50082bb0cfab7f3302
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113949"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="824a4-102">Включение уведомлений запросов</span><span class="sxs-lookup"><span data-stu-id="824a4-102">Enabling Query Notifications</span></span>
<span data-ttu-id="824a4-103">Приложения, в которых используются уведомления о запросах, имеют общий набор требований.</span><span class="sxs-lookup"><span data-stu-id="824a4-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="824a4-104">Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="824a4-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="824a4-105">Чтобы использовать уведомления о запросах, необходимо:</span><span class="sxs-lookup"><span data-stu-id="824a4-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="824a4-106">включить уведомления о запросах для используемой базы данных;</span><span class="sxs-lookup"><span data-stu-id="824a4-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="824a4-107">убедиться, что идентификатор пользователя, используемый для подключения к базе данных, имеет необходимые права доступа;</span><span class="sxs-lookup"><span data-stu-id="824a4-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="824a4-108">использовать объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>;</span><span class="sxs-lookup"><span data-stu-id="824a4-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="824a4-109">предоставить код для обработки уведомления, если отслеживаемые данные изменяются.</span><span class="sxs-lookup"><span data-stu-id="824a4-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="824a4-110">Требования к уведомлениям о запросах</span><span class="sxs-lookup"><span data-stu-id="824a4-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="824a4-111">Уведомления о запросах поддерживаются только для инструкций SELECT, удовлетворяющих списку конкретных требований.</span><span class="sxs-lookup"><span data-stu-id="824a4-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="824a4-112">В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server, посвященные компоненту Service Broker и уведомлениям о запросах.</span><span class="sxs-lookup"><span data-stu-id="824a4-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="824a4-113">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="824a4-113">**SQL Server documentation**</span></span>  
  
-   <span data-ttu-id="824a4-114">[Создание запроса для уведомлений](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-114">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
-   <span data-ttu-id="824a4-115">[Вопросы безопасности для компонента Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="824a4-115">[Security Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
-   <span data-ttu-id="824a4-116">[Безопасность и защита (компонент Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-116">[Security and Protection (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
-   <span data-ttu-id="824a4-117">[Вопросы безопасности для служб уведомления](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="824a4-117">[Security Considerations for Notifications Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
-   <span data-ttu-id="824a4-118">[Разрешения уведомления о запросе](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-118">[Query Notification Permissions](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
-   <span data-ttu-id="824a4-119">[Вопросы международного использования компонента Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="824a4-119">[International Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
-   <span data-ttu-id="824a4-120">[Вопросы проектирования решений (компонент Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-120">[Solution Design Considerations (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
-   <span data-ttu-id="824a4-121">[Справочный центр разработчика службы Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-121">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
-   <span data-ttu-id="824a4-122">[Руководство разработчика (компонент Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="824a4-122">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="824a4-123">Включение уведомлений о запросах для запуска примеров кода</span><span class="sxs-lookup"><span data-stu-id="824a4-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="824a4-124">Чтобы включить компонент Service Broker на **AdventureWorks** базы данных с помощью SQL Server Management Studio, выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="824a4-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="824a4-125">Для правильной работы образцов уведомлений о запросах на сервере базы данных необходимо выполнить следующие инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="824a4-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="824a4-126">Права доступа для уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="824a4-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="824a4-127">Пользователи, которые выполняют команды, требующие уведомления, должны иметь на сервере право доступа к базе данных SUBSCRIBE QUERY NOTIFICATIONS.</span><span class="sxs-lookup"><span data-stu-id="824a4-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="824a4-128">Для кода на стороне клиента, который выполняется в условиях частичного уровня доверия, требуется право доступа <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="824a4-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="824a4-129">В следующем коде создается объект <xref:System.Data.SqlClient.SqlClientPermission> и состояние <xref:System.Security.Permissions.PermissionState> устанавливается в значение <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="824a4-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="824a4-130">Метод <xref:System.Security.CodeAccessPermission.Demand%2A> вызовет исключение <xref:System.Security.SecurityException> во время выполнения, если всем вызывающим объектам, находящимся выше в стеке вызова, не предоставили этого права доступа.</span><span class="sxs-lookup"><span data-stu-id="824a4-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="824a4-131">Выбор объекта уведомления</span><span class="sxs-lookup"><span data-stu-id="824a4-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="824a4-132">API-интерфейс уведомлений о запросах предусматривает два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="824a4-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="824a4-133">В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="824a4-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="824a4-134">В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.</span><span class="sxs-lookup"><span data-stu-id="824a4-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="824a4-135">Использование объекта SqlDependency</span><span class="sxs-lookup"><span data-stu-id="824a4-135">Using SqlDependency</span></span>  
 <span data-ttu-id="824a4-136">Чтобы использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений.</span><span class="sxs-lookup"><span data-stu-id="824a4-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="824a4-137">Объекты компонента Service Broker, такие как очередь уведомлений, являются стандартными.</span><span class="sxs-lookup"><span data-stu-id="824a4-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="824a4-138">Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, представляя данные в виде аргументов событий.</span><span class="sxs-lookup"><span data-stu-id="824a4-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="824a4-139">Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных.</span><span class="sxs-lookup"><span data-stu-id="824a4-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="824a4-140">Это статический метод, который нужно вызывать только один раз во время инициализации приложения для каждого необходимого соединения с базой данных.</span><span class="sxs-lookup"><span data-stu-id="824a4-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="824a4-141">При завершении приложения для каждого установленного соединения зависимости следует вызвать метод `Stop`.</span><span class="sxs-lookup"><span data-stu-id="824a4-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="824a4-142">Использование SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="824a4-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="824a4-143">В отличие от этого, <xref:System.Data.Sql.SqlNotificationRequest> требует от программиста самостоятельно реализовывать всю инфраструктуру прослушивания.</span><span class="sxs-lookup"><span data-stu-id="824a4-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="824a4-144">Кроме того, должны быть определены все основные объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью.</span><span class="sxs-lookup"><span data-stu-id="824a4-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="824a4-145">Такой подход с реализацией вручную удобен, когда в приложении требуется использовать особые сообщения уведомлений или режимы уведомлений, либо если приложение является частью большего приложения компонента Service Broker.</span><span class="sxs-lookup"><span data-stu-id="824a4-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824a4-146">См. также</span><span class="sxs-lookup"><span data-stu-id="824a4-146">See also</span></span>

- [<span data-ttu-id="824a4-147">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="824a4-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="824a4-148">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="824a4-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
