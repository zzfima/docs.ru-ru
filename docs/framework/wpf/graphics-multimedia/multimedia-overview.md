---
title: "Общие сведения о мультимедиа | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "носители"
  - "мультимедиа"
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Общие сведения о мультимедиа
Мультимедийные возможности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют интегрировать в приложения звук и видео, чтобы повысить эффективность работы с ними. В этом разделе представлено описание мультимедийных возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="mediaapi"></a>   
## Мультимедийный интерфейс API  
 Классы <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.MediaPlayer> используются для представления звукового и видеосодержимого.  Управление этими классами может осуществляться интерактивно или с помощью часов.  Эти классы могут использовать элемент управления [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 для воспроизведения мультимедиа. Используемый класс зависит от конкретного сценария.  
  
 Элемент управления <xref:System.Windows.Controls.MediaElement> является элементом <xref:System.Windows.UIElement>, который поддерживается [Макет](../../../../docs/framework/wpf/advanced/layout.md) и используется как содержимое многими элементами управления.  Его также можно использовать в разметке [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или в программном коде. <xref:System.Windows.Media.MediaPlayer>, напротив, предназначен для объектов <xref:System.Windows.Media.Drawing>, и в нем отсутствует поддержка макетов.  Объекты мультимедиа, загруженные с помощью <xref:System.Windows.Media.MediaPlayer>, можно отобразить только при помощи <xref:System.Windows.Media.VideoDrawing> или при непосредственном взаимодействии с <xref:System.Windows.Media.DrawingContext>.  <xref:System.Windows.Media.MediaPlayer> нельзя использовать в языке XAML.  
  
 Дополнительные сведения о графических объектах и контексте рисования см. разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  При распространении мультимедиа вместе с приложением нельзя использовать файл мультимедиа в качестве ресурса проекта.  Вместо этого в файле проекта необходимо задать для типа мультимедиа значение `Content` и для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## Режимы воспроизведения объектов мультимедиа  
  
> [!NOTE]
>  И <xref:System.Windows.Controls.MediaElement>, и <xref:System.Windows.Media.MediaPlayer> содержат похожие члены.  Ссылки в этом разделе относятся к членам класса <xref:System.Windows.Controls.MediaElement>.  Если не указано обратного, то члены, связанные в классе <xref:System.Windows.Controls.MediaElement>, можно также найти и в классе <xref:System.Windows.Media.MediaPlayer>.  
  
 Чтобы понять принцип воспроизведения мультимедиа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], необходимо знание о различных режимах, в которых можно воспроизводить мультимедиа.  И <xref:System.Windows.Controls.MediaElement>, и <xref:System.Windows.Media.MediaPlayer> могут использоваться в двух различных режимах: независимом режиме и режиме часов.  Режим мультимедиа определяется свойством <xref:System.Windows.Controls.MediaElement.Clock%2A>.  Если <xref:System.Windows.Controls.MediaElement.Clock%2A> имеет значение `null`, то объект мультимедиа находится в независимом режиме.  Если <xref:System.Windows.Controls.MediaElement.Clock%2A> имеет значение, отличное от NULL, то объект мультимедиа находится в режиме часов.  По умолчанию объекты мультимедиа находятся в независимом режиме.  
  
### Независимый режим  
 В независимом режиме содержимое мультимедиа управляет воспроизведением мультимедиа.  Независимый режим позволяет следующее:  
  
-   Класс <xref:System.Uri> мультимедиа можно указывать непосредственно.  
  
-   Воспроизведением мультимедиа можно управлять напрямую.  
  
-   Свойства <xref:System.Windows.Controls.MediaElement.Position%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> мультимедиа можно изменять.  
  
 Мультимедиа загружается присвоением значения свойству <xref:System.Windows.Controls.MediaElement.Source%2A> объекта <xref:System.Windows.Controls.MediaElement> или путем вызова метода <xref:System.Windows.Media.MediaPlayer.Open%2A> объекта <xref:System.Windows.Media.MediaPlayer>.  
  
 Для управления воспроизведением мультимедиа в независимом режиме можно использовать управляющие методы объекта мультимедиа.  Доступные управляющие методы: <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A> и <xref:System.Windows.Controls.MediaElement.Stop%2A>.  Для <xref:System.Windows.Controls.MediaElement> интерактивное управление с использованием этих методов доступно только если <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> имеет значение <xref:System.Windows.Controls.MediaState>.  Эти методы недоступны, если объект мультимедиа находится в режиме часов.  
  
 Пример независимого режима см. в разделе [Управление элементом MediaElement \(воспроизведение, пауза, остановка, громкость и скорость\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### Режим часов  
 В режиме часов <xref:System.Windows.Media.MediaTimeline> управляет воспроизведением мультимедиа.  Режим часов имеет следующие характеристики:  
  
-   Класс <xref:System.Uri> мультимедиа задается неявно с помощью <xref:System.Windows.Media.MediaTimeline>.  
  
-   Воспроизведение мультимедиа может управляться часами.  Управляющие методы объекта мультимедиа использовать нельзя.  
  
-   Объект мультимедиа загружается присвоением значения свойству <xref:System.Windows.Media.MediaTimeline.Source%2A> объекта <xref:System.Windows.Media.MediaTimeline>, созданием часов из временной шкалы и назначением часов объекту мультимедиа.  Объект мультимедиа также загружается таким образом, если <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> обращается в <xref:System.Windows.Controls.MediaElement>.  
  
 Для управления воспроизведением мультимедиа в режиме часов должны использоваться управляющие методы класса <xref:System.Windows.Media.Animation.ClockController>.  <xref:System.Windows.Media.Animation.ClockController> берется из свойства <xref:System.Windows.Media.Animation.ClockController> элемента <xref:System.Windows.Media.MediaClock>.  При попытке использовать управляющие методы объектов <xref:System.Windows.Controls.MediaElement> или <xref:System.Windows.Media.MediaPlayer> в режиме часов будет вызвано <xref:System.InvalidOperationException>.  
  
 Дополнительные сведения о часах и временных шкалах см. в разделе общих сведений [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Пример режима часов см. в разделе [Управление элементом MediaElement с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## Класс MediaElement  
 Добавить мультимедиа в приложение просто: нужно добавить элемент управления <xref:System.Windows.Controls.MediaElement> в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] приложения и предоставить <xref:System.Uri> объекту мультимедиа, который требуется включить.  Все типы объектов мультимедиа, поддерживаемые программой [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10, поддерживаются и в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. В следующем примере показано простое использование элемента управления <xref:System.Windows.Controls.MediaElement> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 В этом примере объект мультимедиа воспроизводится автоматически по мере его загрузки.  После завершения воспроизведения мультимедиа закрывается и все ресурсы, используемые мультимедиа, освобождаются \(включая видеопамять\).  Это поведение по умолчанию для объекта <xref:System.Windows.Controls.MediaElement> и оно управляется свойствами <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  
  
### Управление MediaElement  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> управляют поведением <xref:System.Windows.Controls.MediaElement>, когда <xref:System.Windows.FrameworkElement.IsLoaded%2A> имеет значение `true` или `false` соответственно.  Свойства <xref:System.Windows.Controls.MediaState> устанавливаются, чтобы повлиять на поведение воспроизведения объектов мультимедиа.  Например, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> по умолчанию имеет значение <xref:System.Windows.Controls.MediaState>, а <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> по умолчанию имеет значение <xref:System.Windows.Controls.MediaState>.  Это означает, что после загрузки <xref:System.Windows.Controls.MediaElement> и завершения [предварительной пробы](GTMT) начинается воспроизведение мультимедиа.  После завершения воспроизведения мультимедиа закрывается и освобождаются все ресурсы, используемые мультимедиа.  
  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> не являются единственным способом управления воспроизведением мультимедиа.  В режиме часов часы могут управлять объектом <xref:System.Windows.Controls.MediaElement>, а интерактивные управляющие методы получают управление, если свойство <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> имеет значение <xref:System.Windows.Controls.MediaState>.  <xref:System.Windows.Controls.MediaElement> обрабатывает конкуренцию за управление, вычисляя следующие приоритеты.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  В случае выгрузки мультимедиа.  Гарантирует, что все ресурсы мультимедиа освобождаются по умолчанию, даже если <xref:System.Windows.Media.MediaClock> сопоставлен с <xref:System.Windows.Controls.MediaElement>.  
  
2.  <xref:System.Windows.Media.MediaClock>.  В случае, когда мультимедиа имеет <xref:System.Windows.Controls.MediaElement.Clock%2A>.  Если мультимедиа выгружен, то <xref:System.Windows.Media.MediaClock> будет иметь эффект, пока <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> имеет значение <xref:System.Windows.Controls.MediaState>.  Режим часов всегда переопределяет загруженное поведение <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>.  В случае загрузки мультимедиа.  
  
4.  Интерактивные управляющие методы.  В случае, если <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> имеет значение <xref:System.Windows.Controls.MediaState>.  Доступные управляющие методы: <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A> и <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### Отображение свойств MediaElement  
 Для отображения <xref:System.Windows.Controls.MediaElement> он должен иметь содержимое для отображения и значения его свойств <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> будут равными нулю до тех пор, пока не будет загружено содержимое.  Для содержимого, содержащего только звук, эти свойства всегда равны нулю.  Для видео после вызова события <xref:System.Windows.Controls.MediaElement.MediaOpened> свойства <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> сообщат размер загруженного мультимедиа.  Это означает, что до тех пор, пока объект мультимедиа не будет загружен, объект <xref:System.Windows.Controls.MediaElement> не повлияет на [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], так как не потребует физического пространства в нем, если только не заданы свойства <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A>.  
  
 Присвоение значения и свойству <xref:System.Windows.FrameworkElement.Width%2A>, и свойству <xref:System.Windows.FrameworkElement.Height%2A> приведет к растягиванию мультимедиа для заполнения области, предоставленной для <xref:System.Windows.Controls.MediaElement>.  Чтобы сохранить исходные [пропорции](GTMT) мультимедиа, одно из свойств <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A> должно быть задано, но не оба одновременно.  Присвоение значения и свойству <xref:System.Windows.FrameworkElement.Width%2A>, и свойству <xref:System.Windows.FrameworkElement.Height%2A> приведет к отображению мультимедиа в элементе фиксированного размера, а это может быть нежелательным.  
  
 Чтобы избежать элемента фиксированного размера, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может [сделать предварительную пробу](GTMT) мультимедиа.  Это делается путем задания для <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> значения <xref:System.Windows.Controls.MediaState> или <xref:System.Windows.Controls.MediaState>.  В состоянии <xref:System.Windows.Controls.MediaState> мультимедиа делает предварительную пробу и показывает первый кадр.  В состоянии <xref:System.Windows.Controls.MediaState> мультимедиа [сделает предварительную пробу](GTMT) и начнет воспроизведение.  
  
<a name="mediaplayer"></a>   
## Класс MediaPlayer  
 Класс <xref:System.Windows.Controls.MediaElement> является элементом структуры, а класс <xref:System.Windows.Media.MediaPlayer> предназначен для использования в объектах <xref:System.Windows.Media.Drawing>.  Рисованные объекты используются, когда можно пожертвовать возможностями уровня среды ради улучшения производительности или если требуются функции <xref:System.Windows.Freezable>.  <xref:System.Windows.Media.MediaPlayer> позволяет воспользоваться преимуществами этих функций, предоставляя при этом мультимедийное содержимое для приложений.  Как и <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> может использоваться в независимом режиме или режиме часов, но он не располагает состояниями "выгружен" и "загружен", которые есть у объекта <xref:System.Windows.Controls.MediaElement>.  Это уменьшает сложность управления воспроизведением <xref:System.Windows.Media.MediaPlayer>.  
  
### Управление MediaPlayer  
 Поскольку <xref:System.Windows.Media.MediaPlayer> не имеет определенного состояния, существуют только два способа управления воспроизведением мультимедиа.  
  
1.  Интерактивные управляющие методы.  Доступны в независимом режиме \(свойство `null` <xref:System.Windows.Media.MediaPlayer.Clock%2A>\).  
  
2.  <xref:System.Windows.Media.MediaClock>.  В случае, когда мультимедиа имеет <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### Отображение MediaPlayer  
 С технической точки зрения <xref:System.Windows.Media.MediaPlayer> не может быть отображен, так как он не имеет физического представления.  Тем не менее, его можно использовать для отображения мультимедиа в <xref:System.Windows.Media.Drawing> с помощью класса <xref:System.Windows.Media.VideoDrawing>.  В следующем примере демонстрируется использование <xref:System.Windows.Media.VideoDrawing> для отображения мультимедиа.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе общих сведений [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.DrawingGroup>   
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)