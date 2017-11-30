---
title: "Практическое руководство. Отмена блока потока данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a>Практическое руководство. Отмена блока потока данных
В этом документе показано, как включить отмену в приложении. В этом примере используется Windows Forms для отображения позиции активности рабочих элементов в конвейере потока данных, а также последствий отмены.  
  
> [!TIP]
>  Библиотека потоков данных TPL (пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Чтобы установить <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск в Интернете `Microsoft.Tpl.Dataflow` пакета.  
  
### <a name="to-create-the-windows-forms-application"></a>Создание приложения Windows Forms  
  
1.  Создайте проект **Приложение Windows Forms** на C# или Visual Basic. На следующих этапах проекту дается название `CancellationWinForms`.  
  
2.  В конструкторе форм главной формы Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) добавьте элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
3.  Добавьте элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>. Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойства <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> и <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства **Добавить рабочие элементы**.  
  
4.  Добавьте второй элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>. Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойства <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства **отменить**и <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> свойства `False`.  
  
5.  Добавьте четыре объекта <xref:System.Windows.Forms.ToolStripProgressBar> в элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
## <a name="creating-the-dataflow-pipeline"></a>Создание конвейера потока данных  
 В этом разделе описано, как создать конвейер потока данных, который обрабатывает рабочие элементы и обновляет индикаторы выполнения.  
  
#### <a name="to-create-the-dataflow-pipeline"></a>Создание конвейера потока данных  
  
1.  В проекте добавьте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
2.  Убедитесь, что Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) содержит следующие операторы `using` (`Imports` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Добавьте класс `WorkItem` как внутренний тип класса `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Добавьте в класс `Form1` следующие данные-члены.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Добавьте в класс `CreatePipeline` метод `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Поскольку блоки потоков данных `incrementProgress` и `decrementProgress` работают с интерфейсом пользователя, важно, чтобы эти действия происходили в потоке пользовательского интерфейса. Для этого в процессе создания каждый из этих объектов предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, в котором свойству <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> задано значение <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации. Поскольку конструктор `Form1` вызывается из потока пользовательского интерфейса, действия для блоков потоков данных `incrementProgress` и `decrementProgress` также выполняются в потоке пользовательского интерфейса.  
  
 В этом примере задается свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> при создании частей конвейера. Поскольку свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> полностью отменяет выполнение блока потока данных, весь конвейер должен быть заново создан после того, как пользователь отменит операцию и затем захочет добавить нескольких рабочих элементов в конвейер. Пример, демонстрирующий альтернативный способ отмены блока потока данных, чтобы другие работы могли выполняться после отмены операции, см. в разделе [Пошаговое руководство. Использование потока данных в приложении Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a>Подключение конвейера потока данных к пользовательскому интерфейсу  
 В этом разделе описывается, как подключить конвейер потока данных к интерфейсу пользователя. Как созданием конвейера, так и добавлением рабочих элементов в конвейере управляет обработчик событий для кнопки **Добавление рабочих элементов**. Отмена инициируется кнопкой **Отмена**. Когда пользователь нажимает какую-либо из этих кнопок, соответствующее действие выполняется асинхронным образом.  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a>Подключение конвейера потока данных к пользовательскому интерфейсу  
  
1.  В конструкторе форм главной формы создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событий для **Добавить рабочие элементы** кнопки.  
  
2.  Реализуйте <xref:System.Windows.Forms.ToolStripItem.Click> событий для **Добавить рабочие элементы** кнопки.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  В конструкторе форм главной формы создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для **отменить** кнопки.  
  
4.  Реализуйте <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для **отменить** кнопки.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a>Пример  
 В следующем примере приведен полный код Form1.cs (Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 Ниже показано запущенное приложение.  
  
 ![Приложение Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
## <a name="see-also"></a>См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
