---
title: Хранилище экземпляров рабочих процессов SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 81f11b9f88fbe425a07e553e64a08761dca3a2b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517323"
---
# <a name="sql-workflow-instance-store"></a>Хранилище экземпляров рабочих процессов SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] поставляется вместе с хранилищем экземпляров рабочего процесса SQL, благодаря чему рабочие процессы могут сохранять сведения о состоянии экземпляров рабочих процессов в базах данных SQL Server 2005 или SQL Server 2008. Эта функция чаще всего реализуется в виде класса <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, являющегося производным от абстрактного класса <xref:System.Runtime.DurableInstancing.InstanceStore> платформы сохраняемости. Компонент хранилища экземпляров рабочего процесса SQL состоит из поставщика сохраняемости SQL, являющегося конкретной реализацией API сохраняемости, используемой ведущим приложением для отправки команд сохраняемости в хранилище.  
  
 Хранилище экземпляров рабочего процесса SQL поддерживает как самостоятельно размещаемые рабочие процессы, так и службы рабочих процессов, которые используют <xref:System.Activities.WorkflowApplication> или <xref:System.ServiceModel.WorkflowServiceHost>, а также службы, размещаемые в WAS с использованием <xref:System.ServiceModel.WorkflowServiceHost>. Компонент хранилища экземпляров рабочего процесса SQL можно настроить на работу с самостоятельно размещаемыми службами программным образом, воспользовавшись предоставляемой компонентом объектной моделью. Настроить эту функцию для служб, размещенных в <xref:System.ServiceModel.WorkflowServiceHost>, можно как программным образом с использованием объектной модели, так и с использованием файла конфигурации XML.  
  
 Компонент хранилища экземпляров рабочего процесса SQL (**SqlWorkflowInstanceStore** класс) не реализует <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> и поэтому не обеспечивает поддержку сохраняемости для устойчивых служб WCF не в рабочем процессе. Он также не реализует <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> и поэтому не обеспечивает поддержку сохраняемости для рабочих процессов версии 3.x. Этот компонент поддерживает сохраняемость только для рабочих процессов WF 4.0 (и более поздних версий) и служб Workflow Services. Компонент также не поддерживает базы данных, отличные от SQL Server 2005 и SQL Server 2008.  
  
 В подразделах этого раздела описываются свойства и функции хранилища экземпляров рабочего процесса SQL, а также предоставляются подробные сведения о настройке хранилища.  
  
 Фабрика приложений (App Fabric) Windows Server предоставляет собственное хранилище экземпляров и инструментарий для упрощения настройки и использования хранилища. Дополнительные сведения см. в разделе [Windows Server хранилище экземпляров](http://go.microsoft.com/fwlink/?LinkId=201201). Дополнительные сведения о базе данных SQL Server App Fabric сохраняемости см [базы данных SQL Server App Fabric сохраняемости](http://go.microsoft.com/fwlink/?LinkId=201202)  
  
## <a name="in-this-section"></a>В этом разделе  
  
-   [Свойства хранилища экземпляров рабочих процессов SQL](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [Практическое руководство. Включение сохраняемости для рабочих процессов и их служб в SQL](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Активация экземпляров](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [Поддержка запросов](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [Расширяемость хранилища](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [Безопасность](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [База данных сохраняемости SQL Server](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a>См. также  
 [Примеры сохраняемости](http://go.microsoft.com/fwlink/?LinkID=177735)
