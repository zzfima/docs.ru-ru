---
title: Сохраняемость рабочего процесса
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2278762895978f90d80977f9e538b0e10a4f3f8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-persistence"></a>Сохраняемость рабочего процесса
Сохраняемость рабочего процесса - это постоянное отслеживание состояний экземпляра рабочего процесса независимо от выполняемого процесса или данных компьютера. Делается это для обеспечения хорошо известной точки восстановления для экземпляра рабочего процесса в случае сбоя системы или сохранения памяти путем выгрузки экземпляров рабочих процессов, которые в настоящий момент не выполняют активных действий, или переноса состояния экземпляра рабочего процесса с одного узла на другой узел в ферме серверов.  
  
 Сохраняемость обеспечивает гибкость, масштабируемость и восстановление процесса в случае сбоя, а также возможность более эффективного управления памятью. Процесс сохраняемости состоит из определения точки сохраняемости, сбора данных для сохранения и, наконец, делегирование фактического хранения данных поставщику сохраняемости.  
  
 Чтобы включить сохраняемость для рабочего процесса, необходимо связать хранилище экземпляров с **WorkflowApplication** или **WorkflowServiceHost** как упоминалось в [как: включить сохраняемость для Рабочие процессы и службы рабочих процессов](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md). **WorkflowApplication** и **WorkflowServiceHost** позволяет включить сохранения экземпляров рабочего процесса в хранилище сохраняемости и загрузки экземпляров рабочего процесса в хранилище экземпляров, связанных с ними объем памяти, на основе данных экземпляра рабочего процесса, хранящихся в хранилище сохраняемости.  
  
 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] Поставляется с **SqlWorkflowInstanceStore** класс, который обеспечивает сохраняемость данных и метаданных об экземплярах рабочих процессов в базу данных SQL Server 2005 или SQL Server 2008. В разделе [хранилище экземпляров рабочих процессов SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) для получения дополнительных сведений.  
  
 Для сохранения и загрузки данных приложения вместе со сведениями, относящимися к экземпляру рабочего процесса, можно создать участников сохраняемости, расширяющих класс <xref:System.Activities.Persistence.PersistenceParticipant>. Участник сохраняемости принимает участие в процессе сохраняемости и сохраняет пользовательские сериализуемые данные в хранилище сохраняемости, загружает данные из хранилища экземпляров в память и выполняет любую дополнительную логику в транзакции сохраняемости. Дополнительные сведения см. в разделе [участников сохраняемости](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).  
  
 Windows Server App Fabric упрощает процесс настройки сохраняемости. Дополнительные сведения см. в разделе [основные понятия сохраняемости с Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## <a name="implicit-persistence-points"></a>Неявные точки сохранения  
 В следующем списке содержатся примеры условий, при которых рабочий процесс сохраняется, если хранилище экземпляров связано с рабочим процессом.  
  
-   Когда **TransactionScope** завершения действия или **TransactedReceiveScope** завершения действия.  
  
-   При освобождении экземпляра рабочего процесса и **WorkflowIdleBehavior** устанавливается на узел рабочего процесса. Это происходит, например, при использовании действий обмена сообщениями или **задержки** действия.  
  
-   Когда приложение становится неактивным и **PersistableIdle** приложения является свойство **PersistableIdleAction.Persist**.  
  
-   Когда ведущему приложению указано сохранить или выгрузить экземпляр рабочего процесса.  
  
-   При прерывании или завершении экземпляра рабочего процесса.  
  
-   Когда **Persist** выполняется действие.  
  
-   Когда экземпляр рабочего процесса, разработанный с помощью прежней версии Windows Workflow Foundation, встречает точку сохранения при выполнении взаимодействия.  
  
## <a name="in-this-section"></a>В этом разделе  
  
-   [Хранилище экземпляров рабочих процессов SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [Хранилища экземпляров](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [Участники сохраняемости](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [Рекомендации по сохраняемости](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [Несохраняемые экземпляры рабочих процессов](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [Приостановка и возобновление рабочего процесса](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
