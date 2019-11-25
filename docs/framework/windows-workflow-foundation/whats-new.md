---
title: Новые возможности в Windows Workflow Foundation (WF)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
ms.openlocfilehash: 8f79c6d2a564571f8b753f322a79e91a01b1cf2f
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142001"
---
# <a name="whats-new-in-windows-workflow-foundation"></a>Новые возможности в Windows Workflow Foundation (WF)

Windows Workflow Foundation (WF) в .NET Framework 4 изменяет несколько парадигм разработки из предыдущих версий. Теперь рабочие процессы стало еще проще создавать, выполнять и поддерживать, а также реализовывать узел с новыми функциями. Дополнительные сведения о переносе приложений рабочих процессов .NET 3,0 и .NET 3,5 на использование последней версии см. в [руководстве по миграции](migration-guidance.md).  
  
## <a name="workflow-activity-model"></a>Модель действий рабочего процесса  
 Теперь действие, а не использования класса <xref:System.Workflow.Activities.SequentialWorkflowActivity> или <xref:System.Workflow.Activities.StateMachineWorkflowActivity> является базовой единицей создания рабочего процесса. Класс <xref:System.Activities.Activity> обеспечивает базовую абстракцию поведения рабочего процесса. Авторы действий могут использовать <xref:System.Activities.CodeActivity> для базовых функций пользовательских действий или <xref:System.Activities.NativeActivity> для функций пользовательских действий, использующих среду выполнения. <xref:System.Activities.Activity> — это класс, используемый авторами действий для декларативного выражения новых поведений с точки зрения других <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>или <xref:System.Activities.DynamicActivity> объектов, независимо от того, разработаны они как пользовательские или включенные во [встроенную библиотеку действий](net-framework-4-5-built-in-activity-library.md).  
  
## <a name="rich-composite-activity-options"></a>Параметры сложных композитных действий  
 <xref:System.Activities.Statements.Flowchart> - это новое мощное действие потока управления, позволяющее авторам моделировать произвольные циклы и условное ветвление. <xref:System.Activities.Statements.Flowchart> предоставляет модель программирования на основе событий, которую раньше можно было реализовать только с помощью <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. Процедурные рабочие процессы получают дополнительные преимущества благодаря новым действиям управления потоком, которые моделируют обычные структуры управления потоком, такие как <xref:System.Activities.Statements.TryCatch> и <xref:System.Activities.Statements.Switch%601>.  
  
## <a name="expanded-built-in-activity-library"></a>Расширенная библиотека встроенных действий  
 Новые возможности библиотеки действий:  
  
- Новые действия управления потоком, такие как <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> и <xref:System.Activities.Statements.ParallelForEach%601>.  
  
- Действия для обработки данных элементов, такие как <xref:System.Activities.Statements.Assign>, и действия коллекции, такие как <xref:System.Activities.Statements.AddToCollection%601>.  
  
- Действия для управления транзакциями, такие как <xref:System.Activities.Statements.TransactionScope> и <xref:System.Activities.Statements.Compensate>.  
  
- Новые действия для обмена сообщениями, такие как <xref:System.ServiceModel.Activities.SendContent> и <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## <a name="explicit-activity-data-model"></a>Явная модель данных действия  
 .NET Framework 4 содержит новые варианты хранения или перемещения данных. Данные можно сохранить в действии при помощи переменной <xref:System.Activities.Variable>. При перемещении данных в действие и из него для определения направления перемещения данных используются специальные типы аргументов. Такими типами являются <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> и <xref:System.Activities.OutArgument>. Дополнительные сведения см. в разделе [Windows Workflow Foundation Data Model](data-model.md).  
  
## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Улучшенные варианты размещения на узле, сохраняемости и отслеживания  
 .NET Framework 4 содержит следующие усовершенствования сохраняемости:  
  
- Добавлены новые параметры для выполнения рабочих процессов, включая <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> и <xref:System.Activities.WorkflowInvoker>.  
  
- При помощи действия <xref:System.Activities.Statements.Persist> данные состояния рабочего процесса можно сохранять явным образом.  
  
- Узел может сохранить экземпляр <xref:System.Activities.ActivityInstance>, не выгружая его.  
  
- Рабочий процесс может указывать зоны несохраняемости во время работы с данными, которые не могут быть сохранены, чтобы отложить операцию сохраняемости до выхода из зоны несохраняемости.  
  
- Транзакции могут быть введены в рабочий процесс при помощи <xref:System.Activities.Statements.TransactionScope>.  
  
- Выполнять отслеживание проще благодаря <xref:System.Activities.Tracking.TrackingParticipant>.  
  
- Отслеживание и запись в журнал системных событий обеспечивается при помощи <xref:System.Activities.Tracking.EtwTrackingParticipant>.  
  
- Для возобновления ожидающего рабочего процесса теперь используется объект <xref:System.Activities.Bookmark>.  
  
## <a name="easier-ability-to-extend-wf-designer-experience"></a>Более удобное расширение среды проектирования WF Designer  
 Новый конструктор WF основан на Windows Presentation Foundation (WPF) и предоставляет более простую модель для использования при повторном размещении конструктора WF вне Visual Studio, а также предоставляет более удобные механизмы для создания пользовательских конструкторов действий. Дополнительные сведения см. [в разделе Настройка интерфейса рабочего процесса](customizing-the-workflow-design-experience.md).
