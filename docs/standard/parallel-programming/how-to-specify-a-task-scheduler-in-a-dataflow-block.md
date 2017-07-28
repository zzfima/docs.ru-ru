---
title: "How to: Specify a Task Scheduler in a Dataflow Block | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TPL dataflow library, linking to task scheduler in TPL"
  - "Task Parallel Library, dataflows"
  - "task scheduler, linking from TPL"
ms.assetid: 27ece374-ed5b-49ef-9cec-b20db34a65e8
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Specify a Task Scheduler in a Dataflow Block
В этом документе приводятся способы привязки определенного планировщика задач при использовании потока данных в приложении.  В этом пример используется класс <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=fullName> в приложении Windows Forms для указания того, когда активна задача чтения и когда активна задача записи.  Здесь также используется метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>, чтобы позволить блоку потока данных выполняться в потоке пользовательского интерфейса.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Для установки пространства имен <xref:System.Threading.Tasks.Dataflow> откройте свой проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Управление пакетами NuGet** в меню "Проект" и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
### Создание приложения Windows Forms  
  
1.  Создайте проект [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]Приложение Windows Forms на  **или Visual Basic.** На следующих этапах проекту дается название `WriterReadersWinForms`.  
  
2.  В конструкторе форм главной формы Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) добавьте четыре элемента управления <xref:System.Windows.Forms.CheckBox>.  Установите свойству <xref:System.Windows.Forms.Control.Text%2A> значение Читатель 1 для `checkBox1`, Читатель 2 для `checkBox2`, Читатель 3 для `checkBox3` и Средство записи для `checkBox4`.  Задайте свойству <xref:System.Windows.Forms.Control.Enabled%2A> каждого элемента управления значение `False`.  
  
3.  Добавьте на форму элемент управления <xref:System.Windows.Forms.Timer>.  Задайте для свойства <xref:System.Windows.Forms.Timer.Interval%2A> значение `2500`.  
  
## Добавление функциональных возможностей потока данных  
 В этом разделе описываются способы создания блоков потока данных, участвующих в приложении, и привязки каждого из них к планировщику заданий.  
  
#### Добавление функциональных возможностей потока данных в приложение  
  
1.  В проекте добавьте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
2.  Убедитесь, что Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) содержит следующие операторы `using` \(`Imports` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#1)]  
  
3.  Добавьте данные\-член <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> в класс `Form1`.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#2)]  
  
4.  В конструкторе `Form1` после вызова `InitializeComponent` создайте объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, который переключает состояние объектов <xref:System.Windows.Forms.CheckBox>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#3)]  
  
5.  В конструкторе `Form1` создайте объект <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> и четыре объекта <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, по одному объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> для каждого объекта <xref:System.Windows.Forms.CheckBox>.  Для каждого объекта <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> укажите объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, у которого свойству <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> задано свойство <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> для читателей и <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> для средства записи.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#4)]  
  
6.  В конструкторе `Form1` запустите объект <xref:System.Windows.Forms.Timer>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#5)]  
  
7.  В конструкторе форм главной формы создайте обработчик событий для события таймера <xref:System.Windows.Forms.Timer.Tick>.  
  
8.  Реализуйте событие <xref:System.Windows.Forms.Timer.Tick> для таймера.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#6)]  
  
 Поскольку блок потока данных `toggleCheckBox` работает с интерфейсом пользователя, важно, чтобы это действие происходило в потоке пользовательского интерфейса.  Для этого в процессе создания этот объект предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, у которого свойству <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> задано значение <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>.  Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации.  Поскольку конструктор `Form1` вызывается из потока пользовательского интерфейса, действие для блока потока данных `toggleCheckBox` также выполняется в потоке пользовательского интерфейса.  
  
 В этом примере также используется класс <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair>, чтобы обеспечить возможность одновременной работы для нескольких блоков потока данных и монопольной работы еще одного блока потока данных в отношении остальных блоков потока данных, выполняемых в этом же объекте <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair>.  Этот способ полезен, когда несколько блоков потока данных совместно используют ресурс, и некоторым требуется монопольный доступ к этому ресурсу, поскольку это исключают потребность вручную синхронизировать доступ к этому ресурсу.  Исключение ручной синхронизации может сделать код более эффективным.  
  
## Пример  
 В следующем примере приведен полный код Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
 [!code-csharp[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#100)]  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)