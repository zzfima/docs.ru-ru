---
title: "Хранилище экземпляров рабочих процессов SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Хранилище экземпляров рабочих процессов SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] поставляется вместе с хранилищем экземпляров рабочего процесса SQL, благодаря чему рабочие процессы могут сохранять сведения о состоянии экземпляров рабочих процессов в базах данных SQL Server 2005 или SQL Server 2008.Эта функция чаще всего реализуется в виде класса <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, являющегося производным от абстрактного класса <xref:System.Runtime.Persistence.InstanceStore> платформы сохраняемости.Компонент хранилища экземпляров рабочего процесса SQL состоит из поставщика сохраняемости SQL, являющегося конкретной реализацией API сохраняемости, используемой ведущим приложением для отправки команд сохраняемости в хранилище.  
  
 Хранилище экземпляров рабочего процесса SQL поддерживает как самостоятельно размещаемые рабочие процессы, так и службы рабочих процессов, которые используют <xref:System.Activities.WorkflowApplication> или <xref:System.ServiceModel.WorkflowServiceHost>, а также службы, размещаемые в WAS с использованием <xref:System.ServiceModel.WorkflowServiceHost>.Компонент хранилища экземпляров рабочего процесса SQL можно настроить на работу с самостоятельно размещаемыми службами программным образом, воспользовавшись предоставляемой компонентом объектной моделью.Настроить эту функцию для служб, размещенных в <xref:System.ServiceModel.WorkflowServiceHost>, можно как программным образом с использованием объектной модели, так и с использованием файла конфигурации XML.  
  
 Компонент хранилища экземпляров рабочего процесса SQL \(класс **SqlWorkflowInstanceStore**\) не реализует <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> и поэтому не обеспечивает поддержку сохраняемости для устойчивых служб WCF, не входящих в рабочий процесс.Он также не реализует <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> и поэтому не обеспечивает поддержку сохраняемости для рабочих процессов версии 3.x.Этот компонент поддерживает сохраняемость только для рабочих процессов WF 4.0 \(и более поздней версии\) и служб рабочих процессов.Компонент также не поддерживает базы данных, отличные от SQL Server 2005 и SQL Server 2008.  
  
 В подразделах этого раздела описываются свойства и функции хранилища экземпляров рабочего процесса SQL, а также предоставляются подробные сведения о настройке хранилища.  
  
 Фабрика приложений \(App Fabric\) Windows Server предоставляет собственное хранилище экземпляров и инструментарий для упрощения настройки и использования хранилища.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] см. раздел [Хранилище экземпляров Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201201).[!INCLUDE[crabout](../../../includes/crabout-md.md)] базе данных постоянного хранения SQL Server App Fabric см. в разделе [База данных постоянного хранения SQL Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201202)  
  
## В этом подразделе  
  
-   [Свойства хранилища экземпляров рабочего процесса SQL](../../../docs/framework/windows-workflow-foundation//properties-of-sql-workflow-instance-store.md)  
  
-   [Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов](../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Активация экземпляров](../../../docs/framework/windows-workflow-foundation//instance-activation.md)  
  
-   [Поддержка запросов](../../../docs/framework/windows-workflow-foundation//support-for-queries.md)  
  
-   [Расширяемость хранилища](../../../docs/framework/windows-workflow-foundation//store-extensibility.md)  
  
-   [Безопасность](../../../docs/framework/windows-workflow-foundation//security.md)  
  
-   [База данных постоянного хранения SQL Server](../../../docs/framework/windows-workflow-foundation//sql-server-persistence-database.md)  
  
## См. также  
 [Образцы сохраняемости](http://go.microsoft.com/fwlink/?LinkID=177735)