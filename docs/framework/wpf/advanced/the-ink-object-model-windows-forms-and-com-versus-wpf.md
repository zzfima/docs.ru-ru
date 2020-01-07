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
ms.openlocfilehash: 2c0d155d320bab2f0114280e962c8f2f0b559681
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636423"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Объектная модель рукописного ввода: Windows Forms и COM по сравнению с WPF

По сути, это три платформы, поддерживающие цифровые рукописные данные: платформа Windows Forms Tablet PC, платформа COM для планшетных ПК и платформа Windows Presentation Foundation (WPF).  Платформы Windows Forms и COM используют схожую объектную модель, но объектная модель для платформы WPF существенно отличается.  В этом разделе обсуждаются различия на высоком уровне, чтобы разработчики, которые работали с одной объектной моделью, могли лучше понять другие.  
  
## <a name="enabling-ink-in-an-application"></a>Включение рукописного ввода в приложении  
 Все три платформы поставляют объекты и элементы управления, позволяющие приложению принимать входные данные от пера планшета.  Платформы Windows Forms и COM поставляются с классами [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)), [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) и [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) .  [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) и [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) — это элементы управления, которые можно добавить в приложение для получения рукописного ввода.  [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) и [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) можно присоединить к существующему окну, чтобы включить поддержку рукописного ввода для окон и пользовательских элементов управления.  
  
 Платформа WPF включает элемент управления <xref:System.Windows.Controls.InkCanvas>.  Вы можете добавить <xref:System.Windows.Controls.InkCanvas> в приложение и начать сбор рукописных данных немедленно. С помощью <xref:System.Windows.Controls.InkCanvas>пользователь может копировать, выбирать и изменять размеры рукописного ввода.  Можно добавить другие элементы управления в <xref:System.Windows.Controls.InkCanvas>, и пользователь может также вводить эти элементы управления.  Вы можете создать пользовательский элемент управления с поддержкой рукописного ввода, добавив в него <xref:System.Windows.Controls.InkPresenter> и собирая свои точки пера.  
  
 В следующей таблице перечислены дополнительные сведения о включении рукописного ввода в приложении.  
  
|Для этого...|На платформе WPF...|На платформах Windows Forms/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Добавление элемента управления с поддержкой рукописного ввода в приложение|См. [Начало работы с рукописным вводом](getting-started-with-ink.md).|См. [Пример формы Auto Claims](/windows/desktop/tablet/auto-claims-form-sample)|  
|Включение рукописного ввода для пользовательского элемента управления|См. раздел [Создание элемента управления рукописного ввода](creating-an-ink-input-control.md).|См. [Пример рукописного текста в буфере обмена](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Рукописные данные  
 На платформах Windows Forms и COM [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))и [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) предоставляют объект [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) . Объект [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) содержит данные для одного или нескольких объектов [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) и предоставляет общие методы и свойства для управления и управления этими штрихами.  Объект [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) управляет временем существования содержащихся в нем штрихов. Объект [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) создает и удаляет штрихи, которыми он владеет.  Каждый элемент [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) имеет идентификатор, уникальный в пределах родительского объекта [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) .  
  
 На платформе WPF класс <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> владеет и управляет своим собственным временем существования. Группу объектов <xref:System.Windows.Ink.Stroke> можно собирать вместе в <xref:System.Windows.Ink.StrokeCollection>, который предоставляет методы для стандартных операций управления рукописными данными, таких как проверка попадания, стирание, преобразование и сериализация рукописных данных. <xref:System.Windows.Ink.Stroke> может принадлежать к нулю, одному или нескольким <xref:System.Windows.Ink.StrokeCollection> объектам в любое время.  Вместо объекта [Microsoft. Ink. ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) <xref:System.Windows.Controls.InkCanvas> и <xref:System.Windows.Controls.InkPresenter> содержат <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 На следующей паре иллюстраций сравниваются объектные модели рукописного ввода данных.  На платформах Windows Forms и COM объект [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) ограничивает время существования объектов [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) , а пакеты пера относятся к отдельным штрихам.  Два или более штриха могут ссылаться на один объект [Microsoft. Ink. DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) , как показано на следующем рисунке.  
  
 ![Схема объектной модели рукописного ввода для&#47;com WinForms.](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 На [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]каждый <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> является объектом среды CLR, который существует, пока что-то имеет ссылку на него.  Каждый <xref:System.Windows.Ink.Stroke> ссылается на <xref:System.Windows.Input.StylusPointCollection> и <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> объект, который также является объектами среды CLR.  
  
 ![Схема объектной модели рукописного ввода для WPF.](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 В следующей таблице сравниваются способы выполнения некоторых распространенных задач на платформе WPF, а также на платформах Windows Forms и COM.  
  
|Задача|Windows Presentation Foundation (WPF)|Windows Forms и COM|  
|----------|-------------------------------------|---------------------------|  
|Сохранить рукописный ввод|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft. Ink. Ink. Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|Загрузка рукописного ввода|Создайте <xref:System.Windows.Ink.StrokeCollection> с помощью конструктора <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A>.|[Microsoft. Ink. Ink. Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|Проверка нажатия|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft. Ink. Ink. HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|Копировать рукописный ввод|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft. Ink. Ink. Клипбоардкопи](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|Вставить рукописный ввод|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft. Ink. Ink. Клипбоардпасте](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|Доступ к пользовательским свойствам коллекции штрихов|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (свойства хранятся внутренне и доступны через <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>и <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Использование [Microsoft. Ink. Ink. расширенных свойств](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>Совместное использование рукописного ввода между платформами  
 Несмотря на то, что платформы имеют различные объектные модели для рукописных данных, совместное использование данных между платформами очень просто. В следующих примерах сохраняются рукописные данные из Windows Forms приложения и загружаются рукописные данные в Windows Presentation Foundation приложение.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 В следующих примерах сохраняются рукописные данные из Windows Presentation Foundation приложения и загружаются рукописные данные в Windows Forms приложение.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>События планшетного пера  

 [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))и [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) на платформах Windows Forms и com получают события, когда пользователь вводит данные пера. [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) или [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) присоединяется к окну или элементу управления и может подписываться на события, создаваемые входными данными планшета. Поток, на котором происходят эти события, зависит от того, вызываются ли события с помощью пера, мыши или программно. Дополнительные сведения о потоках по отношению к этим событиям см. в разделе [Общие вопросы о потоках](/windows/desktop/tablet/general-threading-considerations) и [потоки, в которых может срабатывать событие](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 На Windows Presentation Foundationной платформе класс <xref:System.Windows.UIElement> имеет события для ввода с помощью пера. Это означает, что каждый элемент управления предоставляет полный набор событий пера.  События пера имеют пары событий нисходящей или восходящей маршрутизации и всегда возникают в потоке приложения.  Дополнительные сведения см. в разделе [Общие сведения о перенаправленных событиях](routed-events-overview.md).  
  
 На следующей диаграмме показано сравнение объектных моделей для классов, инициирующих события пера. В объектной модели Windows Presentation Foundation отображаются только события восходящей маршрутизации, а не аналоги событий туннелирования.  
  
 ![Схема событий пера в WPF и WinForms.](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Данные пера  
 Все три платформы предоставляют способы перехвата и обработки данных, поступающих из пера планшета.  На платформах Windows Forms и COM это достигается путем создания [Microsoft. стилусинпут. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)), присоединения к нему окна или элемента управления и создания класса, реализующего интерфейс [Microsoft. стилусинпут. истилуссинкплугин](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) или [Microsoft. стилусинпут. истилусасинкплугин](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) . Затем пользовательский подключаемый модуль добавляется в коллекцию подключаемых модулей объекта [Microsoft. стилусинпут. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)). Дополнительные сведения об этой объектной модели см. [в разделе Архитектура API-интерфейсов стилусинпут](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 На платформе WPF класс <xref:System.Windows.UIElement> предоставляет коллекцию подключаемых модулей, аналогичную структуре [Microsoft. стилусинпут. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)).  Чтобы перехватить данные пера, создайте класс, наследующий от <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, и добавьте объект в коллекцию <xref:System.Windows.UIElement.StylusPlugIns%2A> <xref:System.Windows.UIElement>. Дополнительные сведения об этом взаимодействии см. в разделе [перехват входных данных с помощью пера](intercepting-input-from-the-stylus.md).  
  
 На всех платформах пул потоков получает данные рукописного ввода через события пера и отправляет их в поток приложения.  Дополнительные сведения о многопоточности на платформах COM и Windows см. [в разделе вопросы использования потоков для интерфейсов API стилусинпут](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Дополнительные сведения о многопоточности в программном обеспечении Windows Presentation см. [в статье потоковая модель рукописного ввода](the-ink-threading-model.md).  
  
 На следующем рисунке сравниваются объектные модели для классов, получающих данные пера в пуле потоков пера.  
  
 ![Схема модели Стилусплугин WPF и WinForms.](./media/ink-stylusplugins.png "Ink_StylusPlugins")
