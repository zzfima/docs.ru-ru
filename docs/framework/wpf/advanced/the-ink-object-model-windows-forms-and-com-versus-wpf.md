---
title: "Объектная модель рукописного ввода: Windows Forms и COM по сравнению с WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "включение рукописного ввода"
  - "события, планшетное перо"
  - "объектная модель рукописного ввода"
  - "рукописный ввод, включение"
  - "InkCanvas - элемент управления"
  - "планшетное перо, события"
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Объектная модель рукописного ввода: Windows Forms и COM по сравнению с WPF
Существует три платформы, поддерживающие рукописный ввод: платформа Windows Forms для планшетных ПК, платформа COM для планшетных ПК и платформа [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Платформы Windows Forms и COM совместно используют сходную объектную модель, но объектная модель для платформы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] существенно отличается.  В этом разделе на обсуждается разница на высоком уровне, так что разработчики, работавшие с одной объектной моделью, смогли лучше понять другие.  
  
## Включение рукописного ввода в приложении  
 Все три платформы поставляют объекты и элементы управления, позволяющие приложению получать входные данные от планшетного пера.  Платформы Windows Forms и COM поставляются с классами <xref:Microsoft.Ink.InkPicture>, <xref:Microsoft.Ink.InkEdit>, <xref:Microsoft.Ink.InkOverlay> и <xref:Microsoft.Ink.InkCollector>.  <xref:Microsoft.Ink.InkPicture> и <xref:Microsoft.Ink.InkEdit> ― это элементы управления, которые можно добавить в приложение для сбора рукописных данных.  <xref:Microsoft.Ink.InkOverlay> и <xref:Microsoft.Ink.InkCollector> могут быть присоединены к существующему окну, чтобы окна и пользовательские элементы управления поддерживали рукописный ввод.  
  
 Платформа WPF включает элемент управления <xref:System.Windows.Controls.InkCanvas>.  Можно добавить <xref:System.Windows.Controls.InkCanvas> в приложение и начать сбор рукописных данных немедленно.  С помощью <xref:System.Windows.Controls.InkCanvas> пользователь может копировать, выделять и изменять размер рукописных данных.  Можно добавить в <xref:System.Windows.Controls.InkCanvas> другие элементы управления, и пользователь сможет вводить рукописные данные в эти элементы управления тоже.  Можно создать пользовательский элемент управления, поддерживающий рукописный ввод, путем добавления ему <xref:System.Windows.Controls.InkPresenter> и сбора его точек пера.  
  
 В следующей таблице перечислены разделы, в которых можно получить более подробные сведения о включении рукописного ввода в приложение.  
  
|Чтобы сделать это...|На платформе WPF…|На платформах Windows Forms\/COM...|  
|--------------------------|-----------------------|-----------------------------------------|  
|Добавить в приложение элемент, поддерживающий рукописные данные|См. раздел [Начало работы с рукописными данными](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|См. раздел [Auto Claims Form Sample](http://msdn.microsoft.com/ru-ru/bec4333a-62ca-4254-a39b-04bc2c556992).|  
|Включить рукописный ввод в пользовательском элементе управления|См. раздел [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|См. раздел [Ink Clipboard Sample](http://msdn.microsoft.com/ru-ru/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## Данные рукописного ввода  
 На платформах Windows Forms и COM, каждый из <xref:Microsoft.Ink.InkCollector>, <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkEdit> и <xref:Microsoft.Ink.InkPicture> предоставляет объект <xref:Microsoft.Ink.Ink?displayProperty=fullName>.  Объект <xref:Microsoft.Ink.Ink> содержит данные для одного или нескольких объектов <xref:Microsoft.Ink.Stroke?displayProperty=fullName> и предоставляет общие методы и свойства для управления этими штрихами.  Объект <xref:Microsoft.Ink.Ink> управляет временем жизни содержащихся в нем штрихов; объект <xref:Microsoft.Ink.Ink> создает и удаляет содержащиеся в нем штрихи.  Каждый <xref:Microsoft.Ink.Stroke> имеет идентификатор, который является уникальным в пределах родительского объекта <xref:Microsoft.Ink.Ink>.  
  
 На платформе WPF, класс <xref:System.Windows.Ink.Stroke?displayProperty=fullName> владеет и управляет своим собственным временем жизни.  Группа объектов <xref:System.Windows.Ink.Stroke> может быть собрана воедино в <xref:System.Windows.Ink.StrokeCollection>, который предоставляет методы для общих операций управления рукописными данными, таких как проверка попадания курсора, стирание, преобразование и сериализация рукописных данных.  <xref:System.Windows.Ink.Stroke> может принадлежать ни одному, одному или нескольким объектам <xref:System.Windows.Ink.StrokeCollection> в одно и то же время.  Вместо того, чтобы содержать объект <xref:Microsoft.Ink.Ink?displayProperty=fullName>, <xref:System.Windows.Controls.InkCanvas> и <xref:System.Windows.Controls.InkPresenter> содержат <xref:System.Windows.Ink.StrokeCollection?displayProperty=fullName>.  
  
 На следующей паре иллюстраций сравниваются объектные модели рукописного ввода данных.  На платформах Windows Forms и COM объект <xref:Microsoft.Ink.Ink?displayProperty=fullName> ограничивает время жизни объектов <xref:Microsoft.Ink.Stroke?displayProperty=fullName>, и пакеты пера принадлежат отдельным штрихам.  Два или более штрихов могут ссылаться на один и тот же объект <xref:Microsoft.Ink.DrawingAttributes?displayProperty=fullName>, как показано на следующей иллюстрации.  
  
 ![Схема модели объекта Ink для COM&#47;Winforms.](../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink\_InkOwnsStrokes")  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] каждый <xref:System.Windows.Ink.Stroke?displayProperty=fullName> является объектом среды CLR, который существует до тех пор, пока какой\-нибудь объект имеет ссылку на него.  Каждый <xref:System.Windows.Ink.Stroke> ссылается на <xref:System.Windows.Input.StylusPointCollection> и объект <xref:System.Windows.Ink.DrawingAttributes?displayProperty=fullName>, которые также являются объектами среды CLR.  
  
 ![Схема модели объекта Ink для WPF.](../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink\_WPFInkObjectModel")  
  
 В следующей таблице сравниваются способы выполнения некоторых общих задач на платформе [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и на платформах Windows Forms и COM.  
  
|Задача|Windows Presentation Foundation \(WPF\)|Windows Forms и COM|  
|------------|---------------------------------------------|-------------------------|  
|Сохранение рукописного ввода|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|<xref:Microsoft.Ink.Ink.Save%2A>|  
|Загрузка рукописного ввода|Создайте <xref:System.Windows.Ink.StrokeCollection> с конструктором <xref:System.Windows.Ink.StrokeCollection.%23ctor%28System.IO.Stream%29?displayProperty=fullName>.|[M:Microsoft.Ink.Ink.Load\(System.Byte\<xref:Microsoft.Ink.Ink.Load%2A>|  
|Проверка нажатия|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|<xref:Microsoft.Ink.Ink.HitTest%2A>|  
|Копирование рукописного ввода|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|<xref:Microsoft.Ink.Ink.ClipboardCopy%2A>|  
|Вставка рукописного ввода|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|<xref:Microsoft.Ink.Ink.ClipboardPaste%2A>|  
|Доступ к настраиваемым свойствам в коллекции штрихов|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> \(свойства хранятся внутри и доступны с помощью <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A> и <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>\)|Используйте <xref:Microsoft.Ink.Ink.ExtendedProperties%2A>.|  
  
### Совместное использование рукописного ввода между платформами  
 Хотя платформы имеют различные объектные модели для рукописных данных, совместное использование данных между платформами является очень простым.  В следующих примерах происходит сохранение рукописных данных из приложения Windows Forms и загрузка рукописных данных в приложение Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 В следующих примерах происходит сохранение рукописных данных из приложения Windows Presentation Foundation и загрузка рукописных данных в приложение Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]  
  
## События планшетного пера  
 <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkCollector> и <xref:Microsoft.Ink.InkPicture> на платформах Windows Forms и COM получают события, когда пользователь вводит данные пера.  <xref:Microsoft.Ink.InkOverlay> или <xref:Microsoft.Ink.InkCollector> присоединяется к окну или элементу управления и может подписаться на события, вызываемые входными данными планшета.  Поток, на котором эти события возникают, зависит от того, вызываются ли эти события с помощью пера, мыши или программно.  Дополнительные сведения о потоке в связи с этими событиями см. в разделах [General Threading Considerations](http://msdn.microsoft.com/ru-ru/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) и [Threads on Which an Event Can Fire](http://msdn.microsoft.com/ru-ru/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 На платформе Windows Presentation Foundation класс <xref:System.Windows.UIElement> имеет события для входных данных пера.  Это означает, что каждый элемент управления предоставляет полный набор событий пера.  События пера имеют пары событий нисходящей\/восходящей маршрутизации и всегда возникают в потоке приложения.  Дополнительные сведения см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 На следующей диаграмме показано сравнение объектных моделей для классов, которые инициируют события пера.  Объектная модель Windows Presentation Foundation показывает только события восходящей маршрутизации, но не парные им события нисходящей маршрутизации.  
  
 ![Схема событий пера в WPF и Winforms.](../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink\_StylusEvents")  
  
## Данные пера  
 Все три платформы предоставляют способы перехвата и обработки данных, поступающих от планшетного пера.  На платформах Windows Forms и COM это достигается путем создания <xref:Microsoft.StylusInput.RealTimeStylus>, присоединения к нему окна или элемента управления, и создания класса, который реализует интерфейс <xref:Microsoft.StylusInput.IStylusSyncPlugin> или <xref:Microsoft.StylusInput.IStylusAsyncPlugin>.  Затем пользовательский подключаемый модуль добавляется к коллекции <xref:Microsoft.StylusInput.RealTimeStylus>.  Дополнительные сведения об этой объектной модели см. в разделе [Architecture of the StylusInput APIs](http://msdn.microsoft.com/ru-ru/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 На платформе [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] класс <xref:System.Windows.UIElement> предоставляет коллекцию подключаемых модулей, при разработке похожую на <xref:Microsoft.StylusInput.RealTimeStylus>.  Чтобы перехватить данные пера, создайте класс, наследуемый из <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, и добавьте объект к коллекции <xref:System.Windows.UIElement.StylusPlugIns%2A> элементов <xref:System.Windows.UIElement>.  Дополнительные сведения об этом взаимодействии см. в разделе [Перехват ввода, осуществляемого пером](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 На всех платформах поток получает данные рукописного ввода с помощью событий пера и отправляет их потоку приложения.  Дополнительные сведения о потоке на платформах COM и Windows см. в разделе [Threading Considerations for the StylusInput APIs](http://msdn.microsoft.com/ru-ru/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Дополнительные сведения о потоке в Windows Presentation Software см. в разделе [Потоковая модель рукописного ввода](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 На следующем рисунке сравниваются объектные модели для классов, которые получают данные пера в пуле потоков пера.  
  
 ![Схема модели StylusPlugin в WPF и Winforms.](../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink\_StylusPlugins")