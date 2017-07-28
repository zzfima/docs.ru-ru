---
title: "Библиотека действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Библиотека действий
Образцы в этом разделе демонстрируют дополнительные пользовательские действия в [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## В этом подразделе  
 [Действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как действие Policy4 позволяет использовать объекты [!INCLUDE[wf2](../../../../includes/wf2-md.md)] в объектах [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF 3.5\) <xref:System.Workflow.Activities.Rules.RuleSet> в [!INCLUDE[wf2](../../../../includes/wf2-md.md)] в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\) непосредственно, посредством применения правил, установленных в WF 3.5.  
  
 [Настраиваемое действие для переключения в диапазоне значений](../../../../docs/framework/windows-workflow-foundation/samples/custom-activity-to-switch-on-a-range-of-values.md)  
 Демонстрирует создание настраиваемого действия, которое расширяет использование утверждения <xref:System.Activities.Statements.Switch%601>.  
  
 [Действие LINQ to Objects](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-objects-activity.md)  
 Демонстрирует создание действия для использования LINQ to Objects для запроса элементов в коллекции.  
  
 [LINQ to SQL](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-sql-sample.md)  
 Демонстрирует создание действия для использования запросов к сущностям LINQ to SQL из таблиц в базах данных SQL Server.  
  
 [Использование действия InvokePowerShell](../../../../docs/framework/windows-workflow-foundation/samples/using-the-invokepowershell-activity.md)  
 Демонстрирует способ вызова команд Windows PowerShell с помощью действия InvokePowerShell.  
  
 [Действие RangeEnumeration](../../../../docs/framework/windows-workflow-foundation/samples/rangeenumeration-activity.md)  
 Демонстрирует способ создания пользовательского действия, которое выполняет итерацию по коллекции чисел.  
  
 [Действия с регулярными выражениями](../../../../docs/framework/windows-workflow-foundation/samples/regular-expression-activities.md)  
 Демонстрирует способ создание набора действий, которые представляют функциональные возможности регулярных выражений пространства имен <xref:System.Text.RegularExpressions>.  
  
 [Настраиваемое действие SendMail](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 Описывается создание пользовательского действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Для действия](../../../../docs/framework/windows-workflow-foundation/samples/for-activity.md)  
 Демонстрирует способ построения пользовательского действия, которое наследует от действия <xref:System.Activities.NativeActivity> и использует рабочий процесс для выполнения итерации по диапазону значений.  
  
 [Ожидание входного действия](../../../../docs/framework/windows-workflow-foundation/samples/wait-for-input-activity.md)  
 Демонстрирует способ создания именованных закладок в рабочем процессе.  
  
 [Параллельное действие ForEach с ограничением](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.  
  
 [Действия с сущностями](../../../../docs/framework/windows-workflow-foundation/samples/entity-activities.md)  
 Демонстрирует способ использования ADO.NET Entity Framework с [!INCLUDE[wf2](../../../../includes/wf2-md.md)] для упрощения доступа к данным.  
  
 [Действия доступа к базе данных](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 Демонстрирует способ создания действий, позволяющих выполнять доступ к базам данных для получения или изменения сведений, а также использования [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.  
  
 [Действие CommentOut](../../../../docs/framework/windows-workflow-foundation/samples/commentout-activity.md)  
 Демонстрирует способ записи пользовательского действия, которое удаляет другие действия из пути выполнения посредством преобразования их в комментарии.  
  
 [Реализованное действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрирует, как с помощью действия ExternalizedPolicy4 можно непосредственно выполнять существующие объекты [!INCLUDE[wf2](../../../../includes/wf2-md.md)] в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF 3.5\) <xref:System.Workflow.Activities.Rules.RuleSet> в [!INCLUDE[wf2](../../../../includes/wf2-md.md)] в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\), используя для этого обработчик правил, входящий в комплект поставки WF 3.5.  
  
 [Действие NoPersistScope](../../../../docs/framework/windows-workflow-foundation/samples/nopersistscope-activity.md)  
 Демонстрирует способ обработки несериализуемого и высвобождаемого состояния в рабочем процессе.  
  
 [Неуниверсальное действие ForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Нестандартное действие ParallelForEach](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение GetWorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.