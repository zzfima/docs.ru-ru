---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 29b3efd648ac103526f572a2cac5b8b67c4b220a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078997"
---
# <a name="activity-library"></a>Библиотека действий
Этот раздел содержит образцы, демонстрирующие дополнительные пользовательские действия в Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как действие Policy4 позволяет Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов для использования в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил, входящий в комплект поставки WF 3.5.  
  
 [Настраиваемое действие для переключения в диапазоне значений](../../../../docs/framework/windows-workflow-foundation/samples/custom-activity-to-switch-on-a-range-of-values.md)  
 Демонстрирует создание настраиваемого действия, которое расширяет использование утверждения <xref:System.Activities.Statements.Switch%601>.  
  
 [Действие LINQ to Objects](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-objects-activity.md)  
 Демонстрирует создание действия для использования LINQ to Objects для запроса элементов в коллекции.  
  
 [Пример LINQ to SQL](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-sql-sample.md)  
 Демонстрирует создание действия для использования запросов к сущностям LINQ to SQL из таблиц в базах данных SQL Server.  
  
 [Использование действия InvokePowerShell](../../../../docs/framework/windows-workflow-foundation/samples/using-the-invokepowershell-activity.md)  
 Демонстрирует способ вызова команд Windows PowerShell с помощью действия InvokePowerShell.  
  
 [Действие RangeEnumeration](../../../../docs/framework/windows-workflow-foundation/samples/rangeenumeration-activity.md)  
 Демонстрирует способ создания пользовательского действия, которое выполняет итерацию по коллекции чисел.  
  
 [Действия с регулярными выражениями](../../../../docs/framework/windows-workflow-foundation/samples/regular-expression-activities.md)  
 Демонстрирует способ создание набора действий, которые представляют функциональные возможности регулярных выражений пространства имен <xref:System.Text.RegularExpressions>.  
  
 [Настраиваемое действие SendMail](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Действие For](../../../../docs/framework/windows-workflow-foundation/samples/for-activity.md)  
 Демонстрирует способ построения пользовательского действия, которое наследует от действия <xref:System.Activities.NativeActivity> и использует рабочий процесс для выполнения итерации по диапазону значений.  
  
 [Ожидание входного действия](../../../../docs/framework/windows-workflow-foundation/samples/wait-for-input-activity.md)  
 Демонстрирует способ создания именованных закладок в рабочем процессе.  
  
 [Параллельное действие ForEach с ограничением](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.  
  
 [Действия с сущностями](../../../../docs/framework/windows-workflow-foundation/samples/entity-activities.md)  
 Показано, как использовать ADO.NET Entity Framework в Windows Workflow Foundation для упрощения доступа к данным.  
  
 [Действия доступа к базе данных](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 Демонстрирует создание действия, которые позволяют получить доступ к базам данных, чтобы вернуть или изменить сведения, а также использовать [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.  
  
 [Действие CommentOut](../../../../docs/framework/windows-workflow-foundation/samples/commentout-activity.md)  
 Демонстрирует способ записи пользовательского действия, которое удаляет другие действия из пути выполнения посредством преобразования их в комментарии.  
  
 [Реализованное действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как действия externalizedpolicy4 можно выполнять существующие Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил это в комплект поставки WF 3.5.  
  
 [Действие NoPersistScope](../../../../docs/framework/windows-workflow-foundation/samples/nopersistscope-activity.md)  
 Демонстрирует способ обработки несериализуемого и высвобождаемого состояния в рабочем процессе.  
  
 [Неуниверсальное действие ForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Неуниверсальное действие ParallelForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение WorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.
