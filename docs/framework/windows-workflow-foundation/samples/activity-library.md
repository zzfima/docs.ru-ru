---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909185"
---
# <a name="activity-library"></a>Библиотека действий
Этот раздел содержит образцы, демонстрирующие дополнительные пользовательские действия в Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>В этом разделе

 [Настраиваемое действие SendMail](sendmail-custom-activity.md)  
 В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Параллельное действие ForEach с ограничением](throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.
  
 [Действия доступа к базе данных](database-access-activities.md)  
 Демонстрирует создание действия, которые позволяют получить доступ к базам данных, чтобы вернуть или изменить сведения, а также использовать [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.  
  
 [Реализованное действие политики в .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как действия externalizedpolicy4 можно выполнять существующие Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил это в комплект поставки WF 3.5. 
  
 [Неуниверсальное действие ForEach](non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Неуниверсальное действие ParallelForEach](non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение WorkflowInstanceId](get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.
