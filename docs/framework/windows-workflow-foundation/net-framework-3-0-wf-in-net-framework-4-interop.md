---
title: Использование действий .NET Framework 3.0 WF на платформе .NET Framework 4 с действием «Interop»
ms.date: 03/30/2017
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
ms.openlocfilehash: de0a0474f0a996ce8c781064f56c03b483ca1bb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283193"
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>Использование действий .NET Framework 3.0 WF на платформе .NET Framework 4 с действием «Interop»
Действие <xref:System.Activities.Statements.Interop> — это действие [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4,5), которое служит оболочкой для действия .NET Framework 3,5 (WF 3,5) в рамках рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Действие WF 3 может быть отдельным действием или целым деревом действий. Выполнение (включая отмену и обработку исключений) и сохраняемость действия .NET Framework 3,5 происходит в контексте выполняемого экземпляра рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].  
  
> [!NOTE]
> Действие <xref:System.Activities.Statements.Interop> не отображается в области элементов конструктора рабочих процессов, если параметру **Целевая версия .NET Framework** в проекте рабочего процесса не присвоено значение **.NET Framework 4.5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Условия использования действия WF 3 совместно с действием взаимодействия (Interop)  
 Для успешного выполнения действия WF 3 в действии <xref:System.Activities.Statements.Interop> необходимо соблюдение следующих условий:  
  
- Действие WF 3 должно быть производным от действия <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType>.  
  
- Действие WF должно быть объявлено, как `public`, оно не может быть `abstract`.  
  
- Действие WF 3 должно иметь общедоступный конструктор без параметров.  
  
- Из-за ограничений типов интерфейсов, поддерживаемых действием <xref:System.Activities.Statements.Interop>, <xref:System.Workflow.Activities.HandleExternalEventActivity> и <xref:System.Workflow.Activities.CallExternalMethodActivity> не могут использоваться непосредственно, но можно использовать производные действия, созданные с помощью инструмента Workflow Communication Activity (WCA.exe). Дополнительные сведения см. в разделе [Windows Workflow Foundation Tools](https://go.microsoft.com/fwlink/?LinkId=178889) .  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Настройка действия WF 3 внутри действия взаимодействия  
 Для настройки, отправки и получения данных из действия WF 3 через границы взаимодействия свойства и метаданные действия WF 3 представляются действием <xref:System.Activities.Statements.Interop>. Свойства метаданных действия WF 3 (например, <xref:System.Workflow.ComponentModel.Activity.Name%2A>) предоставляются посредством коллекции <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A>. Это коллекция пар имя-значение, используемых для определения значений для свойств метаданных действия WF 3. Свойство метаданных - это свойство, поддерживаемое свойством зависимости, для которого установлен флаг <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata>.  
  
 Свойства действия WF 3 предоставляются посредством коллекции <xref:System.Activities.Statements.Interop.ActivityProperties%2A>. Это набор пар имя-значение, где каждое значение - это объект <xref:System.Activities.Argument>, используемый для определения аргументов для свойств действия WF 3. Поскольку направление свойства действия WF 3 не может быть определено, каждое свойство отображается в виде пары <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument>. В зависимости от способа использования свойства действием может потребоваться предоставить запись <xref:System.Activities.InArgument>, запись <xref:System.Activities.OutArgument> или обе эти записи. Ожидаемое имя записи <xref:System.Activities.InArgument> в коллекции - это имя свойства, определенное в действии WF 3. Ожидаемое имя записи <xref:System.Activities.OutArgument> в коллекции — это объединение имени свойства и строки "out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Ограничения использования действия WF 3 в действии взаимодействия  
 Действия WF 3, предоставленные системой, могут быть непосредственно обернуты в оболочку действия <xref:System.Activities.Statements.Interop>. Для некоторых действий WF 3, например для <xref:System.Workflow.Activities.DelayActivity>, это вызвано тем, что существует аналогичное действие WF 4.5. Для других это вызвано тем, что функциональные возможности действия не поддерживаются. Многие действия WF 3, предоставляемые системой, могут быть использованы в рабочих процессах, обернутых в оболочку действия <xref:System.Activities.Statements.Interop>, со следующими ограничениями:  
  
1. <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive> нельзя использовать в действии <xref:System.Activities.Statements.Interop>.  
  
2. <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity>и <xref:System.Workflow.Activities.WebServiceFaultActivity> нельзя использовать в рамках действия <xref:System.Activities.Statements.Interop>.  
  
3. <xref:System.Workflow.Activities.InvokeWorkflowActivity> нельзя использовать в действиях <xref:System.Activities.Statements.Interop>.  
  
4. <xref:System.Workflow.ComponentModel.SuspendActivity> нельзя использовать в действиях <xref:System.Activities.Statements.Interop>.  
  
5. Действия, связанные с компенсацией, не могут использоваться внутри действия <xref:System.Activities.Statements.Interop>.  
  
 Существуют некоторые особенности поведения действий WF 3, используемых в действии <xref:System.Activities.Statements.Interop>:  
  
1. Действия WF 3, содержащиеся в действии <xref:System.Activities.Statements.Interop>, инициализируются при выполнении действия <xref:System.Activities.Statements.Interop>. В WF 4.5 отсутствует фаза инициализации экземпляра рабочего процесса до его выполнения.  
  
2. Среда выполнения WF 4.5 не расставляет контрольные точки состояния экземпляра рабочего процесса при запуске транзакции вне зависимости от того, где начинается транзакция (в действии <xref:System.Activities.Statements.Interop> или за его границами).  
  
3. Записи отслеживания WF 3 для действий в действии <xref:System.Activities.Statements.Interop> предоставляются участникам отслеживания WF 4.5 в виде объектов <xref:System.Activities.Tracking.InteropTrackingRecord>. <xref:System.Activities.Tracking.InteropTrackingRecord> является производной от <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4. Пользовательское действие WF 3 может осуществлять доступ к данным, используя очереди рабочего процесса в среде взаимодействия точно таким же образом, что и в среде выполнения рабочего процесса в WF 3. Вносить изменения в пользовательский код действия не требуется. В ведущем приложении данные вносятся в очередь рабочего процесса WF 3 посредством возобновления закладки <xref:System.Activities.Bookmark>. Имя закладки - это строковая форма имени очереди рабочего процесса <xref:System.IComparable>.
