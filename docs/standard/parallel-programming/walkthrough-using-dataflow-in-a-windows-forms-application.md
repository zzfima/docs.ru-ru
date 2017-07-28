---
title: "Walkthrough: Using Dataflow in a Windows Forms Application | Microsoft Docs"
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
  - "TPL dataflow library, in Windows Forms"
  - "Task Parallel Library, dataflows"
  - "Windows Forms, and TPL"
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using Dataflow in a Windows Forms Application
Этот документ демонстрирует, как создать сеть блоков потока данных, которые выполняют обработку изображений в приложении Windows Forms.  
  
 В этом примере файлы изображения загружается из указанной папки, из них создается составное изображение и результат отображается.  В этом примере для перемещения изображений по сети используется модель потока данных.  В модели потока данных независимые компоненты программы взаимодействуют друг с другом посредством отправки сообщений.  Когда компонент получает сообщение, он выполняет какое\-либо действие и передает результат другому компоненту.  Сравните эту модель с моделью потока управления, в которой приложение управляет действиями программы с помощью структур управления, например условных операторов, циклов и так далее.  
  
## Обязательные компоненты  
 Прежде чем начать выполнение этого пошагового руководства, необходимо ознакомиться с разделом [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Подразделы  
 Это пошаговое руководство содержит следующие подразделы.  
  
-   [Создание приложения Windows Forms](#winforms)  
  
-   [Создание сети потока данных](#network)  
  
-   [Подключение сети потока данных к пользовательскому интерфейсу](#ui)  
  
-   [Полный код примера](#complete)  
  
<a name="winforms"></a>   
## Создание приложения Windows Forms  
 В этом разделе описывается, как создать простое приложение Windows Forms и добавить элементы управления на главную форму.  
  
#### Для создания приложения Windows Forms  
  
1.  В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] создайте проект [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] или Visual Basic **Приложение Windows Forms**.  В этом документе проект называется `CompositeImages`.  
  
2.  В конструкторе форм главной формы Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), добавьте элемент управления <xref:System.Windows.Forms.ToolStrip>.  
  
3.  Добавьте элемент управления <xref:System.Windows.Forms.ToolStripButton> на элемент управления <xref:System.Windows.Forms.ToolStrip>.  Установите свойство <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> равным <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, а свойство <xref:System.Windows.Forms.ToolStripItem.Text%2A> равным "Выбрать папку".  
  
4.  Добавьте второй элемент управления <xref:System.Windows.Forms.ToolStripButton> на элемент управления <xref:System.Windows.Forms.ToolStrip>.  Задайте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение "Отмена", а свойству <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> значение `False`.  
  
5.  Добавьте объект <xref:System.Windows.Forms.PictureBox> на главную форму.  Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
<a name="network"></a>   
## Создание сети потока данных  
 В этом разделе описывается создание сети потока данных, которая выполняет обработку изображений.  
  
#### Для создания сети потока данных  
  
1.  Добавьте в проекте ссылку на System.Threading.Tasks.Dataflow.dll.  
  
2.  Убедитесь, что Form1 \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) содержит следующие операторы `using` \(`Using` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\):  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  Добавьте в класс `Form1` следующие члены данных:  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  Добавьте в класс `Form1` метод `CreateImageProcessingNetwork`.  Этот метод создает сеть обработки изображений.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  Реализуйте метод `LoadBitmaps`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  Реализуйте метод `CreateCompositeBitmap`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  C\# версия метода `CreateCompositeBitmap` использует указатели для обеспечения эффективной обработки объектов <xref:System.Drawing.Bitmap?displayProperty=fullName>.  Поэтому необходимо включить параметр **Разрешить небезопасный код** в проекте для использования ключевого слова [небезопасный](../Topic/unsafe%20\(C%23%20Reference\).md).  Дополнительные сведения о включении небезопасного кода в проекте [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] см. в разделе [Страница "Построение" в конструкторе проектов \(C\#\)](../Topic/Build%20Page,%20Project%20Designer%20\(C%23\).md).  
  
 В следующей таблице описаны члены сети.  
  
|Член|Тип|Описание|  
|----------|---------|--------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Принимает путь папки на входе и создает коллекцию объектов <xref:System.Drawing.Bitmap> на выходе.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Получает коллекцию объектов <xref:System.Drawing.Bitmap> на входе и подает составное растровое изображение на выход.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Отображает составное растровое изображение на форме.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Отображает изображение, чтобы указать, что операция отменена, и позволяет пользователю выбрать другую папку.|  
  
 Для подключения блоков потока данных для формирования сети в этом примере используется метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>.  Метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> содержит перегруженную версию, которая принимает объект <xref:System.Predicate%601>, указывающий, допускает или отклоняет блок целевого объекта сообщение.  Этот механизм фильтрации позволяет блокам сообщений получать только определенные значения.  В этом примере в сети может пойти по одной из двух возможных ветвей.  Основная ветвь загружает изображения с диска, создает составное изображение и отображает его на форме.  Другая ветвь отменяет текущую операцию.  Объекты <xref:System.Predicate%601> позволяют блокам потока данных, работающим по основной ветви, перейти к альтернативной ветви путем отклонения определенных сообщения.  Например, если пользователь отменил операцию, блок потока данных `createCompositeBitmap` на выход подает `null` \(`Nothing` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  Блок потока данных `displayCompositeBitmap` отклоняет входные значения `null`, и поэтому сообщение передается `operationCancelled`.  Блок потока данных `operationCancelled` принимает все сообщения и поэтому отображает изображение, чтобы показать, что операция отменена.  
  
 На следующем рисунке показана сеть обработки изображений.  
  
 ![Сеть обработки изображений](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")  
  
 Поскольку блоки потока данных `displayCompositeBitmap` и `operationCancelled` работают с интерфейсом пользователя, важно, чтобы эти действия происходили в потоке пользовательского интерфейса.  Для этого в процессе построения каждый из этих объектов предоставляет объект <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>, который содержит свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> со значением <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>.  Метод <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> создает объект <xref:System.Threading.Tasks.TaskScheduler>, выполняющий работу в текущем контексте синхронизации.  Поскольку метод `CreateImageProcessingNetwork` вызывается из обработчика кнопки "Выбор папки", которая выполняется в потоке пользовательского интерфейса, действия для блокировки потока данных `displayCompositeBitmap` и `operationCancelled` также выполняются в потоке пользовательского интерфейса.  
  
 В этом примере используется общий токен отмены, а не устанавливается свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>, поскольку свойство <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> окончательно отменяет выполнение блока потока данных.  Токен отмены в этом примере позволяет повторно использовать те же сети потока данных несколько раз, даже если пользователь отменил одну или несколько операций.  Пример, использующий <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> чтобы окончательно отменить выполнение блока потока данных см. в разделе [How to: Cancel a Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>   
## Подключение сети потока данных к пользовательскому интерфейсу  
 В этом разделе описывается, как подключить сеть потока данных к интерфейсу пользователя.  Создание составного изображения и отмена операции инициализируются кнопками "Выбрать папку" и "Отмена".  Когда пользователь выбирает какую\-либо из этих кнопок, соответствующее действие выполняется асинхронно.  
  
#### Для подключения сети потока данных к пользовательскому интерфейсу  
  
1.  В конструкторе форм главной формы создайте обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click> кнопки "Выбрать папку".  
  
2.  Реализуйте событие <xref:System.Windows.Forms.ToolStripItem.Click> кнопки "Выбрать папку".  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  В конструкторе форм главной формы создайте обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click> кнопки "Отмена".  
  
4.  Реализуйте событие <xref:System.Windows.Forms.ToolStripItem.Click> кнопки "Отмена".  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## Полный код примера  
 В следующем примере приведен полный код этого руководства.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 На следующем рисунке показаны типичные выходные данные для общей папки \\Sample Pictures\\.  
  
 ![Приложение Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow\_CompositeImages")  
  
## Следующие действия  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)