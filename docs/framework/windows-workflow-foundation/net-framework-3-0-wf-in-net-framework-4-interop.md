---
title: "Использование действий .NET Framework 3.0 WF на платформе .NET Framework 4 с действием &#171;Interop&#187; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Использование действий .NET Framework 3.0 WF на платформе .NET Framework 4 с действием &#171;Interop&#187;
 <xref:System.Activities.Statements.Interop> действия [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] действия (WF 4.5), являющийся оболочкой для [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] действия (WF 3.5) в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса. Действие WF 3 может быть отдельным действием или целым деревом действий. Выполнение (включая отмену и обработку исключений) и сохраняемость действий [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] происходят в контексте выполняющегося экземпляра рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].  
  
> [!NOTE]
>   <xref:System.Activities.Statements.Interop> действия не отображается в области элементов конструктора рабочих процессов, если проект рабочего процесса содержит его **Требуемая версия .NET Framework** задано значение **.NET Framework 4.5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Условия использования действия WF 3 совместно с действием взаимодействия (Interop)  
 Для успешного выполнения в рамках действия WF 3 <xref:System.Activities.Statements.Interop> действия должны выполняться следующие условия:  
  
-   Действия WF 3 должно быть производным от <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>.  
  
-   Действие WF должно быть объявлено, как `public`, оно не может быть `abstract`.  
  
-   Действие WF 3 должно иметь открытый конструктор по умолчанию.  
  
-   Из-за ограничений интерфейса типы <xref:System.Activities.Statements.Interop> поддерживает действия, <xref:System.Workflow.Activities.HandleExternalEventActivity> и <xref:System.Workflow.Activities.CallExternalMethodActivity> не может быть использоваться непосредственно, но производные действия, созданные с помощью инструмента Workflow Communication Activity (WCA.exe) может использоваться. В разделе [средства Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=178889) Подробные сведения.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Настройка действия WF 3 внутри действия взаимодействия  
 Для настройки отправки и получения данных из действия WF 3 через границы взаимодействия, свойства и метаданные действия WF 3 представляются <xref:System.Activities.Statements.Interop> действия. Свойства метаданных действия WF 3 (такие как <xref:System.Workflow.ComponentModel.Activity.Name%2A>) предоставляются посредством <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A> коллекции. Это коллекция пар имя-значение, используемых для определения значений для свойств метаданных действия WF 3. Свойство метаданных — это свойство, поддерживаемое свойством зависимости, для которого <xref:System.Workflow.ComponentModel.DependencyPropertyOptions> флаг.  
  
 Свойства действия WF 3 предоставляются посредством <xref:System.Activities.Statements.Interop.ActivityProperties%2A> коллекции. Это набор пар имя значение, где каждое значение является <xref:System.Activities.Argument> объект, используемый для определения аргументов для свойства действия WF 3. Поскольку направление свойства действия WF 3 не может быть выведено, каждое свойство отображается как <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument> пары. В зависимости от использования свойства действия, может понадобиться предоставить <xref:System.Activities.InArgument> запись <xref:System.Activities.OutArgument> или обе эти записи. Ожидаемое имя <xref:System.Activities.InArgument> записи в коллекции является именем свойства, определенное в действии WF 3. Ожидаемое имя <xref:System.Activities.OutArgument> записи в коллекции представляет собой объединение имени свойства и строку «Выходной».  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Ограничения использования действия WF 3 в действии взаимодействия  
 Системные действия WF 3 не может быть непосредственно обернуты в <xref:System.Activities.Statements.Interop> действия. Для некоторых действий WF 3 такие как <xref:System.Workflow.Activities.DelayActivity>, это потому, что существует аналогичное действие WF 4.5. Для других это вызвано тем, что функциональные возможности действия не поддерживаются. Многие действия, предоставляемые системой WF 3 может использоваться в рабочих процессах, оболочкой для которого <xref:System.Activities.Statements.Interop> действия со следующими ограничениями:  
  
1.  <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive> не может использоваться в <xref:System.Activities.Statements.Interop> действия.  
  
2.  <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity>, и <xref:System.Workflow.Activities.WebServiceFaultActivity> не может использоваться в <xref:System.Activities.Statements.Interop> действия.  
  
3.  <xref:System.Workflow.Activities.InvokeWorkflowActivity> не может использоваться в <xref:System.Activities.Statements.Interop> действия.  
  
4.  <xref:System.Workflow.ComponentModel.SuspendActivity> не может использоваться в <xref:System.Activities.Statements.Interop> действия.  
  
5.  Действия, связанные с компенсацией, не может использоваться в <xref:System.Activities.Statements.Interop> действия.  
  
 Также существуют некоторые особенности поведения использования действия WF 3 внутри <xref:System.Activities.Statements.Interop> действия:  
  
1.  WF 3 внутри действия <xref:System.Activities.Statements.Interop> деятельность инициализируются при <xref:System.Activities.Statements.Interop> выполняется действие. В WF 4.5 отсутствует фаза инициализации экземпляра рабочего процесса до его выполнения.  
  
2.  Среда выполнения WF 4.5 не не контрольной точки состояния экземпляра рабочего процесса в начале транзакции, независимо от того, где начинается транзакция (внутри или за пределами <xref:System.Activities.Statements.Interop> действия).  
  
3.  Записи отслеживания WF 3 для действий в <xref:System.Activities.Statements.Interop> действия предоставляются участникам отслеживания WF 4.5 как <xref:System.Activities.Tracking.InteropTrackingRecord> объектов. <xref:System.Activities.Tracking.InteropTrackingRecord> является производным от <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4.  Пользовательское действие WF 3 может осуществлять доступ к данным, используя очереди рабочего процесса в среде взаимодействия точно таким же образом, что и в среде выполнения рабочего процесса в WF 3. Вносить изменения в пользовательский код действия не требуется. На узле данных является, поставленных в очередь рабочего процесса WF 3 посредством возобновления закладки <xref:System.Activities.Bookmark>. Имя закладки является формой строка <xref:System.IComparable> имени очереди рабочего процесса.  
  
## <a name="see-also"></a>См. также раздел  
 [С помощью .NET Framework 3.0 или .NET Framework 3.5 действия в рабочем процессе .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)