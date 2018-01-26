---
title: "Какой &#39; новые возможности Windows Workflow Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c5026c7c3e90afa843b819fb51d7a4a7c8249a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="what39s-new-in-windows-workflow-foundation"></a>Какой &#39; новые возможности Windows Workflow Foundation
В сравнении с предыдущими версиями [!INCLUDE[wf](../../../includes/wf-md.md)] в [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] изменяет несколько принципов разработки. Теперь рабочие процессы стало еще проще создавать, выполнять и поддерживать, а также реализовывать узел с новыми функциями. [!INCLUDE[crabout](../../../includes/crabout-md.md)]перенос .NET 3.0 и .NET 3.5 приложений рабочих процессов, чтобы использовать последнюю версию в разделе [руководство по миграции](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="workflow-activity-model"></a>Модель действий рабочего процесса  
 Теперь действие, а не использования класса <xref:System.Workflow.Activities.SequentialWorkflowActivity> или <xref:System.Workflow.Activities.StateMachineWorkflowActivity> является базовой единицей создания рабочего процесса. Класс <xref:System.Activities.Activity> обеспечивает базовую абстракцию поведения рабочего процесса. Авторы действий могут использовать <xref:System.Activities.CodeActivity> для базовых функций пользовательских действий или <xref:System.Activities.NativeActivity> для функций пользовательских действий, использующих среду выполнения. <xref:System.Activities.Activity>— Это класс, используемый авторы действий для express новые режимы поведения декларативно с точки зрения других <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, или <xref:System.Activities.DynamicActivity> объектов, являются ли они разработанного или не входит в [встроенных действий Библиотека](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).  
  
## <a name="rich-composite-activity-options"></a>Параметры сложных композитных действий  
 <xref:System.Activities.Statements.Flowchart> - это новое мощное действие потока управления, позволяющее авторам моделировать произвольные циклы и условное ветвление. <xref:System.Activities.Statements.Flowchart> предоставляет модель программирования на основе событий, которую раньше можно было реализовать только с помощью <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. Процедурные рабочие процессы получают дополнительные преимущества благодаря новым действиям управления потоком, которые моделируют обычные структуры управления потоком, такие как <xref:System.Activities.Statements.TryCatch> и <xref:System.Activities.Statements.Switch%601>.  
  
## <a name="expanded-built-in-activity-library"></a>Расширенная библиотека встроенных действий  
 Новые функции библиотеки действий:  
  
-   Новые действия управления потоком, такие как <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> и <xref:System.Activities.Statements.ParallelForEach%601>.  
  
-   Действия для обработки данных элементов, такие как <xref:System.Activities.Statements.Assign>, и действия коллекции, такие как <xref:System.Activities.Statements.AddToCollection%601>.  
  
-   Действия для управления транзакциями, такие как <xref:System.Activities.Statements.TransactionScope> и <xref:System.Activities.Statements.Compensate>.  
  
-   Новые действия для обмена сообщениями, такие как <xref:System.ServiceModel.Activities.SendContent> и <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## <a name="explicit-activity-data-model"></a>Явная модель данных действия  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] включает новые варианты хранения и перемещения данных. Данные можно сохранить в действии при помощи переменной <xref:System.Activities.Variable>. При перемещении данных в действие и из него для определения направления перемещения данных используются специальные типы аргументов. Такими типами являются <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> и <xref:System.Activities.OutArgument>. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Модель данных Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/data-model.md).  
  
## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Улучшенные варианты размещения на узле, сохраняемости и отслеживания  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] содержит следующие усовершенствования сохраняемости.  
  
-   Добавлены новые параметры для выполнения рабочих процессов, включая <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> и <xref:System.Activities.WorkflowInvoker>.  
  
-   При помощи действия <xref:System.Activities.Statements.Persist> данные состояния рабочего процесса можно сохранять явным образом.  
  
-   Узел может сохранить экземпляр <xref:System.Activities.ActivityInstance>, не выгружая его.  
  
-   Рабочий процесс может указывать зоны несохраняемости во время работы с данными, которые не могут быть сохранены, чтобы отложить операцию сохраняемости до выхода из зоны несохраняемости.  
  
-   Транзакции могут быть введены в рабочий процесс при помощи <xref:System.Activities.Statements.TransactionScope>.  
  
-   Выполнять отслеживание проще благодаря <xref:System.Activities.Tracking.TrackingParticipant>.  
  
-   Отслеживание и запись в журнал системных событий обеспечивается при помощи <xref:System.Activities.Tracking.EtwTrackingParticipant>.  
  
-   Для возобновления ожидающего рабочего процесса теперь используется объект <xref:System.Activities.Bookmark>.  
  
## <a name="easier-ability-to-extend-wf-designer-experience"></a>Более удобное расширение среды проектирования WF Designer  
 Новый WF Designer построен на основе [!INCLUDE[avalon1](../../../includes/avalon1-md.md)], он обеспечивает более удобную модель для повторного размещения WF Designer за пределами Visual Studio, а также обеспечивает более простые механизмы для создания конструкторов пользовательских действий. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Настройка конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md).
