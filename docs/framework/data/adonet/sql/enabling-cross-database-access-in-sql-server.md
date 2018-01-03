---
title: "Организация межбазового доступа в SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 56de7da4c0883c9fe209a221c36457ef8b617a18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="f5497-102">Организация межбазового доступа в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5497-102">Enabling Cross-Database Access in SQL Server</span></span>
<span data-ttu-id="f5497-103">Межбазовые цепочки владения возникают, когда процедура в одной базе данных зависит от объектов в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-103">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="f5497-104">Межбазовая цепочка владения работает так же, как цепочка владения внутри единой базы данных, но для непрерывной цепочки владения необходимо, чтобы все владельцы объекта были сопоставлены с одной учетной записью входа.</span><span class="sxs-lookup"><span data-stu-id="f5497-104">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="f5497-105">Если одна учетная запись входа является владельцем исходного объекта в исходной базе данных и целевых объектов в целевых базах данных, то SQL Server не проверяет наличие разрешений в целевых объектах.</span><span class="sxs-lookup"><span data-stu-id="f5497-105">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="f5497-106">Отключено по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f5497-106">Off By Default</span></span>  
 <span data-ttu-id="f5497-107">Формирование межбазовых цепочек владения отключено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5497-107">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="f5497-108">Майкрософт рекомендует отключить межбазовые цепочки владения, так как с ними связаны следующие угрозы безопасности:</span><span class="sxs-lookup"><span data-stu-id="f5497-108">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
-   <span data-ttu-id="f5497-109">Владельцы баз данных и члены ролей базы данных `db_ddladmin` или `db_owners` могут создавать объекты, владельцами которых являются другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="f5497-109">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="f5497-110">Эти объекты потенциально могут обращаться к объектам в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-110">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="f5497-111">Это значит, что при включенных межбазовых цепочках владения этим пользователям необходимо полностью доверять при доступе к данным во всех базах данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-111">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
-   <span data-ttu-id="f5497-112">Пользователи с разрешением CREATE DATABASE могут создавать новые базы данных и присоединять существующие базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-112">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="f5497-113">Если межбазовые цепочки владения включены, то эти пользователи могут обращаться к объектам в других базах данных, в которых у них нет прав доступа, из вновь созданных или присоединенных баз данных, которые они создали.</span><span class="sxs-lookup"><span data-stu-id="f5497-113">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="f5497-114">Включение межбазовых цепочек владения</span><span class="sxs-lookup"><span data-stu-id="f5497-114">Enabling Cross-database Ownership Chaining</span></span>  
 <span data-ttu-id="f5497-115">Межбазовые цепочки владения нужно включать только в среде с привилегированными пользователями, имеющими полный уровень доверия.</span><span class="sxs-lookup"><span data-stu-id="f5497-115">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="f5497-116">Их можно настроить во время установки всех баз данных или выборочно для определенных баз данных с помощью команд [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `sp_configure` и `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="f5497-116">It can be configured during setup for all databases, or selectively for specific databases using the [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="f5497-117">Для выборочной настройки межбазовых цепочек владения служит хранимая процедура `sp_configure`, с помощью которой эти цепочки отключаются для сервера.</span><span class="sxs-lookup"><span data-stu-id="f5497-117">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="f5497-118">Затем с помощью команды ALTER DATABASE с параметром SET DB_CHAINING ON настраиваются межбазовые цепочки владения только в требуемых базах данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-118">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="f5497-119">В следующем примере включены межбазовые цепочки владения для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-119">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="f5497-120">В следующем примере включены межбазовые цепочки владения для конкретных баз данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-120">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="f5497-121">Динамический SQL</span><span class="sxs-lookup"><span data-stu-id="f5497-121">Dynamic SQL</span></span>  
 <span data-ttu-id="f5497-122">Межбазовые цепочки владения неприменимы в тех случаях, когда выполняются динамически созданные инструкции SQL, если только один и тот же пользователь не присутствует в обеих базах данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-122">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="f5497-123">Это можно обойти в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], создав хранимую процедуру для доступа к данным другой базы данных и подписав эту процедуру сертификатом, существующим в обеих базах данных.</span><span class="sxs-lookup"><span data-stu-id="f5497-123">You can work around this in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="f5497-124">Это предоставляет пользователям доступ к используемым процедурой ресурсам базы данных без предоставления им доступа к базе данных или разрешений на нее.</span><span class="sxs-lookup"><span data-stu-id="f5497-124">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="f5497-125">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="f5497-125">External Resources</span></span>  
 <span data-ttu-id="f5497-126">Дополнительные сведения см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="f5497-126">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="f5497-127">Ресурс</span><span class="sxs-lookup"><span data-stu-id="f5497-127">Resource</span></span>|<span data-ttu-id="f5497-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="f5497-128">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f5497-129">[Расширение олицетворения базы данных с помощью инструкции EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) и [параметр Cross DB Ownership Chaining](http://msdn.microsoft.com/library/ms188694.aspx) [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] электронной документации.</span><span class="sxs-lookup"><span data-stu-id="f5497-129">[Extending Database Impersonation by Using EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) and [Cross DB Ownership Chaining Option](http://msdn.microsoft.com/library/ms188694.aspx)[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>|<span data-ttu-id="f5497-130">Разделы описывают, как настроить межбазовые цепочки владения между базами данных для экземпляра [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5497-130">Topics describe how to configure cross-database ownership chaining for an instance of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5497-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f5497-131">See Also</span></span>  
 [<span data-ttu-id="f5497-132">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5497-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="f5497-133">Общие сведения о безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5497-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="f5497-134">Управление разрешениями с использованием хранимых процедур в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5497-134">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="f5497-135">Написание безопасного динамического кода SQL в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5497-135">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="f5497-136">Подписывание хранимых процедур в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5497-136">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="f5497-137">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5497-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
