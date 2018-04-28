---
title: Хранилище экземпляров рабочих процессов SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11e61e1d702572af10cf4e46b9d1b284022fa56e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="sql-workflow-instance-store"></a><span data-ttu-id="82894-102">Хранилище экземпляров рабочих процессов SQL</span><span class="sxs-lookup"><span data-stu-id="82894-102">SQL Workflow Instance Store</span></span>
<span data-ttu-id="82894-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] поставляется вместе с хранилищем экземпляров рабочего процесса SQL, благодаря чему рабочие процессы могут сохранять сведения о состоянии экземпляров рабочих процессов в базах данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="82894-103">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ships with the SQL Workflow Instance Store, which allows workflows to persist state information about workflow instances in a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="82894-104">Эта функция чаще всего реализуется в виде класса <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, являющегося производным от абстрактного класса <xref:System.Runtime.DurableInstancing.InstanceStore> платформы сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="82894-104">This feature is primarily implemented in the form of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class, which derives from the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class of the persistence framework.</span></span> <span data-ttu-id="82894-105">Компонент хранилища экземпляров рабочего процесса SQL состоит из поставщика сохраняемости SQL, являющегося конкретной реализацией API сохраняемости, используемой ведущим приложением для отправки команд сохраняемости в хранилище.</span><span class="sxs-lookup"><span data-stu-id="82894-105">The SQL Workflow Instance Store feature constitutes a SQL persistence provider, which is a concrete implementation of the persistence API that a host uses to send persistence commands to the store.</span></span>  
  
 <span data-ttu-id="82894-106">Хранилище экземпляров рабочего процесса SQL поддерживает как самостоятельно размещаемые рабочие процессы, так и службы рабочих процессов, которые используют <xref:System.Activities.WorkflowApplication> или <xref:System.ServiceModel.WorkflowServiceHost>, а также службы, размещаемые в WAS с использованием <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="82894-106">The SQL Workflow Instance Store supports both self-hosted workflows or workflow services that use <xref:System.Activities.WorkflowApplication> or <xref:System.ServiceModel.WorkflowServiceHost> as well as services hosted in WAS using <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="82894-107">Компонент хранилища экземпляров рабочего процесса SQL можно настроить на работу с самостоятельно размещаемыми службами программным образом, воспользовавшись предоставляемой компонентом объектной моделью.</span><span class="sxs-lookup"><span data-stu-id="82894-107">You can configure the SQL Workflow Instance Store feature for self-hosted services programmatically by using the object model exposed by the feature.</span></span> <span data-ttu-id="82894-108">Настроить эту функцию для служб, размещенных в <xref:System.ServiceModel.WorkflowServiceHost>, можно как программным образом с использованием объектной модели, так и с использованием файла конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="82894-108">You can configure this feature for services hosted by <xref:System.ServiceModel.WorkflowServiceHost> both programmatically by using the object model and also by using an XML configuration file.</span></span>  
  
 <span data-ttu-id="82894-109">Компонент хранилища экземпляров рабочего процесса SQL (**SqlWorkflowInstanceStore** класс) не реализует <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> и поэтому не обеспечивает поддержку сохраняемости для устойчивых служб WCF не в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="82894-109">The SQL Workflow Instance Store feature (**SqlWorkflowInstanceStore** class) does not implement <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> and hence does not offer persistence support for durable non-workflow WCF services.</span></span> <span data-ttu-id="82894-110">Он также не реализует <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> и поэтому не обеспечивает поддержку сохраняемости для рабочих процессов версии 3.x.</span><span class="sxs-lookup"><span data-stu-id="82894-110">It also does not implement <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> and hence does not offer persistence support for 3.x workflows.</span></span> <span data-ttu-id="82894-111">Этот компонент поддерживает сохраняемость только для рабочих процессов WF 4.0 (и более поздних версий) и служб Workflow Services.</span><span class="sxs-lookup"><span data-stu-id="82894-111">The feature supports persistence for only WF 4.0 (and later) workflows and workflow services.</span></span> <span data-ttu-id="82894-112">Компонент также не поддерживает базы данных, отличные от SQL Server 2005 и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="82894-112">The feature also does not support any databases other than SQL Server 2005 and SQL Server 2008.</span></span>  
  
 <span data-ttu-id="82894-113">В подразделах этого раздела описываются свойства и функции хранилища экземпляров рабочего процесса SQL, а также предоставляются подробные сведения о настройке хранилища.</span><span class="sxs-lookup"><span data-stu-id="82894-113">The topics in this section describe properties and features of the SQL Workflow Instance Store and provide you with details on configuring the store.</span></span>  
  
 <span data-ttu-id="82894-114">Фабрика приложений (App Fabric) Windows Server предоставляет собственное хранилище экземпляров и инструментарий для упрощения настройки и использования хранилища.</span><span class="sxs-lookup"><span data-stu-id="82894-114">Windows Server App Fabric provides its own instance store and tooling to simplify the configuration and use of the instance store.</span></span> <span data-ttu-id="82894-115">Дополнительные сведения см. в разделе [Windows Server хранилище экземпляров](http://go.microsoft.com/fwlink/?LinkId=201201).</span><span class="sxs-lookup"><span data-stu-id="82894-115">For more information, see see [Windows Server App Fabric Instance Store](http://go.microsoft.com/fwlink/?LinkId=201201).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="82894-116"> в разделе базы данных SQL Server App Fabric сохраняемости [базы данных SQL Server App Fabric сохраняемости](http://go.microsoft.com/fwlink/?LinkId=201202)</span><span class="sxs-lookup"><span data-stu-id="82894-116"> the App Fabric SQL Server Persistence Database see [App Fabric SQL Server Persistence Database](http://go.microsoft.com/fwlink/?LinkId=201202)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82894-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="82894-117">In This Section</span></span>  
  
-   [<span data-ttu-id="82894-118">Свойства хранилища экземпляров рабочих процессов SQL</span><span class="sxs-lookup"><span data-stu-id="82894-118">Properties of SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="82894-119">Практическое руководство. Включение сохраняемости для рабочих процессов и их служб в SQL</span><span class="sxs-lookup"><span data-stu-id="82894-119">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [<span data-ttu-id="82894-120">Активация экземпляров</span><span class="sxs-lookup"><span data-stu-id="82894-120">Instance Activation</span></span>](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [<span data-ttu-id="82894-121">Поддержка запросов</span><span class="sxs-lookup"><span data-stu-id="82894-121">Support for Queries</span></span>](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [<span data-ttu-id="82894-122">Расширяемость хранилища</span><span class="sxs-lookup"><span data-stu-id="82894-122">Store Extensibility</span></span>](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [<span data-ttu-id="82894-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="82894-123">Security</span></span>](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [<span data-ttu-id="82894-124">База данных сохраняемости SQL Server</span><span class="sxs-lookup"><span data-stu-id="82894-124">SQL Server Persistence Database</span></span>](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="82894-125">См. также</span><span class="sxs-lookup"><span data-stu-id="82894-125">See Also</span></span>  
 [<span data-ttu-id="82894-126">Примеры сохраняемости</span><span class="sxs-lookup"><span data-stu-id="82894-126">Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkID=177735)
