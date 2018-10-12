---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e8777d0068e6cca9c9324a6fd2668e6ff9e9da7
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123128"
---
# <a name="activity-library"></a>Библиотека действий
Этот раздел содержит образцы, демонстрирующие дополнительные пользовательские действия в Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>В этом разделе

 [Настраиваемое действие SendMail](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Параллельное действие ForEach с ограничением](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.
  
 [Действия доступа к базе данных](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 Демонстрирует создание действия, которые позволяют получить доступ к базам данных, чтобы вернуть или изменить сведения, а также использовать [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.  
  
 [Реализованное действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как действия externalizedpolicy4 можно выполнять существующие Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил это в комплект поставки WF 3.5. 
  
 [Неуниверсальное действие ForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Неуниверсальное действие ParallelForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение WorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.
