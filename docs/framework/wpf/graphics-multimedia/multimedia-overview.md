---
title: Общие сведения о мультимедиа
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181885"
---
# <a name="multimedia-overview"></a>Общие сведения о мультимедиа
Мультимедийные возможности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют интегрировать аудио и видео в приложения для расширения возможностей пользователя. В этом разделе представлены мультимедийные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="mediaapi"></a>
## <a name="media-api"></a>API мультимедиа  
 <xref:System.Windows.Media.MediaPlayer> Классы <xref:System.Windows.Controls.MediaElement> используются для представления аудио- или видеоконтента. Этими классами можно управлять в интерактивном режиме или с помощью часов. Эти классы могут использоваться на элементе управления Microsoft Windows Media Player 10 для воспроизведения мультимедиа. Выбор класса зависит от сценария.  
  
 <xref:System.Windows.Controls.MediaElement>является <xref:System.Windows.UIElement> то, что поддерживается [layout](../advanced/layout.md) и может быть использован в качестве содержимого многих элементов управления. Его можно также использовать в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] наряду с программным кодом. <xref:System.Windows.Media.MediaPlayer>, с другой стороны, <xref:System.Windows.Media.Drawing> предназначен для объектов и не хватает поддержки макета. Средства массовой <xref:System.Windows.Media.MediaPlayer> информации, загруженные <xref:System.Windows.Media.VideoDrawing> с помощью a, могут быть представлены только с помощью или путем прямого взаимодействия с <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer>не могут быть использованы в XAML.  
  
 Дополнительные сведения о графических объектах и контексте рисования см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).  
  
> [!NOTE]
> При распространении мультимедиа вместе с приложением файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>Режимы воспроизведения мультимедиа  
  
> [!NOTE]
> Оба <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> и имеют аналогичных членов. Ссылки в этом разделе <xref:System.Windows.Controls.MediaElement> относятся к членам класса. Если конкретно не указано, <xref:System.Windows.Controls.MediaElement> члены, связанные <xref:System.Windows.Media.MediaPlayer> с в классе также могут быть найдены в классе.  
  
 Чтобы понимать принципы воспроизведения мультимедиа в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], необходимо знание о различных режимах, в которых может воспроизводиться содержимое мультимедиа. Оба <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> и могут быть использованы в двух различных медиа-режимах, независимом режиме и режиме часов. Режим мультимедиа определяется <xref:System.Windows.Controls.MediaElement.Clock%2A> свойством. Когда <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`это, медиа-объект находится в независимом режиме. Когда <xref:System.Windows.Controls.MediaElement.Clock%2A> объект мультимедиа не является нулевым, он находится в часовом режиме. По умолчанию объекты мультимедиа находятся в независимом режиме.  
  
### <a name="independent-mode"></a>Независимый режим  
 В независимом режиме содержимое мультимедиа управляет своим воспроизведением. Независимый режим имеет следующие параметры.  
  
- Средства массовой информации <xref:System.Uri> могут быть непосредственно указаны.  
  
- Воспроизведением мультимедиа можно управлять напрямую.  
  
- Средства массовой информации <xref:System.Windows.Controls.MediaElement.Position%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> свойства могут быть изменены.  
  
 Медиа загружаются либо <xref:System.Windows.Controls.MediaElement> путем <xref:System.Windows.Controls.MediaElement.Source%2A> настройки свойства <xref:System.Windows.Media.MediaPlayer> объекта, <xref:System.Windows.Media.MediaPlayer.Open%2A> либо путем вызова метода объекта.  
  
 Для управления воспроизведением мультимедиа в независимом режиме можно использовать управляющие методы объекта мультимедиа. Доступны методы <xref:System.Windows.Controls.MediaElement.Play%2A>управления: <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>и <xref:System.Windows.Controls.MediaElement.Stop%2A>. Для, <xref:System.Windows.Controls.MediaElement>интерактивный контроль с помощью <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> этих методов доступен только тогда, когда установлен на <xref:System.Windows.Controls.MediaState.Manual>. Эти методы недоступны, если объект мультимедиа находится в режиме часов.  
  
 Пример использования независимого режима см. в разделе [Управление элементом MediaElement (воспроизведение, пауза, стоп, громкость и скорость)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Режим часов  
 В режиме <xref:System.Windows.Media.MediaTimeline> часов воспроизведение мультимедиа приводит к воспроизведению мультимедиа. Режим часов имеет следующие характеристики.  
  
- Средства массовой информации <xref:System.Uri> косвенно <xref:System.Windows.Media.MediaTimeline>устанавливается через .  
  
- Воспроизведением мультимедиа можно управлять с помощью часов. Нельзя использовать управляющие методы объекта мультимедиа.  
  
- Медиа загружается <xref:System.Windows.Media.MediaTimeline> путем <xref:System.Windows.Media.MediaTimeline.Source%2A> установки свойства объекта, создания часов из временной шкалы и присвоения часов объекту мультимедиа. Медиа также загружается <xref:System.Windows.Media.MediaTimeline> таким <xref:System.Windows.Media.Animation.Storyboard> образом, <xref:System.Windows.Controls.MediaElement>когда внутри цели .  
  
 Для управления воспроизведением мультимедиа <xref:System.Windows.Media.Animation.ClockController> в часовом режиме необходимо использовать методы управления. A <xref:System.Windows.Media.Animation.ClockController> получен из <xref:System.Windows.Media.Animation.ClockController> собственности <xref:System.Windows.Media.MediaClock>. Если вы попытаетесь использовать методы <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> управления либо объекта или <xref:System.InvalidOperationException> объекта в то время как в режиме часы, будет брошен.  
  
 Дополнительные сведения о часах и временных шкалах см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 Пример использования режима часов см. в разделе [Управление элементом MediaElement с помощью раскадровки](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>Класс MediaElement  
 Добавление носителя в приложение так же <xref:System.Windows.Controls.MediaElement> просто, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] как добавление элемента управления в приложение и предоставление <xref:System.Uri> средств массовой информации, которые вы хотите включить. Все типы мультимедиа, поддерживаемые Microsoft [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Windows Media Player 10, поддерживаются в. Следующий пример показывает простое <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]использование дюйма .  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 В этом примере содержимое мультимедиа воспроизводится автоматически по мере его загрузки. После завершения воспроизведения содержимое мультимедиа закрывается, а все ресурсы мультимедиа освобождаются (включая видеопамять). Это поведение <xref:System.Windows.Controls.MediaElement> объекта по умолчанию и <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> контролируется <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> и свойствами.  
  
### <a name="controlling-a-mediaelement"></a>Управление объектом MediaElement  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> и свойства контролируют <xref:System.Windows.Controls.MediaElement> поведение, `true` `false`когда <xref:System.Windows.FrameworkElement.IsLoaded%2A> есть или, соответственно. Свойства <xref:System.Windows.Controls.MediaState> влияют на поведение воспроизведения мультимедиа. Например, по <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play> умолчанию <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> и <xref:System.Windows.Controls.MediaState.Close>по умолчанию . Это означает, что <xref:System.Windows.Controls.MediaElement> как только загружается и преролл завершен, средства массовой информации начинают играть. После завершения воспроизведения содержимое мультимедиа закрывается и освобождаются все ресурсы мультимедиа.  
  
 Свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> и свойства не являются единственным способом управления воспроизведением мультимедиа. В режиме часов, часы могут контролировать <xref:System.Windows.Controls.MediaElement> и интерактивные <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>методы управления имеют контроль, когда находится . <xref:System.Windows.Controls.MediaElement>обрабатывает этот конкурс для управления путем оценивать следующие приоритеты.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. В случае, когда содержимое мультимедиа выгружается. Это гарантирует, что все медиа-ресурсы будут <xref:System.Windows.Media.MediaClock> выпущены <xref:System.Windows.Controls.MediaElement>по умолчанию, даже если а. связан с .  
  
2. <xref:System.Windows.Media.MediaClock>. На месте, когда <xref:System.Windows.Controls.MediaElement.Clock%2A>средства массовой информации имеет . Если носители выгружаются, то они вступят в <xref:System.Windows.Media.MediaClock> силу до тех пор, пока <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> это <xref:System.Windows.Controls.MediaState.Manual>. Режим часов всегда перекрывает загруженное <xref:System.Windows.Controls.MediaElement>поведение .  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. В случае, когда содержимое мультимедиа загружается.  
  
4. Интерактивные управляющие методы. На месте, когда <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> это <xref:System.Windows.Controls.MediaState.Manual>. Доступны методы <xref:System.Windows.Controls.MediaElement.Play%2A>управления: <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>и <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Отображение объекта MediaElement  
 Для отображения <xref:System.Windows.Controls.MediaElement> он должен иметь <xref:System.Windows.FrameworkElement.ActualWidth%2A> содержимое для визуализации, и он будет иметь его и <xref:System.Windows.FrameworkElement.ActualHeight%2A> свойства установлены до нуля, пока содержимое загружено. Для содержимого, в составе которого есть только звук, эти свойства всегда имеют нулевое значение. Для видеоконтента, <xref:System.Windows.Controls.MediaElement.MediaOpened> как только <xref:System.Windows.FrameworkElement.ActualWidth%2A> событие <xref:System.Windows.FrameworkElement.ActualHeight%2A> было поднято и сообщит о размере загруженных носителей. Это означает, что до загрузки носителя <xref:System.Windows.Controls.MediaElement> не будет займено какое-либо физическое пространство в том случае, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] если <xref:System.Windows.FrameworkElement.Width%2A> не установлены или <xref:System.Windows.FrameworkElement.Height%2A> свойства.  
  
 Установка как <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> и свойства приведет к средствам растянуть, <xref:System.Windows.Controls.MediaElement>чтобы заполнить область, предусмотренную для . Чтобы сохранить исходное соотношение сторон <xref:System.Windows.FrameworkElement.Width%2A> средств <xref:System.Windows.FrameworkElement.Height%2A> массовой информации, либо или свойство должно быть установлено, но не оба. Установка как <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> свойств, так и свойств приведет к тому, что носители будут представлены в фиксированном размере элемента, который может оказаться нежелательным.  
  
 Чтобы избежать отображения элемента фиксированного размера, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может сделать предварительную пробу содержимого мультимедиа. Это делается путем <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play> установки либо или <xref:System.Windows.Controls.MediaState.Pause>. В <xref:System.Windows.Controls.MediaState.Pause> состоянии, средства массовой информации будет preroll и представит первый кадр. В <xref:System.Windows.Controls.MediaState.Play> государстве, средства массовой информации будет preroll и начать играть.  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>Класс MediaPlayer  
 Если <xref:System.Windows.Controls.MediaElement> класс является элементом фреймворка, <xref:System.Windows.Media.MediaPlayer> класс <xref:System.Windows.Media.Drawing> предназначен для использования в объектах. Объекты рисования используются, когда можно пожертвовать функциями <xref:System.Windows.Freezable> уровня фреймворка, чтобы получить преимущества в производительности или когда вам нужны функции. <xref:System.Windows.Media.MediaPlayer>позволяет использовать эти функции, предоставляя медиа-контент в приложениях. Как <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> , может быть использован в независимом <xref:System.Windows.Controls.MediaElement> или тактовом режиме, но не имеет объекта выгружены и загружены состояния. Это снижает сложность управления воспроизведением. <xref:System.Windows.Media.MediaPlayer>  
  
### <a name="controlling-mediaplayer"></a>Управление объектом MediaPlayer  
 Поскольку <xref:System.Windows.Media.MediaPlayer> он является апосредонером, существует только два способа управления воспроизведением мультимедиа.  
  
1. Интерактивные управляющие методы. На месте, когда`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> в независимом режиме (собственность).  
  
2. <xref:System.Windows.Media.MediaClock>. На месте, когда <xref:System.Windows.Media.MediaPlayer.Clock%2A>средства массовой информации имеет .  
  
### <a name="displaying-a-mediaplayer"></a>Отображение объекта MediaPlayer  
 Технически, не <xref:System.Windows.Media.MediaPlayer> может быть отображено, так как он не имеет физического представления. Тем не менее, он может <xref:System.Windows.Media.Drawing> быть <xref:System.Windows.Media.VideoDrawing> использован для представления средств массовой информации в использовании класса. Следующий пример демонстрирует использование <xref:System.Windows.Media.VideoDrawing> носителя для отображения.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Дополнительную информацию об <xref:System.Windows.Media.Drawing> объектах можно узнать в [обзоре объектов рисования.](drawing-objects-overview.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.DrawingGroup>
- [Макет](../advanced/layout.md)
- [Как-к темам](audio-and-video-how-to-topics.md)
