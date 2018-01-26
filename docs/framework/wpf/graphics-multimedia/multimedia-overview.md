---
title: "Общие сведения о мультимедиа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65553e18fc66825c9c0a991aba600b4b90d0d4c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="multimedia-overview"></a>Общие сведения о мультимедиа
Мультимедийные возможности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют интегрировать аудио и видео в приложения для расширения возможностей пользователя. В этом разделе представлены мультимедийные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 
  
<a name="mediaapi"></a>   
## <a name="media-api"></a>API мультимедиа  
 <xref:System.Windows.Controls.MediaElement> И <xref:System.Windows.Media.MediaPlayer> классы используются для представления содержимого аудио и видео. Этими классами можно управлять в интерактивном режиме или с помощью часов. Эти классы можно использовать в элементе управления 10 в [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] для воспроизведения мультимедиа. Выбор класса зависит от сценария.  
  
 <xref:System.Windows.Controls.MediaElement>— <xref:System.Windows.UIElement> , поддерживаемую [макета](../../../../docs/framework/wpf/advanced/layout.md) и могут быть использованы в качестве содержимого многие элементы управления. Его можно также использовать в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] наряду с программным кодом. <xref:System.Windows.Media.MediaPlayer>, с другой стороны, предназначен для <xref:System.Windows.Media.Drawing> объектов и не предоставляет поддержку макета. Носитель, загруженный с помощью <xref:System.Windows.Media.MediaPlayer> могут быть представлены только с помощью <xref:System.Windows.Media.VideoDrawing> или путем непосредственного взаимодействия с <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer>не может использоваться в XAML.  
  
 Дополнительные сведения о графических объектах и контексте рисования см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  При распространении мультимедиа вместе с приложением файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Режимы воспроизведения мультимедиа  
  
> [!NOTE]
>  Оба <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.MediaPlayer> содержат похожие члены. Ссылки в этом разделе, относятся к <xref:System.Windows.Controls.MediaElement> члены класса. Если не указано обратное, элементы, связанные в <xref:System.Windows.Controls.MediaElement> класса также могут находиться в <xref:System.Windows.Media.MediaPlayer> класса.  
  
 Чтобы понимать принципы воспроизведения мультимедиа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], необходимо знание о различных режимах, в которых может воспроизводиться содержимое мультимедиа. Оба <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.MediaPlayer> можно использовать в двух различных режимах: независимом режиме и режиме синхронизации. Режим мультимедиа определяется <xref:System.Windows.Controls.MediaElement.Clock%2A> свойство. Когда <xref:System.Windows.Controls.MediaElement.Clock%2A> — `null`, объект мультимедиа находится в независимом режиме. Когда <xref:System.Windows.Controls.MediaElement.Clock%2A> имеет значение null, объект мультимедиа находится в режиме часов. По умолчанию объекты мультимедиа находятся в независимом режиме.  
  
### <a name="independent-mode"></a>Независимый режим  
 В независимом режиме содержимое мультимедиа управляет своим воспроизведением. Независимый режим имеет следующие параметры.  
  
-   Мультимедиа <xref:System.Uri> можно указывать непосредственно.  
  
-   Воспроизведением мультимедиа можно управлять напрямую.  
  
-   Мультимедиа <xref:System.Windows.Controls.MediaElement.Position%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> свойства могут быть изменены.  
  
 Носитель присвоением значения <xref:System.Windows.Controls.MediaElement> объекта <xref:System.Windows.Controls.MediaElement.Source%2A> свойства или путем вызова <xref:System.Windows.Media.MediaPlayer> объекта <xref:System.Windows.Media.MediaPlayer.Open%2A> метод.  
  
 Для управления воспроизведением мультимедиа в независимом режиме можно использовать управляющие методы объекта мультимедиа. Доступные методы управления <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, и <xref:System.Windows.Controls.MediaElement.Stop%2A>. Для <xref:System.Windows.Controls.MediaElement>, с помощью этих методов интерактивный элемент управления доступен только тогда, когда <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> равно <xref:System.Windows.Controls.MediaState.Manual>. Эти методы недоступны, если объект мультимедиа находится в режиме часов.  
  
 Пример использования независимого режима см. в разделе [Управление элементом MediaElement (воспроизведение, пауза, стоп, громкость и скорость)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Режим часов  
 В режиме часов <xref:System.Windows.Media.MediaTimeline> дисков воспроизведения мультимедиа. Режим часов имеет следующие характеристики.  
  
-   Мультимедиа <xref:System.Uri> задан косвенно через <xref:System.Windows.Media.MediaTimeline>.  
  
-   Воспроизведением мультимедиа можно управлять с помощью часов. Нельзя использовать управляющие методы объекта мультимедиа.  
  
-   Носитель, задав <xref:System.Windows.Media.MediaTimeline> объекта <xref:System.Windows.Media.MediaTimeline.Source%2A> свойство созданием часов из временной шкалы и назначением часов объекту мультимедиа. Также носитель таким образом при <xref:System.Windows.Media.MediaTimeline> внутри <xref:System.Windows.Media.Animation.Storyboard> цели <xref:System.Windows.Controls.MediaElement>.  
  
 Для управления воспроизведением мультимедиа в режиме часов <xref:System.Windows.Media.Animation.ClockController> необходимо использовать методы управления. Объект <xref:System.Windows.Media.Animation.ClockController> берется из <xref:System.Windows.Media.Animation.ClockController> свойство <xref:System.Windows.Media.MediaClock>. При попытке использовать методы управления либо <xref:System.Windows.Controls.MediaElement> или <xref:System.Windows.Media.MediaPlayer> объекта в режиме часов <xref:System.InvalidOperationException> будет создано.  
  
 Дополнительные сведения о часах и временных шкалах см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Пример использования режима часов см. в разделе [Управление элементом MediaElement с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Класс MediaElement  
 Добавление приложения мультимедиа простым добавлением <xref:System.Windows.Controls.MediaElement> управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] приложения и предоставляя <xref:System.Uri> на носитель, которые требуется включить. Все типы мультимедиа, поддерживаемые [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10, также поддерживаются в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. В следующем примере показано простое использование элемента <xref:System.Windows.Controls.MediaElement> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 В этом примере содержимое мультимедиа воспроизводится автоматически по мере его загрузки. После завершения воспроизведения содержимое мультимедиа закрывается, а все ресурсы мультимедиа освобождаются (включая видеопамять). Это поведение по умолчанию <xref:System.Windows.Controls.MediaElement> объекта и определяется <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> свойства.  
  
### <a name="controlling-a-mediaelement"></a>Управление объектом MediaElement  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> И <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> свойства управляют поведением <xref:System.Windows.Controls.MediaElement> при <xref:System.Windows.FrameworkElement.IsLoaded%2A> — `true` или `false`соответственно. <xref:System.Windows.Controls.MediaState> Свойства устанавливаются для влияния на поведение воспроизведения мультимедиа. Например, значение по умолчанию <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> — <xref:System.Windows.Controls.MediaState.Play> и значение по умолчанию <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> — <xref:System.Windows.Controls.MediaState.Close>. Это означает, что как только <xref:System.Windows.Controls.MediaElement> загружена и выполнена предварительной пробы, начинается воспроизведение мультимедиа. После завершения воспроизведения содержимое мультимедиа закрывается и освобождаются все ресурсы мультимедиа.  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> И <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> свойства не являются единственным способом управления воспроизведением мультимедиа. В режиме часов часы могут управлять <xref:System.Windows.Controls.MediaElement> и интерактивные управляющие методы получают управление, если <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> — <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement>обрабатывает конкуренцию за управление, вычисляя следующие приоритеты.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. В случае, когда содержимое мультимедиа выгружается. Это гарантирует, что все ресурсы мультимедиа освобождаются по умолчанию, даже если <xref:System.Windows.Media.MediaClock> связан с <xref:System.Windows.Controls.MediaElement>.  
  
2.  <xref:System.Windows.Media.MediaClock>. В случае, когда мультимедиа имеет <xref:System.Windows.Controls.MediaElement.Clock%2A>. Если мультимедиа выгружен, <xref:System.Windows.Media.MediaClock> вступят в силу при условии, что <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> — <xref:System.Windows.Controls.MediaState.Manual>. Режим часов всегда переопределяет загруженное поведение <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. В случае, когда содержимое мультимедиа загружается.  
  
4.  Интерактивные управляющие методы. В случае, если <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> — <xref:System.Windows.Controls.MediaState.Manual>. Доступные методы управления <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, и <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Отображение объекта MediaElement  
 Для отображения <xref:System.Windows.Controls.MediaElement> он должен иметь содержимое, преобразовываемое и будет иметь его <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> свойства установлено в ноль, пока загрузится содержимое. Для содержимого, в составе которого есть только звук, эти свойства всегда имеют нулевое значение. Для видео после <xref:System.Windows.Controls.MediaElement.MediaOpened> события <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> сообщат размер загруженного мультимедиа. Это означает, что пока носитель, <xref:System.Windows.Controls.MediaElement> не займет физического пространства в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Если <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A> свойств.  
  
 Установка <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства приведет к носитель растягиваются для заполнения области, предоставленной для <xref:System.Windows.Controls.MediaElement>. Для сохранения носителя исходные пропорции, либо <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A> свойство должно иметь значение, но не оба. Установка <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства приведет к отображению мультимедиа в элементе фиксированного размера, который может быть нежелательно.  
  
 Чтобы избежать отображения элемента фиксированного размера, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может сделать предварительную пробу содержимого мультимедиа. Это можно сделать, настроив <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> либо <xref:System.Windows.Controls.MediaState.Play> или <xref:System.Windows.Controls.MediaState.Pause>. В <xref:System.Windows.Controls.MediaState.Pause> состояние носителя будет пробу и передачей первого кадра. В <xref:System.Windows.Controls.MediaState.Play> состоянии, будет Проба и начнет воспроизведение мультимедиа.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Класс MediaPlayer  
 При этом <xref:System.Windows.Controls.MediaElement> класса является элементом структуры <xref:System.Windows.Media.MediaPlayer> класс предназначен для использования в <xref:System.Windows.Media.Drawing> объектов. Графические объекты используются, когда можно пожертвовать возможностями уровня среды, чтобы повысить производительность, а также при необходимости <xref:System.Windows.Freezable> функции. <xref:System.Windows.Media.MediaPlayer>позволяет воспользоваться преимуществами этих функций, предоставляя мультимедийное содержимое для приложений. Как <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> может использоваться в независимом или режиме часов, но может не иметь <xref:System.Windows.Controls.MediaElement> выгрузки и загрузки состояния объекта. Это снижает сложность управления воспроизведением <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Управление объектом MediaPlayer  
 Поскольку <xref:System.Windows.Media.MediaPlayer> — без сохранения состояния, существуют только два способа управления воспроизведением мультимедиа.  
  
1.  Интерактивные управляющие методы. На месте в независимом режиме (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> свойство).  
  
2.  <xref:System.Windows.Media.MediaClock>. В случае, когда мультимедиа имеет <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Отображение объекта MediaPlayer  
 С технической точки зрения <xref:System.Windows.Media.MediaPlayer> невозможно, так как он не имеет физического представления. Тем не менее, он может использоваться для отображения мультимедиа в <xref:System.Windows.Media.Drawing> с помощью <xref:System.Windows.Media.VideoDrawing> класса. В следующем примере показано использование <xref:System.Windows.Media.VideoDrawing> для отображения мультимедиа.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 В разделе [Общие сведения об объектах Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md) Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingGroup>  
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
