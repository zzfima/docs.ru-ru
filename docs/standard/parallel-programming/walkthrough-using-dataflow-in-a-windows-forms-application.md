---
title: Пошаговое руководство. Использование потока данных в приложении Windows Forms
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
ms.openlocfilehash: b6f4b933f76834f48d522d9c97fb0c9b5c24e13d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139917"
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a>Пошаговое руководство. Использование потока данных в приложении Windows Forms
В этом документе демонстрируется способ создания сети блоков потока данных, которые выполняют обработку изображений в приложении Windows Forms.  
  
 В этом примере файлы изображения загружаются из указанной папки, из них создается составное изображение, и результат отображается. В данном примере для перемещения изображений по сети используется модель потока данных. В модели потока данных независимые компоненты программы взаимодействуют друг с другом, отправляя сообщения. Когда компонент получает сообщение, он выполняет какое-либо действие и затем передает результат другому компоненту. Сравните это с моделью потока управления, в который приложение использует структуры управления, например условные операторы, циклы и т. д., для управления порядком операций в программе.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Прежде чем начать выполнение этого пошагового руководства, ознакомьтесь с документом [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="sections"></a>Разделы  
 Это пошаговое руководство содержит следующие разделы:  
  
- [Создание приложения Windows Forms](#winforms)  
  
- [Создание сети потока данных](#network)  
  
- [Подключение сети потока данных к пользовательскому интерфейсу](#ui)  
  
- [Полный пример](#complete)  
  
<a name="winforms"></a>   
## <a name="creating-the-windows-forms-application"></a>Создание приложения Windows Forms  
 В этом разделе описывается, как создать простое приложение Windows Forms и добавить элементы управления в главную форму.  
  
### <a name="to-create-the-windows-forms-application"></a>Создание приложения Windows Forms  
  
1. В Visual Studio создайте проект **Приложение Windows Forms** на Visual C# или Visual Basic. В этом документе проект называется `CompositeImages`.  
  
2. В конструкторе форм главной формы Form1.cs (Form1.vb для Visual Basic) добавьте элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
3. Добавьте элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>. Задайте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, а свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> — **Выбрать папку**.  
  
4. Добавьте второй элемент управления <xref:System.Windows.Forms.ToolStripButton> к элементу управления <xref:System.Windows.Forms.ToolStrip>. Задайте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение **Отмена**, а свойству <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> — значение `False`.  
  
5. Добавьте объект <xref:System.Windows.Forms.PictureBox> на главную форму. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.  
  
<a name="network"></a>   
## <a name="creating-the-dataflow-network"></a>Создание сети потока данных  
 В этом разделе описывается способ создания сети потока данных, которая выполняет обработку изображений.  
  
### <a name="to-create-the-dataflow-network"></a>Создание сети потока данных  
  
1. В своем проекте добавьте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
2. Убедитесь, что Form1.cs (Form1.vb для Visual Basic) содержит следующие операторы `using` (`Using` в Visual Basic).  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3. Добавьте в класс `Form1` следующие данные-члены.  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4. Добавьте в класс `CreateImageProcessingNetwork` метод `Form1`. Этот метод создает сеть обработки изображений.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5. Выполните метод `LoadBitmaps`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6. Выполните метод `CreateCompositeBitmap`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    > Версия метода `CreateCompositeBitmap` в C# использует указатели для обеспечения эффективной обработки объектов <xref:System.Drawing.Bitmap?displayProperty=nameWithType>. Поэтому необходимо включить параметр **Разрешить небезопасный код** в проекте для использования ключевого слова [небезопасный](../../csharp/language-reference/keywords/unsafe.md). Дополнительные сведения о включении небезопасного кода в проекте Visual C# см. в разделе [Страница "Сборка" в конструкторе проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
 Следующая таблица описывает члены сети.  
  
|Член|Тип|ОПИСАНИЕ|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Принимает путь папки на входе и создает коллекцию объектов <xref:System.Drawing.Bitmap> на выходе.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Принимает коллекцию объектов <xref:System.Drawing.Bitmap> на входе и подает составной точечный рисунок на выход.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Отображает составной точечный рисунок на форме.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Отображает изображение, чтобы указать, что операция отменена, и позволяет пользователю выбрать другую папку.|  
  
 Для подключения блоков потока данных для формирования сети в этом примере используется метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>. Метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> содержит перегруженную версию, которая принимает объект <xref:System.Predicate%601>, указывающий, допускает или отклоняет блок целевого объекта определенное сообщение. Этот механизм фильтрации позволяет блокам сообщений получать только определенные значения. В этом примере сеть может разветвляться одним из двух способов. Основная ветвь загружает изображения с диска, создает составное изображение и отображает его на форме. Другая ветвь отменяет текущую операцию. Объекты <xref:System.Predicate%601> позволяют блокам потоков данных, работающим по основной ветви, перейти к альтернативной ветви путем отклонения определенных сообщений. Например, если пользователь отменяет операцию, блок потока данных `createCompositeBitmap` выводит `null` (`Nothing` в Visual Basic). Блок потока данных `displayCompositeBitmap` отклоняет входные значения `null`, и поэтому сообщение передается `operationCancelled`. Блок потока данных `operationCancelled` принимает все сообщения и поэтому отображает изображение, чтобы показать, что операция отменена.  
  
 На следующем рисунке показана сеть обработки изображений:  
  
 ![Рисунок, показывающий сеть обработки изображений.](./media/walkthrough-using-dataflow-in-a-windows-forms-application/dataflow-winforms-image-processing.png)  
  
 Поскольку блоки потоков данных `displayCompositeBitmap` и `operationCancelled` работают с интерфейсом пользователя, важно, чтобы эти действия происходили в потоке пользовательского интерфейса. Для этого в процессе создания каждый из этих объектов предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, который содержит свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> со значением <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации. Так как метод `CreateImageProcessingNetwork` вызывается из обработчика кнопки **Выбрать папку**, которая выполняется в потоке пользовательского интерфейса, действия для блоков потока данных `displayCompositeBitmap` и `operationCancelled` также выполняются в потоке пользовательского интерфейса.  
  
 В этом примере используется общий токен отмены, а не устанавливается свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>, поскольку свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> окончательно отменяет выполнение блока потока данных. Токен отмены в этом примере позволяет повторно использовать те же сети потоков данных несколько раз, даже если пользователь отменил одну или несколько операций. Пример, использующий <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>, чтобы окончательно отменить выполнение блока потока данных, см. в разделе [Практическое руководство. Отмена блока потока данных](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>   
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a>Подключение сети потока данных к пользовательскому интерфейсу  
 В этом разделе описывается, как подключить сеть потока данных к интерфейсу пользователя. Создание составного изображения и отмена операции инициализируются кнопками **Выбрать папку** и **Отмена**. Когда пользователь выбирает какую-либо из этих кнопок, соответствующее действие выполняется асинхронно.  
  
### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a>Подключение сети потока данных к пользовательскому интерфейсу  
  
1. В конструкторе форм главной формы создайте обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click> кнопки **Выбрать папку**.  
  
2. Реализуйте событие <xref:System.Windows.Forms.ToolStripItem.Click> кнопки **Выбрать папку**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3. В конструкторе форм главной формы создайте обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click> кнопки **Отмена**.  
  
4. Реализуйте событие <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки **Отмена**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>Полный пример  
 В следующем примере приведен полный код для этого руководства.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 На следующем рисунке показаны типовые выходные данные для общей папки \Sample Pictures\.  
  
 ![Приложение Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")  

## <a name="see-also"></a>См. также

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
