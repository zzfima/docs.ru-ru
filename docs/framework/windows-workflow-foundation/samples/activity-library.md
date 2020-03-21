---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142905"
---
# <a name="activity-library"></a>Библиотека действий
Этот раздел содержит образцы, демонстрирующие передовые пользовательские действия в Фонде рабочего процесса Windows (WF).  
  
## <a name="in-this-section"></a>в этом разделе

 [Настраиваемое действие SendMail](sendmail-custom-activity.md)  
 В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Параллельное действие ForEach с ограничением](throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.
  
 [Действия доступа к базе данных](database-access-activities.md)  
 Демонстрирует, как создавать действия, позволяющие получить доступ к базам данных для получения или изменения информации и использования [ADO.NET](../../data/adonet/index.md) для доступа к базе данных.  
  
 [Реализованное действие политики в .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как деятельность ExternalizedPolicy4 позволяет выполнять существующие объекты Windows Workflow Foundation в .NET <xref:System.Workflow.Activities.Rules.RuleSet> Framework 3.5 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 3.5) в Фонде рабочего процесса Windows в (WF 4.5) непосредственно с помощью движка правил, поставляемого в WF 3.5.
  
 [Неуниверсальное действие ForEach](non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Неуниверсальное действие ParallelForEach](non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение WorkflowInstanceId](get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.
