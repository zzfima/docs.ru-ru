---
title: Общие сведения о мультимедиа
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 42d0d388e859b556d23b7fc81931cd61470ba541
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039805"
---
# <a name="multimedia-overview"></a>Общие сведения о мультимедиа
Мультимедийные возможности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют интегрировать аудио и видео в приложения для расширения возможностей пользователя. В этом разделе представлены мультимедийные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>   
## <a name="media-api"></a>API мультимедиа  
 Классы <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.MediaPlayer> используются для представления содержимого аудио или видео. Этими классами можно управлять в интерактивном режиме или с помощью часов. Эти классы могут использоваться в элементе управления проигрывателя Microsoft Windows Media 10 для воспроизведения мультимедиа. Выбор класса зависит от сценария.  
  
 <xref:System.Windows.Controls.MediaElement> — это <xref:System.Windows.UIElement>, который поддерживается [макетом](../advanced/layout.md) и может использоваться как содержимое многих элементов управления. Его можно также использовать в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] наряду с программным кодом. <xref:System.Windows.Media.MediaPlayer>, с другой стороны, предназначен для <xref:System.Windows.Media.Drawing> объектов и не имеет поддержки макета. Носитель, загруженный с помощью <xref:System.Windows.Media.MediaPlayer>, может быть представлен только с помощью <xref:System.Windows.Media.VideoDrawing> или непосредственного взаимодействия с <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer> нельзя использовать в XAML.  
  
 Дополнительные сведения о графических объектах и контексте рисования см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> При распространении мультимедиа вместе с приложением файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Режимы воспроизведения мультимедиа  
  
> [!NOTE]
> Как <xref:System.Windows.Controls.MediaElement>, так и <xref:System.Windows.Media.MediaPlayer> имеют похожие члены. Ссылки в этом разделе относятся к членам класса <xref:System.Windows.Controls.MediaElement>. Если не указано особо, члены, связанные с в классе <xref:System.Windows.Controls.MediaElement>, также могут быть найдены в классе <xref:System.Windows.Media.MediaPlayer>.  
  
 Чтобы понимать принципы воспроизведения мультимедиа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], необходимо знание о различных режимах, в которых может воспроизводиться содержимое мультимедиа. И <xref:System.Windows.Controls.MediaElement>, и <xref:System.Windows.Media.MediaPlayer> можно использовать в двух различных режимах мультимедиа, независимом режиме и режиме часов. Режим мультимедиа определяется свойством <xref:System.Windows.Controls.MediaElement.Clock%2A>. Если <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`, объект мультимедиа находится в независимом режиме. Если <xref:System.Windows.Controls.MediaElement.Clock%2A> не равно null, объект мультимедиа находится в режиме часов. По умолчанию объекты мультимедиа находятся в независимом режиме.  
  
### <a name="independent-mode"></a>Независимый режим  
 В независимом режиме содержимое мультимедиа управляет своим воспроизведением. Независимый режим имеет следующие параметры.  
  
- <xref:System.Uri> носителя можно указать непосредственно.  
  
- Воспроизведением мультимедиа можно управлять напрямую.  
  
- Свойства <xref:System.Windows.Controls.MediaElement.Position%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> мультимедиа можно изменить.  
  
 Носитель загружается либо путем установки свойства <xref:System.Windows.Controls.MediaElement.Source%2A> объекта <xref:System.Windows.Controls.MediaElement>, либо путем вызова метода <xref:System.Windows.Media.MediaPlayer.Open%2A> объекта <xref:System.Windows.Media.MediaPlayer>.  
  
 Для управления воспроизведением мультимедиа в независимом режиме можно использовать управляющие методы объекта мультимедиа. Доступные методы управления: <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>и <xref:System.Windows.Controls.MediaElement.Stop%2A>. Для <xref:System.Windows.Controls.MediaElement>интерактивное управление, использующее эти методы, доступно только в том случае, если для <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> задано значение <xref:System.Windows.Controls.MediaState.Manual>. Эти методы недоступны, если объект мультимедиа находится в режиме часов.  
  
 Пример использования независимого режима см. в разделе [Управление элементом MediaElement (воспроизведение, пауза, стоп, громкость и скорость)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Режим часов  
 В режиме часов <xref:System.Windows.Media.MediaTimeline> воспроизводит воспроизведение мультимедиа. Режим часов имеет следующие характеристики.  
  
- <xref:System.Uri> носителя косвенно устанавливается через <xref:System.Windows.Media.MediaTimeline>.  
  
- Воспроизведением мультимедиа можно управлять с помощью часов. Нельзя использовать управляющие методы объекта мультимедиа.  
  
- Носитель загружается путем установки свойства <xref:System.Windows.Media.MediaTimeline.Source%2A> объекта <xref:System.Windows.Media.MediaTimeline>, создания часов из временной шкалы и назначения часов объекту мультимедиа. Носитель также загружается таким образом, когда <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> нацелен на <xref:System.Windows.Controls.MediaElement>.  
  
 Для управления воспроизведением мультимедиа в режиме часов необходимо использовать методы управления <xref:System.Windows.Media.Animation.ClockController>. <xref:System.Windows.Media.Animation.ClockController> получается из свойства <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.MediaClock>. При попытке использовать управляющие методы либо объекта <xref:System.Windows.Controls.MediaElement> или <xref:System.Windows.Media.MediaPlayer> в режиме часов, будет создано исключение <xref:System.InvalidOperationException>.  
  
 Дополнительные сведения о часах и временных шкалах см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 Пример использования режима часов см. в разделе [Управление элементом MediaElement с помощью раскадровки](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>Класс MediaElement  
 Добавление мультимедиа в приложение — это просто добавление <xref:System.Windows.Controls.MediaElement> элемента управления в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] приложения и предоставление <xref:System.Uri> носителям, который вы хотите включить. В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]поддерживаются все типы носителей, поддерживаемые проигрывателем Microsoft Windows Media 10. В следующем примере показано простое использование <xref:System.Windows.Controls.MediaElement> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 В этом примере содержимое мультимедиа воспроизводится автоматически по мере его загрузки. После завершения воспроизведения содержимое мультимедиа закрывается, а все ресурсы мультимедиа освобождаются (включая видеопамять). Это поведение по умолчанию для объекта <xref:System.Windows.Controls.MediaElement> и управляется свойствами <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  
  
### <a name="controlling-a-mediaelement"></a>Управление объектом MediaElement  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> управляют поведением <xref:System.Windows.Controls.MediaElement>, когда <xref:System.Windows.FrameworkElement.IsLoaded%2A> — `true` или `false`соответственно. <xref:System.Windows.Controls.MediaState> свойства задаются для изменения поведения воспроизведения мультимедиа. Например, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> по умолчанию — <xref:System.Windows.Controls.MediaState.Play>, а <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> по умолчанию — <xref:System.Windows.Controls.MediaState.Close>. Это означает, что после загрузки <xref:System.Windows.Controls.MediaElement> и завершения предполной работы носитель начнет воспроизводиться. После завершения воспроизведения содержимое мультимедиа закрывается и освобождаются все ресурсы мультимедиа.  
  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> и <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> не являются единственным способом управления воспроизведением мультимедиа. В режиме часов часы могут управлять <xref:System.Windows.Controls.MediaElement>, а методы интерактивного управления — управлять тем, когда <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement> обрабатывает этот конкурс для контроля, оценивая следующие приоритеты.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> В случае, когда содержимое мультимедиа выгружается. Это гарантирует, что все ресурсы мультимедиа будут освобождены по умолчанию даже при сопоставлении <xref:System.Windows.Media.MediaClock> с <xref:System.Windows.Controls.MediaElement>.  
  
2. <xref:System.Windows.Media.MediaClock> На месте, когда на носителе имеется <xref:System.Windows.Controls.MediaElement.Clock%2A>. Если носитель выгружен, <xref:System.Windows.Media.MediaClock> вступят в силу, пока <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>. Режим часов всегда переопределяет загруженное поведение <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> В случае, когда содержимое мультимедиа загружается.  
  
4. Интерактивные управляющие методы. На месте, когда <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>. Доступные методы управления: <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>и <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Отображение объекта MediaElement  
 Чтобы отобразить <xref:System.Windows.Controls.MediaElement> он должен иметь содержимое для подготовки к просмотру, а его <xref:System.Windows.FrameworkElement.ActualWidth%2A> и свойства <xref:System.Windows.FrameworkElement.ActualHeight%2A> равны нулю, пока содержимое не будет загружено. Для содержимого, в составе которого есть только звук, эти свойства всегда имеют нулевое значение. Для видеосодержимого после того, как событие <xref:System.Windows.Controls.MediaElement.MediaOpened> вызвано <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> сообщит о размере загруженного носителя. Это означает, что до загрузки носителя <xref:System.Windows.Controls.MediaElement> не будет занимать никакого физического пространства в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], пока не будут заданы свойства <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A>.  
  
 Установка свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> приведет к переносу носителя для заполнения области, предоставленной для <xref:System.Windows.Controls.MediaElement>. Чтобы сохранить исходные пропорции носителя, необходимо задать либо свойство <xref:System.Windows.FrameworkElement.Width%2A>, либо <xref:System.Windows.FrameworkElement.Height%2A>, но не оба значения одновременно. Установка свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> приведет к тому, что носитель будет представлен фиксированным размером элемента, который может оказаться нежелательным.  
  
 Чтобы избежать отображения элемента фиксированного размера, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может сделать предварительную пробу содержимого мультимедиа. Это можно сделать, задав для <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> значение <xref:System.Windows.Controls.MediaState.Play> или <xref:System.Windows.Controls.MediaState.Pause>. В <xref:System.Windows.Controls.MediaState.Pause> состоянии носитель будет предварительно рулоном и будет представлять первый кадр. В <xref:System.Windows.Controls.MediaState.Play> состоянии носитель будет предварительно восстановлен и начнет воспроизводиться.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>Класс MediaPlayer  
 Если класс <xref:System.Windows.Controls.MediaElement> является элементом платформы, класс <xref:System.Windows.Media.MediaPlayer> предназначен для использования в <xref:System.Windows.Media.Drawing>ных объектах. Графические объекты используются, когда вы можете пожертвовать функциями уровня инфраструктуры, чтобы повысить производительность или когда вам нужны <xref:System.Windows.Freezable> функции. <xref:System.Windows.Media.MediaPlayer> позволяет использовать преимущества этих функций при предоставлении мультимедийного содержимого в приложениях. Как и <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> можно использовать в независимом или часовом режиме, но не содержит выгруженные и загруженные состояния объекта <xref:System.Windows.Controls.MediaElement>. Это сокращает сложность элемента управления воспроизведением <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Управление объектом MediaPlayer  
 Поскольку <xref:System.Windows.Media.MediaPlayer> не имеет состояния, существует два способа управления воспроизведением мультимедиа.  
  
1. Интерактивные управляющие методы. На месте в независимом режиме (`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A> свойство).  
  
2. <xref:System.Windows.Media.MediaClock> На месте, когда на носителе имеется <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Отображение объекта MediaPlayer  
 Технически <xref:System.Windows.Media.MediaPlayer> невозможно отобразить, так как она не имеет физического представления. Однако его можно использовать для представления носителя в <xref:System.Windows.Media.Drawing> с помощью класса <xref:System.Windows.Media.VideoDrawing>. В следующем примере демонстрируется использование <xref:System.Windows.Media.VideoDrawing> для вывода мультимедиа.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Дополнительные сведения об <xref:System.Windows.Media.Drawing>ных объектах см. в разделе "Общие сведения о [графических объектах](drawing-objects-overview.md) ".  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.DrawingGroup>
- [Макет](../advanced/layout.md)
- [Разделы практического руководства](audio-and-video-how-to-topics.md)
