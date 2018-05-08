---
title: 'Объектная модель рукописного ввода: Windows Forms и COM по сравнению с WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: aead6d6bf3956c1b5af56d21fb7c15bd1b80bc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Объектная модель рукописного ввода: Windows Forms и COM по сравнению с WPF

Существует три платформы, поддерживающие рукописный: платформы Windows Forms планшетных ПК, платформа COM для планшетных ПК и платформы Windows Presentation Foundation (WPF).  Папки платформы Windows Forms и COM, аналогичной модели объекта, если объект модели для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] платформы существенно отличается.  В этом разделе описываются различия на высоком уровне, чтобы разработчики, которые работали с одной модели объекта позволяет лучше понять другой.  
  
## <a name="enabling-ink-in-an-application"></a>Включение рукописного ввода в приложении  
 Все три платформы поставляют объекты и элементы управления, которые позволяют приложению получать ввод от пера.  Windows Forms и COM платформы поставляются вместе с [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) и [ Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) классы.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) и [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) являются элементами управления, которые можно добавить в приложение для сбора рукописного ввода.  [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) и [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) можно прикрепить к существующему окну, чтобы включить рукописного ввода windows и пользовательских элементов управления.  
  
 Платформа WPF включает <xref:System.Windows.Controls.InkCanvas> элемента управления.  Можно добавить <xref:System.Windows.Controls.InkCanvas> в приложение и начать сбор немедленно рукописного ввода. С <xref:System.Windows.Controls.InkCanvas>, пользователь может скопировать, выберите и измените размер рукописного ввода.  Можно добавить другие элементы управления для <xref:System.Windows.Controls.InkCanvas>, и пользователь может подписывать их в эти элементы управления слишком.  Можно создать пользовательский элемент управления, поддержка рукописного ввода, добавив <xref:System.Windows.Controls.InkPresenter> и сбора его точек пера.  
  
 В следующей таблице перечислены дополнительные сведения о включении рукописного ввода в приложении:  
  
|Чтобы сделать это...|На платформе WPF...|На платформах Windows Forms/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Добавление элемента управления рукописного ввода в приложение|В разделе [Приступая к работе с заметкой рукописного ввода](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|В разделе [автоматического утверждения образуют образца](http://msdn.microsoft.com/bec4333a-62ca-4254-a39b-04bc2c556992)|  
|Включить рукописный ввод в пользовательский элемент управления|В разделе [создания заметки рукописного ввода входного управления](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|В разделе [рукописного ввода образец буфера обмена](http://msdn.microsoft.com/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## <a name="ink-data"></a>Данные рукописного ввода  
 На платформах COM и Windows Forms [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), и [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) каждого предоставляют [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) объекта. [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) объект содержит данные для одного или нескольких [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) объектов и предоставляет общие методы и свойства для управления и этими штрихами.  [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) объекта управляет временем существования штрихов, она содержит; [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) объект создает и удаляет штрихи, которому он принадлежит.  Каждый [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) имеет идентификатор, который является уникальным в пределах родительского [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) объекта.  
  
 На платформе WPF <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> класс владеет и управляет своим собственным временем жизни. Группы <xref:System.Windows.Ink.Stroke> объединяются объекты в <xref:System.Windows.Ink.StrokeCollection>, который предоставляет методы для общих рукописного ввода операций по управлению данными например попаданий тестирование, стирание, преобразование и сериализация рукописный ввод. Объект <xref:System.Windows.Ink.Stroke> может принадлежать ноль, один или несколько <xref:System.Windows.Ink.StrokeCollection> дать объектов в любое время.  Вместо того, [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) объекта, <xref:System.Windows.Controls.InkCanvas> и <xref:System.Windows.Controls.InkPresenter> содержат <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 В следующей паре иллюстраций сравниваются объектные модели рукописного ввода данных.  На платформах COM и Windows Forms [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) объекта ограничивает время существования [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) объектов и пакеты пера принадлежат отдельных штрихов рукописного ввода.  Два или более штрихов могут ссылаться на же [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) объекта, как показано на следующем рисунке.  
  
 ![Схема модели объекта Ink для COM&#47;Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 На [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], каждая <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> является объект CLR, существуют до тех пор, пока что-нибудь содержит ссылку на него.  Каждый <xref:System.Windows.Ink.Stroke> ссылки <xref:System.Windows.Input.StylusPointCollection> и <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> объекта, которые также являются объектами среды CLR.  
  
 ![Схема модели объекта Ink для WPF. ] (../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 В следующей таблице сравниваются способы выполнения общих задач на [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] платформы и платформы Windows Forms и COM.  
  
|Задача|Windows Presentation Foundation|Windows Forms и COM|  
|----------|-------------------------------------|---------------------------|  
|Сохранение рукописного ввода|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Загрузка рукописного ввода|Создание <xref:System.Windows.Ink.StrokeCollection> с <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> конструктор.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Проверка нажатия|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Копирование рукописного ввода|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Вставьте рукописного ввода|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Доступ к настраиваемым свойствам набора штрихов рукописного ввода|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (внутренне хранятся и доступны через свойства <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, и <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Используйте [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Совместное использование рукописного ввода между платформами  
 Хотя платформы имеют разные объектные модели для заметки рукописного ввода данных, совместное использование данных между платформами является очень простым. В следующих примерах сохранение рукописного ввода из приложения Windows Forms и загрузка рукописный ввод в приложение Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 В следующих примерах сохранение рукописного ввода из приложения Windows Presentation Foundation и загрузить рукописный ввод в приложении Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>События из пера  
 [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), и [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) в Windows Forms и COM платформы получают события при пользователя входные данные пера данных.  [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) или [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) подключен к окну или элементу управления и можно подписаться на события, вызываемые входными данными планшета.  Поток, на котором эти события возникают зависит от того, вызываются ли события с помощью пера, мышь, или программно.  Дополнительные сведения о работе с потоками в связи с этими событиями см. в разделе [общие вопросы работы с потоками](http://msdn.microsoft.com/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) и [потоков, на котором срабатывают события](http://msdn.microsoft.com/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 На платформе Windows Presentation Foundation <xref:System.Windows.UIElement> класс имеет события перо. Это означает, что каждый элемент управления предоставляет полный набор событий пера.  События пера имеют туннелирование восходящей событий пар и всегда выполняется в потоке приложения.  Дополнительные сведения см. в разделе [направлено Общие сведения о событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 На следующей схеме показано сравниваются объектные модели для классов, которые инициируют события пера. Объектной модели Windows Presentation Foundation показывает только восходящей события, а не туннелирования им события.  
  
 ![Схема событий пера в WPF и Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Данные пера  
 Все три платформы предоставляют способа перехвата и обработки данных, поступающих от пера.  На платформах Windows Forms и COM, это достигается путем создания [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx)подсоединением к нему окна или элемента управления и создания класса, который реализует [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) или [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) интерфейса. Пользовательский подключаемый модуль добавляется к коллекции [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Дополнительные сведения об этой объектной модели см. в разделе [архитектура потоке на платформах](http://msdn.microsoft.com/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 На [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] платформы, <xref:System.Windows.UIElement> класс предоставляет доступ к коллекции из подключаемых модулей, разработке похожую [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Для перехвата данных пера, создайте класс, наследующий от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> и добавить объект к <xref:System.Windows.UIElement.StylusPlugIns%2A> коллекцию <xref:System.Windows.UIElement>. Дополнительные сведения об этом взаимодействии см. в разделе [перехват ввод от пера](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 На всех платформах пул потоков получает данные рукописного ввода с помощью событий пера и отправляет их в потоке приложения.  Дополнительные сведения о работе с потоками на платформах Windows и COM см. в разделе [рекомендации по работе с потоками потоке на платформах](http://msdn.microsoft.com/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Дополнительные сведения о работе с потоками в презентации программного обеспечения Windows см. в разделе [потоковая модель рукописного ввода](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 На следующем рисунке сравниваются объектные модели для классов, которые получают данные пера в пуле потоков пера.  
  
 ![Схема StylusPlugin модели WPF и Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")
