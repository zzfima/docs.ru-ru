---
title: Хранилище экземпляров рабочих процессов SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 1764017369e82cfbed38be06b4a36847576b5fc0
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837640"
---
# <a name="sql-workflow-instance-store"></a>Хранилище экземпляров рабочих процессов SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] поставляется вместе с хранилищем экземпляров рабочего процесса SQL, благодаря чему рабочие процессы могут сохранять сведения о состоянии экземпляров рабочих процессов в базах данных SQL Server 2005 или SQL Server 2008. Эта функция чаще всего реализуется в виде класса <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, являющегося производным от абстрактного класса <xref:System.Runtime.DurableInstancing.InstanceStore> платформы сохраняемости. Компонент хранилища экземпляров рабочего процесса SQL состоит из поставщика сохраняемости SQL, являющегося конкретной реализацией API сохраняемости, используемой ведущим приложением для отправки команд сохраняемости в хранилище.  
  
 Хранилище экземпляров рабочего процесса SQL поддерживает как самостоятельно размещаемые рабочие процессы, так и службы рабочих процессов, которые используют <xref:System.Activities.WorkflowApplication> или <xref:System.ServiceModel.WorkflowServiceHost>, а также службы, размещаемые в WAS с использованием <xref:System.ServiceModel.WorkflowServiceHost>. Компонент хранилища экземпляров рабочего процесса SQL можно настроить на работу с самостоятельно размещаемыми службами программным образом, воспользовавшись предоставляемой компонентом объектной моделью. Настроить эту функцию для служб, размещенных в <xref:System.ServiceModel.WorkflowServiceHost>, можно как программным образом с использованием объектной модели, так и с использованием файла конфигурации XML.  
  
 Функция хранилища экземпляров рабочих процессов SQL (класс**SqlWorkflowInstanceStore** ) не реализует <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> и поэтому не поддерживает сохраняемость для устойчивых служб WCF, не являющихся рабочими процессами. Он также не реализует <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> и поэтому не обеспечивает поддержку сохраняемости для рабочих процессов версии 3.x. Этот компонент поддерживает сохраняемость только для рабочих процессов WF 4.0 (и более поздних версий) и служб Workflow Services. Компонент также не поддерживает базы данных, отличные от SQL Server 2005 и SQL Server 2008.  
  
 В подразделах этого раздела описываются свойства и возможности хранилища экземпляров рабочего процесса SQL, а также предоставляются подробные сведения о настройке хранилища.  
  
 Фабрика приложений (App Fabric) Windows Server предоставляет собственное хранилище экземпляров и инструментарий для упрощения настройки и использования хранилища. Дополнительные сведения см. в статье [хранилище экземпляров Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)). Дополнительные сведения о структуре приложений SQL Server базы данных сохраняемости см. в статье [app fabric SQL Server сохраняемость базы данных](https://docs.microsoft.com/previous-versions/appfabric/ee790819(v=azure.10)) .  
  
## <a name="in-this-section"></a>Содержание  
  
- [Свойства хранилища экземпляров рабочих процессов SQL](properties-of-sql-workflow-instance-store.md)  
  
- [Практическое руководство. Включение сохраняемости для рабочих процессов и их служб в SQL](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
- [Активация экземпляров](instance-activation.md)  
  
- [Поддержка запросов](support-for-queries.md)  
  
- [Расширяемость хранилища](store-extensibility.md)  
  
- [Security](security.md)  
  
- [База данных сохраняемости SQL Server](sql-server-persistence-database.md)  
  
## <a name="see-also"></a>См. также:

- [Примеры сохраняемости](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100))
