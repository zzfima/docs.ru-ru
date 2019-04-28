---
title: Общие сведения о Windows Workflow
ms.date: 03/30/2017
ms.assetid: fc44adbe-1412-49ae-81af-0298be44aae6
ms.openlocfilehash: 57c394805d4aa07f8a137af259619bb1e65c43de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61861053"
---
# <a name="windows-workflow-overview"></a>Общие сведения о Windows Workflow
Рабочий процесс представляет собой набор элементарных единиц вызывается *действия* , которые хранятся на модель, описывающую реального процесса. Рабочие процессы позволяют описывать порядок выполнения этапов краткосрочных и долгосрочных работ, а также зависимости между этими этапами. Работа проходит по модели от начала и до конца, а действия могут выполняться как людьми, так и системными функциями.  
  
## <a name="workflow-run-time-engine"></a>Среда выполнения рабочих процессов  
 Каждый работающий экземпляр рабочего процесса создается и обслуживается внутрипроцессной подсистемой среды выполнения, с которой ведущий процесс взаимодействует с помощью одного из следующих инструментов:  
  
- <xref:System.Activities.WorkflowInvoker>, который вызывает рабочий процесс как метод.  
  
- <xref:System.Activities.WorkflowApplication> для явного управления выполнением одного экземпляра рабочего процесса.  
  
- <xref:System.ServiceModel.WorkflowServiceHost> для взаимодействия с помощью сообщений в многоэкземплярных сценариях.  
  
 Каждый из этих классов является оболочкой для среды выполнения основной операции, представленной как объект <xref:System.Activities.ActivityInstance>, ответственный за выполнение операции. В домене приложения может быть несколько объектов <xref:System.Activities.ActivityInstance>, работающих параллельно.  
  
 Каждый из трех предыдущих объектов взаимодействия узлов создается из дерева операций, называемого программой рабочего процесса. С помощью этих типов или пользовательского ведущего приложения, который заключает в оболочку <xref:System.Activities.ActivityInstance>, рабочие процессы могут выполняться внутри любого процесса Windows, включая консольные приложения, приложения на основе форм, службы Windows, [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] веб-сайты и Windows Communication Foundation ( Службы WCF).  
  
 ![Компоненты рабочего процесса в хост-процессе](./media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")  
Компоненты рабочего процесса в хост-процессе  
  
## <a name="interaction-between-workflow-components"></a>Взаимодействие между компонентами рабочего процесса  
 На следующей диаграмме показано взаимодействие компонентов рабочего процесса.  
  
 ![Схема, показывающая, как взаимодействуют компоненты рабочего процесса.](./media/overview/workflow-component-interatction.gif)  
  
 На предыдущей диаграмме используется метод <xref:System.Activities.WorkflowInvoker.Invoke%2A> класса <xref:System.Activities.WorkflowInvoker> для вызова нескольких экземпляров рабочего процесса. <xref:System.Activities.WorkflowInvoker> используется для упрощенных рабочих процессов, не требующих управления с сервера. Рабочие же процессы, требующие управления с сервера (например, возобновление <xref:System.Activities.Bookmark>), должны выполняться с помощью <xref:System.Activities.WorkflowApplication.Run%2A>. Чтобы вызвать экземпляр рабочего процесса, не обязательно ждать завершения другого. Среда выполнения допускает одновременное выполнение нескольких экземпляров рабочего процесса.  Вызываются следующие рабочие процессы:  
  
- Действие <xref:System.Activities.Statements.Sequence>, содержащее дочернее действие <xref:System.Activities.Statements.WriteLine>. Переменная <xref:System.Activities.Variable> родительского действия привязана к <xref:System.Activities.InArgument> дочернего действия. Дополнительные сведения о переменных, аргументах и привязке см. в разделе [переменных и аргументов](variables-and-arguments.md).  
  
- Настраиваемое действие `ReadLine`. <xref:System.Activities.OutArgument> действия `ReadLine` возвращается в вызывающий метод <xref:System.Activities.WorkflowInvoker.Invoke%2A>.  
  
- Настраиваемое действие, происходящее от абстрактного класса <xref:System.Activities.CodeActivity>. <xref:System.Activities.CodeActivity> может обращаться к возможностям среды выполнения (например, к отслеживанию и свойствам) с помощью <xref:System.Activities.CodeActivityContext>, доступного в качестве параметра метода <xref:System.Activities.CodeActivity.Execute%2A>. Дополнительные сведения об этих функциях времени выполнения см. в разделе [отслеживание и трассировка рабочих процессов](workflow-tracking-and-tracing.md) и [свойства выполнения рабочего процесса](workflow-execution-properties.md).  
  
## <a name="see-also"></a>См. также

- [BizTalk Server 2006 или WF? Выбор средства верного потока работ для проекта](https://go.microsoft.com/fwlink/?LinkId=154901)
