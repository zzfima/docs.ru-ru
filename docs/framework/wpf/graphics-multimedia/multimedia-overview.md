---
title: Общие сведения о мультимедиа
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 44059fe96a0deeda18f0abd9079100b55be98e77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929624"
---
# <a name="multimedia-overview"></a>Общие сведения о мультимедиа
Мультимедийные возможности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют интегрировать аудио и видео в приложения для расширения возможностей пользователя. В этом разделе представлены мультимедийные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API мультимедиа  
 Классы <xref:System.Windows.Controls.MediaElement> и<xref:System.Windows.Media.MediaPlayer> используются для представления аудио или видео содержимого. Этими классами можно управлять в интерактивном режиме или с помощью часов. Эти классы можно использовать в элементе управления 10 в [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] для воспроизведения мультимедиа. Выбор класса зависит от сценария.  
  
 <xref:System.Windows.Controls.MediaElement>— Это <xref:System.Windows.UIElement> объект, который поддерживается [макетом](../advanced/layout.md) и может использоваться как содержимое многих элементов управления. Его можно также использовать в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] наряду с программным кодом. <xref:System.Windows.Media.MediaPlayer>, с другой стороны, предназначен для <xref:System.Windows.Media.Drawing> объектов и не имеет поддержки макета. Носитель, загруженный <xref:System.Windows.Media.MediaPlayer> с помощью, может быть представлен <xref:System.Windows.Media.VideoDrawing> только с помощью или путем <xref:System.Windows.Media.DrawingContext>непосредственного взаимодействия с. <xref:System.Windows.Media.MediaPlayer>не может использоваться в XAML.  
  
 Дополнительные сведения о графических объектах и контексте рисования см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> При распространении мультимедиа вместе с приложением файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Режимы воспроизведения мультимедиа  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement> И<xref:System.Windows.Media.MediaPlayer> имеют похожие члены. Ссылки в этом разделе относятся к <xref:System.Windows.Controls.MediaElement> членам класса. Если не указано особо, члены, связанные с <xref:System.Windows.Controls.MediaElement> в классе, также можно найти <xref:System.Windows.Media.MediaPlayer> в классе.  
  
 Чтобы понимать принципы воспроизведения мультимедиа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], необходимо знание о различных режимах, в которых может воспроизводиться содержимое мультимедиа. И, <xref:System.Windows.Media.MediaPlayer> и могут использоваться в двух различных режимах мультимедиа, независимом режиме и режиме часов. <xref:System.Windows.Controls.MediaElement> Режим мультимедиа определяется <xref:System.Windows.Controls.MediaElement.Clock%2A> свойством. Если <xref:System.Windows.Controls.MediaElement.Clock%2A> параметр `null`имеет значение, объект мультимедиа находится в независимом режиме. Если параметр <xref:System.Windows.Controls.MediaElement.Clock%2A> имеет значение, отличное от NULL, объект мультимедиа находится в режиме часов. По умолчанию объекты мультимедиа находятся в независимом режиме.  
  
### <a name="independent-mode"></a>Независимый режим  
 В независимом режиме содержимое мультимедиа управляет своим воспроизведением. Независимый режим имеет следующие параметры.  
  
- <xref:System.Uri> Носитель можно указать непосредственно.  
  
- Воспроизведением мультимедиа можно управлять напрямую.  
  
- Свойства носителя <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> и могут быть изменены. <xref:System.Windows.Controls.MediaElement.Position%2A>  
  
 Носитель загружается либо путем установки <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Controls.MediaElement.Source%2A> <xref:System.Windows.Media.MediaPlayer> свойства объекта, либо <xref:System.Windows.Media.MediaPlayer.Open%2A> путем вызова метода объекта.  
  
 Для управления воспроизведением мультимедиа в независимом режиме можно использовать управляющие методы объекта мультимедиа. <xref:System.Windows.Controls.MediaElement.Play%2A>Доступные методы управления: <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>,, и. <xref:System.Windows.Controls.MediaElement.Stop%2A> Для <xref:System.Windows.Controls.MediaElement>интерактивное управление, использующее эти методы, доступно только <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> в том случае <xref:System.Windows.Controls.MediaState.Manual>, если для задано значение. Эти методы недоступны, если объект мультимедиа находится в режиме часов.  
  
 Пример использования независимого режима см. в разделе [Управление элементом MediaElement (воспроизведение, пауза, стоп, громкость и скорость)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Режим часов  
 В режиме часов диск воспроизводится на <xref:System.Windows.Media.MediaTimeline> диске. Режим часов имеет следующие характеристики.  
  
- Носитель косвенно устанавливается <xref:System.Windows.Media.MediaTimeline>через. <xref:System.Uri>  
  
- Воспроизведением мультимедиа можно управлять с помощью часов. Нельзя использовать управляющие методы объекта мультимедиа.  
  
- Носитель загружается путем задания <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaTimeline.Source%2A> свойства объекта, создания часов из временной шкалы и назначения часов объекту мультимедиа. Носитель также загружается таким образом, <xref:System.Windows.Media.MediaTimeline> когда объект <xref:System.Windows.Media.Animation.Storyboard> a обращается <xref:System.Windows.Controls.MediaElement>к.  
  
 Для управления воспроизведением мультимедиа в режиме <xref:System.Windows.Media.Animation.ClockController> часов необходимо использовать методы управления. Объект <xref:System.Windows.Media.Animation.ClockController> извлекается <xref:System.Windows.Media.Animation.ClockController> из свойства объекта <xref:System.Windows.Media.MediaClock>. При попытке использования управляющих методов <xref:System.Windows.Controls.MediaElement> объекта или <xref:System.Windows.Media.MediaPlayer> <xref:System.InvalidOperationException> в режиме часов будет выдано исключение.  
  
 Дополнительные сведения о часах и временных шкалах см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 Пример использования режима часов см. в разделе [Управление элементом MediaElement с помощью раскадровки](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Класс MediaElement  
 Добавление мультимедиа в приложение — это просто добавление <xref:System.Windows.Controls.MediaElement> элемента управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в приложение и предоставление <xref:System.Uri> к носителю, который вы хотите включить. Все типы мультимедиа, поддерживаемые [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10, также поддерживаются в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. В следующем примере показано простое использование <xref:System.Windows.Controls.MediaElement> в. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 В этом примере содержимое мультимедиа воспроизводится автоматически по мере его загрузки. После завершения воспроизведения содержимое мультимедиа закрывается, а все ресурсы мультимедиа освобождаются (включая видеопамять). Это поведение по умолчанию для <xref:System.Windows.Controls.MediaElement> объекта и управляется <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> свойствами и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> .  
  
### <a name="controlling-a-mediaelement"></a>Управление объектом MediaElement  
 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.FrameworkElement.IsLoaded%2A> Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> управляют поведением, если имеет`true` значение или`false`соответственно. <xref:System.Windows.Controls.MediaState> Свойства задаются для изменения поведения воспроизведения мультимедиа. Например, значение <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> по умолчанию <xref:System.Windows.Controls.MediaState.Play> —, а <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> значение <xref:System.Windows.Controls.MediaState.Close>по умолчанию —. Это означает, что, как только <xref:System.Windows.Controls.MediaElement> загрузится и будет выполнена Предзагрузка, начнется воспроизведение носителя. После завершения воспроизведения содержимое мультимедиа закрывается и освобождаются все ресурсы мультимедиа.  
  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> не являются единственным способом управления воспроизведением мультимедиа. В режиме часов часы могут контролировать <xref:System.Windows.Controls.MediaElement> , а методы интерактивного управления <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> — управлять тем, когда имеет <xref:System.Windows.Controls.MediaState.Manual>значение. <xref:System.Windows.Controls.MediaElement>обрабатывает этот конкурс для управления, оценивая следующие приоритеты.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. В случае, когда содержимое мультимедиа выгружается. Это гарантирует, что все ресурсы мультимедиа будут освобождены по умолчанию, <xref:System.Windows.Media.MediaClock> даже если объект связан <xref:System.Windows.Controls.MediaElement>с.  
  
2. <xref:System.Windows.Media.MediaClock>. На месте, <xref:System.Windows.Controls.MediaElement.Clock%2A>когда у мультимедиа есть. Если носитель выгружается, то вступит <xref:System.Windows.Media.MediaClock> в силу при условии <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> , что имеет <xref:System.Windows.Controls.MediaState.Manual>значение. Режим часов всегда переопределяет загруженное поведение <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. В случае, когда содержимое мультимедиа загружается.  
  
4. Интерактивные управляющие методы. На месте, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> если <xref:System.Windows.Controls.MediaState.Manual>имеет. <xref:System.Windows.Controls.MediaElement.Play%2A>Доступные методы управления: <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>,, и. <xref:System.Windows.Controls.MediaElement.Stop%2A>  
  
### <a name="displaying-a-mediaelement"></a>Отображение объекта MediaElement  
 Для отображения <xref:System.Windows.Controls.MediaElement> он должен иметь содержимое для подготовки к просмотру, а свойства <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> имеют значение 0, пока содержимое не будет загружено. Для содержимого, в составе которого есть только звук, эти свойства всегда имеют нулевое значение. Для видеоматериала после того <xref:System.Windows.Controls.MediaElement.MediaOpened> , как событие было <xref:System.Windows.FrameworkElement.ActualWidth%2A> вызвано <xref:System.Windows.FrameworkElement.ActualHeight%2A> , и сообщит о размере загруженного носителя. Это означает <xref:System.Windows.Controls.MediaElement> , что до загрузки носителя не будет занимать никакого физического пространства в, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] если <xref:System.Windows.FrameworkElement.Width%2A> не заданы свойства <xref:System.Windows.FrameworkElement.Height%2A> или.  
  
 Установка обоих <xref:System.Windows.FrameworkElement.Width%2A> свойств и <xref:System.Windows.FrameworkElement.Height%2A> приведет к растяжению носителя для заполнения области, <xref:System.Windows.Controls.MediaElement>предоставленной для. Чтобы сохранить исходные пропорции носителя, <xref:System.Windows.FrameworkElement.Width%2A> необходимо задать свойство или <xref:System.Windows.FrameworkElement.Height%2A> , но не то и другое. Установка обоих <xref:System.Windows.FrameworkElement.Width%2A> свойств и <xref:System.Windows.FrameworkElement.Height%2A> приведет к тому, что носитель будет представлен фиксированным размером элемента, который может оказаться нежелательным.  
  
 Чтобы избежать отображения элемента фиксированного размера, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может сделать предварительную пробу содержимого мультимедиа. Это можно сделать, задав <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play> для параметра значение или <xref:System.Windows.Controls.MediaState.Pause>. <xref:System.Windows.Controls.MediaState.Pause> В состоянии носитель будет предварительно рулоном и будет представлять первый кадр. <xref:System.Windows.Controls.MediaState.Play> В состоянии носитель будет предварительно восстановлен и начнет воспроизводиться.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Класс MediaPlayer  
 Если класс является элементом платформы <xref:System.Windows.Media.MediaPlayer> , класс предназначен для использования в <xref:System.Windows.Media.Drawing> объектах. <xref:System.Windows.Controls.MediaElement> Графические объекты используются, когда вы можете пожертвовать функциями уровня инфраструктуры, чтобы повысить производительность или необходимость <xref:System.Windows.Freezable> использования функций. <xref:System.Windows.Media.MediaPlayer>позволяет использовать преимущества этих функций при предоставлении мультимедийного содержимого в приложениях. Like <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> может использоваться в независимом или часовом режиме, <xref:System.Windows.Controls.MediaElement> но не содержит выгруженных и загруженных состояний объекта. Это сокращает сложность <xref:System.Windows.Media.MediaPlayer>элемента управления воспроизведением.  
  
### <a name="controlling-mediaplayer"></a>Управление объектом MediaPlayer  
 Поскольку <xref:System.Windows.Media.MediaPlayer> не имеет состояния, существует два способа управления воспроизведением мультимедиа.  
  
1. Интерактивные управляющие методы. На месте в независимом режиме (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> свойство).  
  
2. <xref:System.Windows.Media.MediaClock>. На месте, <xref:System.Windows.Media.MediaPlayer.Clock%2A>когда у мультимедиа есть.  
  
### <a name="displaying-a-mediaplayer"></a>Отображение объекта MediaPlayer  
 Технически <xref:System.Windows.Media.MediaPlayer> невозможно отобразить, так как у него нет физического представления. Однако его можно использовать для представления мультимедиа в <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.VideoDrawing> помощью класса. В следующем примере показано использование <xref:System.Windows.Media.VideoDrawing> для вывода мультимедиа.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Дополнительные сведения об <xref:System.Windows.Media.Drawing> объектах см. в [обзоре объектов Drawing](drawing-objects-overview.md) .  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.DrawingGroup>
- [Макет](../advanced/layout.md)
- [Разделы практического руководства](audio-and-video-how-to-topics.md)
