---
title: "Уведомления запросов в SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d922598cb31e60b1c1648884555695c1ba089726
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="97faa-102">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="97faa-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="97faa-103">С помощью уведомлений о запросах на основе инфраструктуры компонента Service Broker приложения могут получать извещения об изменениях данных.</span><span class="sxs-lookup"><span data-stu-id="97faa-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="97faa-104">Эта функция особенно полезна для приложений, которые предоставляют кэш данных из базы данных (например, для веб-приложений), и которым требуются уведомления об изменении исходных данных.</span><span class="sxs-lookup"><span data-stu-id="97faa-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="97faa-105">Существует три способа реализации уведомлений о запросах с помощью ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="97faa-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="97faa-106">Низкоуровневую реализацию обеспечивает класс `SqlNotificationRequest`, который предоставляет функциональность на стороне сервера, позволяя выполнить команду с запросом на уведомления.</span><span class="sxs-lookup"><span data-stu-id="97faa-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="97faa-107">Высокоуровневая реализация обеспечивается классом `SqlDependency`, который обеспечивает высокоуровневую абстракцию работы с уведомлениями между исходным приложением и SQL Server, позволяя определять изменения на сервере с помощью зависимости.</span><span class="sxs-lookup"><span data-stu-id="97faa-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="97faa-108">В большинстве случаев это самый простой и самый эффективный способ задействовать возможности уведомления SQL Server в управляемых клиентских приложениях с помощью поставщика данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97faa-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="97faa-109">Кроме того, в веб-приложениях, построенных с помощью ASP.NET 2.0 или более поздних версий, можно использовать вспомогательные классы `SqlCacheDependency`.</span><span class="sxs-lookup"><span data-stu-id="97faa-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="97faa-110">Уведомления о запросах используются в приложениях, в которых при изменении данных необходимо обновлять соответствующие данные на экране или в кэше.</span><span class="sxs-lookup"><span data-stu-id="97faa-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="97faa-111">Microsoft SQL Server позволяет приложениям .NET Framework передавать команды в SQL Server и запрашивать уведомления, если при выполнении одной и той же команды может получиться результирующий набор, отличный от полученного первоначально.</span><span class="sxs-lookup"><span data-stu-id="97faa-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="97faa-112">Уведомления, создаваемые на сервере, помещаются в очереди для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="97faa-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="97faa-113">Уведомления можно задать для инструкций SELECT и EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="97faa-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="97faa-114">При использовании инструкции EXECUTE сервер SQL Server регистрирует уведомление для выполняемой команды, а не самой инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="97faa-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="97faa-115">Команда должна соответствовать требованиям, предъявляемым к инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="97faa-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="97faa-116">Если команда, для которой регистрируется уведомление, состоит из нескольких инструкций, компонент Database Engine создает уведомления для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="97faa-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="97faa-117">Если вы разрабатываете приложение которых требуется надежный доли секунды уведомления об изменении данных, просмотрите разделы **планирование эффективной стратегии уведомлений о запросах** и **альтернативы для запросов Уведомления о** в [планирование уведомлений](http://go.microsoft.com/fwlink/?LinkId=211984) раздел электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97faa-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="97faa-118">Дополнительные сведения об уведомлениях о запросах и компоненте SQL Server Service Broker см. в указанных ниже разделах электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97faa-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="97faa-119">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="97faa-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="97faa-120">Использование уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="97faa-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="97faa-121">Создание запроса для уведомлений</span><span class="sxs-lookup"><span data-stu-id="97faa-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="97faa-122">Компонент Service Broker</span><span class="sxs-lookup"><span data-stu-id="97faa-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="97faa-123">Справочный центр разработчика Service Broker</span><span class="sxs-lookup"><span data-stu-id="97faa-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="97faa-124">Разработка (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="97faa-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="97faa-125">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="97faa-125">In This Section</span></span>  
 [<span data-ttu-id="97faa-126">Включение уведомлений запросов</span><span class="sxs-lookup"><span data-stu-id="97faa-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="97faa-127">Описывает использование уведомлений о запросах, в том числе требования к их включению и использованию.</span><span class="sxs-lookup"><span data-stu-id="97faa-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="97faa-128">SqlDependency в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="97faa-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="97faa-129">Демонстрирует использование уведомлений о запросах из приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="97faa-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="97faa-130">Обнаружение изменений с использованием SqlDependency</span><span class="sxs-lookup"><span data-stu-id="97faa-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="97faa-131">Демонстрирует, как определить, когда результаты запроса будут отличаться от полученных первоначально.</span><span class="sxs-lookup"><span data-stu-id="97faa-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="97faa-132">Выполнение SqlCommand с помощью SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="97faa-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="97faa-133">Демонстрирует настройку работы с уведомлениями о запросах в объекте <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="97faa-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="97faa-134">Ссылка</span><span class="sxs-lookup"><span data-stu-id="97faa-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="97faa-135">Описывает класс <xref:System.Data.Sql.SqlNotificationRequest> и все его члены.</span><span class="sxs-lookup"><span data-stu-id="97faa-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="97faa-136">Описывает класс <xref:System.Data.SqlClient.SqlDependency> и все его члены.</span><span class="sxs-lookup"><span data-stu-id="97faa-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="97faa-137">Описывает класс <xref:System.Web.Caching.SqlCacheDependency> и все его члены.</span><span class="sxs-lookup"><span data-stu-id="97faa-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97faa-138">См. также</span><span class="sxs-lookup"><span data-stu-id="97faa-138">See Also</span></span>  
 [<span data-ttu-id="97faa-139">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97faa-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="97faa-140">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97faa-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
