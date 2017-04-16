---
title: "How to: Cancel a Dataflow Block | Microsoft Docs"
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
  - "Task Parallel Library, dataflows"
  - "dataflow blocks, canceling in TPL"
  - "TPL dataflow library,canceling dataflow blocks"
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Cancel a Dataflow Block
В этом документе показано, как включить отмену в приложении.  В этом примере используется Windows Forms для отображения позиции активности рабочих элементов в конвейере потока данных, а также эффекта отмены.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
### Для создания приложения Windows Forms  
  
1.  Создайте проект C\# или Visual Basic **Windows Forms Application**.  На следующем шаге проекту дается название `CancellationWinForms`.  
  
2.  В конструкторе форм главной формы Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), добавьте элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
3.  Добавьте элемент управления <xref:System.Windows.Forms.ToolStripButton> на элемент управления <xref:System.Windows.Forms.ToolStrip>.  Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle> и свойство <xref:System.Windows.Forms.ToolStripItem.Text%2A> в Add Work Items.  
  
4.  Добавьте второй элемент управления <xref:System.Windows.Forms.ToolStripButton> на элемент управления <xref:System.Windows.Forms.ToolStrip>.  Задайте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение "Отмена", а свойству <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> значение `False`.  
  
5.  Добавьте четыре объекта <xref:> System.Windows.Forms.ToolStripProgressBar?qualifyHint=False&autoUpgrade=True в элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
## Создание конвейера потока данных  
 В этом разделе описано, как создать конвейер потока данных, который обрабатывает рабочие элементы и обновляет индикаторы выполнения.  
  
#### Чтобы создать конвейер потока данных  
  
1.  В проекте добавьте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
2.  Убедитесь, что Form1 \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) содержит следующие операторы `using` \(`Imports` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Добавьте класс `WorkItem` как внутренний тип класса `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Добавьте в класс `Form1` следующие члены данных.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Добавьте в класс `Form1` метод `CreatePipeline`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Поскольку блоки потока данных `incrementProgress` и `decrementProgress` работают с интерфейсом пользователя, важно, чтобы эти действия происходили в потоке пользовательского интерфейса.  Для этого в процессе построения каждый из этих объектов предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, который содержит свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> со значением <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>.  Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации.  Поскольку конструктор `Form1` вызывается из потока пользовательского интерфейса, действия для блоков потока данных `incrementProgress` и `decrementProgress` также выполняются в потоке пользовательского интерфейса.  
  
 В этом примере задается свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> при создании членов конвейера.  Поскольку свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> полностью отменяет выполнение блока потока данных, весь конвейер должен быть заново создан после того, как пользователь отменил операцию и затем хочет добавить нескольких рабочих элементов в конвейер.  Пример, демонстрирующий альтернативный способ отмены блока потока данных, чтобы другие работы могли выполняться после отмены операции, см. в разделе [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## Подключение конвейера потока данных к пользовательскому интерфейсу  
 В этом разделе описывается, как подключить конвейер потока данных к интерфейсу пользователя.  Создание конвейера и добавление рабочих элементов в конвейере управляется обработчиком событий для кнопки Add Work Items.  Отмена инициируется кнопкой Cancel.  Когда пользователь выбирает какую\-либо из этих кнопок, соответствующее действие выполняется асинхронно.  
  
#### Чтобы подключить конвейер потока данных к пользовательскому интерфейсу  
  
1.  В конструкторе форм главной формы создайте обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click> кнопки Add Work Items.  
  
2.  Реализуйте события <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки Add Work Items.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  В конструкторе форм главной формы создайте обработчик событий для события кнопки Cancel <xref:System.Windows.Forms.ToolStripItem.Click>.  
  
4.  Реализуйте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки Cancel.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## Пример  
 В следующем примере приведен полный код Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 Ниже показано запущенное приложение.  
  
 ![Приложение Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow\_Cancellation")  
  
## Отказоустойчивость  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)