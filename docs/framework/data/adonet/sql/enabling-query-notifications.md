---
title: "Включение уведомлений запросов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c7b02ba7959a5cfc2205222655460026847c3098
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="8278d-102">Включение уведомлений запросов</span><span class="sxs-lookup"><span data-stu-id="8278d-102">Enabling Query Notifications</span></span>
<span data-ttu-id="8278d-103">Приложения, в которых используются уведомления о запросах, имеют общий набор требований.</span><span class="sxs-lookup"><span data-stu-id="8278d-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="8278d-104">Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="8278d-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="8278d-105">Чтобы использовать уведомления о запросах, необходимо:</span><span class="sxs-lookup"><span data-stu-id="8278d-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="8278d-106">включить уведомления о запросах для используемой базы данных;</span><span class="sxs-lookup"><span data-stu-id="8278d-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="8278d-107">убедиться, что идентификатор пользователя, используемый для подключения к базе данных, имеет необходимые права доступа;</span><span class="sxs-lookup"><span data-stu-id="8278d-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="8278d-108">использовать объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>;</span><span class="sxs-lookup"><span data-stu-id="8278d-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="8278d-109">предоставить код для обработки уведомления, если отслеживаемые данные изменяются.</span><span class="sxs-lookup"><span data-stu-id="8278d-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="8278d-110">Требования к уведомлениям о запросах</span><span class="sxs-lookup"><span data-stu-id="8278d-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="8278d-111">Уведомления о запросах поддерживаются только для инструкций SELECT, удовлетворяющих списку конкретных требований.</span><span class="sxs-lookup"><span data-stu-id="8278d-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="8278d-112">В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server, посвященные компоненту Service Broker и уведомлениям о запросах.</span><span class="sxs-lookup"><span data-stu-id="8278d-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="8278d-113">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8278d-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="8278d-114">Создание запроса для уведомлений</span><span class="sxs-lookup"><span data-stu-id="8278d-114">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="8278d-115">Рекомендации по безопасности для компонента Service Broker</span><span class="sxs-lookup"><span data-stu-id="8278d-115">Security Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="8278d-116">Безопасность и защита (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="8278d-116">Security and Protection (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="8278d-117">Вопросы безопасности для служб уведомления</span><span class="sxs-lookup"><span data-stu-id="8278d-117">Security Considerations for Notifications Services</span></span>](http://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="8278d-118">Разрешения уведомления о запросе</span><span class="sxs-lookup"><span data-stu-id="8278d-118">Query Notification Permissions</span></span>](http://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="8278d-119">Вопросы международного использования компонента Service Broker</span><span class="sxs-lookup"><span data-stu-id="8278d-119">International Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="8278d-120">Вопросы проектирования решений (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="8278d-120">Solution Design Considerations (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="8278d-121">Справочный центр разработчика Service Broker</span><span class="sxs-lookup"><span data-stu-id="8278d-121">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="8278d-122">Руководство разработчика (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="8278d-122">Developer's Guide (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="8278d-123">Включение уведомлений о запросах для запуска примеров кода</span><span class="sxs-lookup"><span data-stu-id="8278d-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="8278d-124">Чтобы включить компонент Service Broker на **AdventureWorks** баз данных с помощью SQL Server Management Studio, выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="8278d-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="8278d-125">Для правильной работы образцов уведомлений о запросах на сервере базы данных необходимо выполнить следующие инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8278d-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="8278d-126">Права доступа для уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="8278d-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="8278d-127">Пользователи, которые выполняют команды, требующие уведомления, должны иметь на сервере право доступа к базе данных SUBSCRIBE QUERY NOTIFICATIONS.</span><span class="sxs-lookup"><span data-stu-id="8278d-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="8278d-128">Для кода на стороне клиента, который выполняется в условиях частичного уровня доверия, требуется право доступа <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="8278d-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="8278d-129">В следующем коде создается объект <xref:System.Data.SqlClient.SqlClientPermission> и состояние <xref:System.Security.Permissions.PermissionState> устанавливается в значение <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="8278d-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="8278d-130">Метод <xref:System.Security.CodeAccessPermission.Demand%2A> вызовет исключение <xref:System.Security.SecurityException> во время выполнения, если всем вызывающим объектам, находящимся выше в стеке вызова, не предоставили этого права доступа.</span><span class="sxs-lookup"><span data-stu-id="8278d-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="8278d-131">Выбор объекта уведомления</span><span class="sxs-lookup"><span data-stu-id="8278d-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="8278d-132">API-интерфейс уведомлений о запросах предусматривает два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="8278d-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="8278d-133">В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="8278d-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="8278d-134">В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.</span><span class="sxs-lookup"><span data-stu-id="8278d-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="8278d-135">Использование объекта SqlDependency</span><span class="sxs-lookup"><span data-stu-id="8278d-135">Using SqlDependency</span></span>  
 <span data-ttu-id="8278d-136">Чтобы использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений.</span><span class="sxs-lookup"><span data-stu-id="8278d-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="8278d-137">Объекты компонента Service Broker, такие как очередь уведомлений, являются стандартными.</span><span class="sxs-lookup"><span data-stu-id="8278d-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="8278d-138">Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, представляя данные в виде аргументов событий.</span><span class="sxs-lookup"><span data-stu-id="8278d-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="8278d-139">Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных.</span><span class="sxs-lookup"><span data-stu-id="8278d-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="8278d-140">Это статический метод, который нужно вызывать только один раз во время инициализации приложения для каждого необходимого соединения с базой данных.</span><span class="sxs-lookup"><span data-stu-id="8278d-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="8278d-141">При завершении приложения для каждого установленного соединения зависимости следует вызвать метод `Stop`.</span><span class="sxs-lookup"><span data-stu-id="8278d-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="8278d-142">Использование SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="8278d-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="8278d-143">В отличие от этого, <xref:System.Data.Sql.SqlNotificationRequest> требует от программиста самостоятельно реализовывать всю инфраструктуру прослушивания.</span><span class="sxs-lookup"><span data-stu-id="8278d-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="8278d-144">Кроме того, должны быть определены все основные объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью.</span><span class="sxs-lookup"><span data-stu-id="8278d-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="8278d-145">Такой подход с реализацией вручную удобен, когда в приложении требуется использовать особые сообщения уведомлений или режимы уведомлений, либо если приложение является частью большего приложения компонента Service Broker.</span><span class="sxs-lookup"><span data-stu-id="8278d-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8278d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="8278d-146">See Also</span></span>  
 [<span data-ttu-id="8278d-147">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="8278d-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="8278d-148">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8278d-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
