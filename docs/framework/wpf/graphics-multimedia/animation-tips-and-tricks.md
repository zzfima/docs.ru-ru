---
title: Советы и рекомендации по анимации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: ef59631663e6cf1c98adfed77a2dbdb6ca124fa1
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636033"
---
# <a name="animation-tips-and-tricks"></a>Советы и рекомендации по анимации
При работе с анимациями в WPF существует ряд советов и рекомендаций, которые помогут сделать анимацию более эффективной и сэкономить на недовольство.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Общие проблемы  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Анимация расположения полосы прокрутки или ползунка замораживает их  
 Если анимировать положение полосы прокрутки или ползунка с помощью анимации, имеющей <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (значение по умолчанию), пользователь больше не сможет перемещать полосу прокрутки или ползунок. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение целевого свойства. Чтобы запретить анимации переопределять текущее значение свойства, удалите его или присвойте ему <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Дополнительные сведения и пример см. в разделе [Задание свойства после его анимации с помощью раскадровки](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Анимация выходных данных анимации ничего не делает  
 Невозможна анимация объекта, являющегося выходным объектом другой анимации. Например, при использовании <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> для анимации <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> из <xref:System.Windows.Media.RadialGradientBrush> в <xref:System.Windows.Media.SolidColorBrush>нельзя анимировать какие-либо свойства <xref:System.Windows.Media.RadialGradientBrush> или <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Невозможно изменить значение свойства после его анимации  
 В некоторых случаях может получиться так, что вы не сможете изменить значение свойства после его анимации, даже после завершения анимации. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение свойства. Чтобы запретить анимации переопределять текущее значение свойства, удалите его или присвойте ему <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Дополнительные сведения и пример см. в разделе [Задание свойства после его анимации с помощью раскадровки](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Изменение временной шкалы ничего не делает  
 Хотя большинство свойств <xref:System.Windows.Media.Animation.Timeline> являются анимированными и могут быть привязаны к данным, изменение значений свойств активной <xref:System.Windows.Media.Animation.Timeline> не оказывает никакого влияния. Это происходит потому, что при начале <xref:System.Windows.Media.Animation.Timeline> система времени создает копию <xref:System.Windows.Media.Animation.Timeline> и использует ее для создания объекта <xref:System.Windows.Media.Animation.Clock>. Изменение исходного объекта не влияет на сделанную системой копию.  
  
 Чтобы <xref:System.Windows.Media.Animation.Timeline> отражать изменения, его часы необходимо повторно создать и использовать для замены ранее созданных часов. Автоматическое обновление часов не поддерживается. Ниже показано несколько способов применения изменений временной шкалы.  
  
- Если временная шкала является или принадлежит <xref:System.Windows.Media.Animation.Storyboard>, можно сделать так, чтобы она отражала изменения путем повторного применения раскадровки с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> или метода <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>. Это имеет побочный эффект в виде перезапуска анимации. В коде можно использовать метод <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>, чтобы переместить раскадровку обратно в предыдущее расположение.  
  
- Если вы применили анимацию непосредственно к свойству с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>, вызовите метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> еще раз и передайте ему измененную анимацию.  
  
- При работе непосредственно на уровне часов создайте и примените новый набор часов и используйте его для замены предыдущего набора созданных часов.  
  
 Дополнительные сведения о временных шкалах и часах см. в разделе [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop не работает должным образом  
 Бывают случаи, когда установка свойства <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> в <xref:System.Windows.Media.Animation.FillBehavior.Stop> не оказывает никакого воздействия, например, когда одна анимация «передает» другой, так как она имеет значение <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 В следующем примере создается <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Media.TranslateTransform>. <xref:System.Windows.Media.TranslateTransform> будет анимирован для перемещения <xref:System.Windows.Shapes.Rectangle> вокруг <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Примеры в этом разделе используют приведенные выше объекты для демонстрации нескольких случаев, когда свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не работает так, как вы можете ожидать.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" и HandoffBehavior с несколькими анимациями  
 Иногда кажется, что анимация пропускает свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>, когда оно заменяется второй анимацией. Возьмем следующий пример, который создает два <xref:System.Windows.Media.Animation.Storyboard> объектов и использует их для анимации того же <xref:System.Windows.Media.TranslateTransform>, как показано в предыдущем примере.  
  
 Первый <xref:System.Windows.Media.Animation.Storyboard>, `B1`, анимирует свойство <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> от 0 до 350, перемещая прямоугольник 350 пикселей вправо. Когда анимация достигает окончания ее длительности и прекращает воспроизведение, свойство <xref:System.Windows.Media.TranslateTransform.X%2A> возвращается к исходному значению 0. В результате прямоугольник перемещается вправо на 350 пикселей, а затем перепрыгивает обратно в исходное положение.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Вторая <xref:System.Windows.Media.Animation.Storyboard>, `B2`, также анимирует свойство <xref:System.Windows.Media.TranslateTransform.X%2A> того же <xref:System.Windows.Media.TranslateTransform>. Так как задано только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> анимации в этой <xref:System.Windows.Media.Animation.Storyboard>, анимация использует текущее значение свойства, которое оно анимируется в качестве начального значения.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 При нажатии второй кнопки во время воспроизведения первого <xref:System.Windows.Media.Animation.Storyboard> может возникнуть следующее поведение:  
  
1. Первая раскадровка завершается и отправляет прямоугольник обратно в исходное расположение, поскольку анимация имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2. Вторая раскадровка вступает в силу и анимируется от текущей позиции, которая теперь имеет значение 0, до 500.  
  
 **Но этого не происходит.** Прямоугольник не прыгает обратно; он продолжает перемещаться вправо. Это происходит потому, что вторая анимация использует текущее значение первой анимации в качестве своего начального значения и анимируется от этого значения до 500. Когда вторая анимация заменяет первый из-за использования <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>, <xref:System.Windows.Media.Animation.FillBehavior> первой анимации не имеет значения.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior и завершенное событие  
 В следующих примерах демонстрируется другой сценарий, в котором <xref:System.Windows.Media.Animation.FillBehavior.Stop>, <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>, кажется, не оказывает никакого воздействия. Опять же, в примере используется раскадровка для анимации свойства <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> от 0 до 350. Однако на этот раз в примере регистрируется событие <xref:System.Windows.Media.Animation.Timeline.Completed>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Обработчик событий <xref:System.Windows.Media.Animation.Timeline.Completed> запускает еще одну <xref:System.Windows.Media.Animation.Storyboard>, которая анимирует то же свойство из текущего значения в 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Ниже приведена разметка, определяющая второй <xref:System.Windows.Media.Animation.Storyboard> как ресурс.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 При запуске <xref:System.Windows.Media.Animation.Storyboard>можно ожидать, что свойство <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> анимируется от 0 до 350, а затем вернуться к 0 после завершения (так как у него есть параметр <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop>), а затем выполнить анимацию от 0 до 500. Вместо этого <xref:System.Windows.Media.TranslateTransform> анимируется от 0 до 350, а затем до 500.  
  
 Это обусловлено порядком, в котором WPF создает события, а значения свойств кэшируются и не пересчитываются, если только свойство не является недействительным. Событие <xref:System.Windows.Media.Animation.Timeline.Completed> обрабатывается первым, так как оно было активировано корневой временной шкалой (первый <xref:System.Windows.Media.Animation.Storyboard>). В настоящее время свойство <xref:System.Windows.Media.TranslateTransform.X%2A> по-прежнему возвращает свое анимированное значение, так как оно еще не было аннулировано. Второй <xref:System.Windows.Media.Animation.Storyboard> использует кэшированное значение в качестве начального значения и начинает анимацию.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Производительность  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Анимация продолжает выполняться после ухода со страницы  
 При переходе от <xref:System.Windows.Controls.Page>, содержащего выполняющиеся анимации, эти анимации будут продолжать воспроизводиться до тех пор, пока <xref:System.Windows.Controls.Page> не будет собран сборщиком мусора. В зависимости от используемой системы навигации страница, с которой ушли, может оставаться в памяти неограниченное количество времени, постоянно потребляя ресурсы на анимацию. Это наиболее заметно, когда страница содержит постоянно выполняющиеся анимации ("фоновые").  
  
 По этой причине рекомендуется использовать событие <xref:System.Windows.FrameworkElement.Unloaded>, чтобы удалить анимацию при переходе с одной страницы на другую.  
  
 Анимацию можно удалить разными способами. Для удаления анимаций, принадлежащих <xref:System.Windows.Media.Animation.Storyboard>, можно использовать следующие методы.  
  
- Сведения об удалении <xref:System.Windows.Media.Animation.Storyboard>, запущенного с помощью триггера событий, см. в разделе [как удалить раскадровку](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Чтобы использовать код для удаления <xref:System.Windows.Media.Animation.Storyboard>, см. метод <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>.  
  
 Следующий метод может использоваться независимо от того, как была запущена анимация.  
  
- Чтобы удалить анимацию из определенного свойства, используйте метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>. Укажите свойство, анимированное в качестве первого параметра, а `null` в качестве второго. Это удалит из свойства все часы анимации.  
  
 Дополнительные сведения о различных способах анимации свойств см. в разделе [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Использование составного HandoffBehavior потребляет системные ресурсы  
 При применении <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>или <xref:System.Windows.Media.Animation.AnimationClock> к свойству с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose><xref:System.Windows.Media.Animation.HandoffBehavior>любые <xref:System.Windows.Media.Animation.Clock> объекты, ранее связанные с этим свойством, продолжают потреблять системные ресурсы. система времени не будет автоматически удалять эти часы.  
  
 Чтобы избежать проблем с производительностью при применении большого количества часов с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, следует удалить составные часы из анимированного свойства после их завершения. Есть несколько способов удаления часов.  
  
- Чтобы удалить все часы из свойства, используйте метод <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> или <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> анимированного объекта. Укажите свойство, анимированное в качестве первого параметра, а `null` в качестве второго. Это удалит из свойства все часы анимации.  
  
- Чтобы удалить определенное <xref:System.Windows.Media.Animation.AnimationClock> из списка часов, используйте свойство <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.Animation.AnimationClock> для получения <xref:System.Windows.Media.Animation.ClockController>, а затем вызовите метод <xref:System.Windows.Media.Animation.ClockController.Remove%2A> <xref:System.Windows.Media.Animation.ClockController>. Обычно это делается в обработчике событий <xref:System.Windows.Media.Animation.Clock.Completed> для часов. Обратите внимание, что <xref:System.Windows.Media.Animation.ClockController>может управлять только корневыми часами; Свойство <xref:System.Windows.Media.Animation.Clock.Controller%2A> дочернего объекта Clock будет возвращать `null`. Обратите внимание, что событие <xref:System.Windows.Media.Animation.Clock.Completed> не будет вызываться, если фактическая длительность часов бесконечно.  В этом случае пользователю нужно будет определить, когда следует вызывать <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 В основном это проблема для анимации объектов, имеющих длинное время жизни.  Когда объект собирается как мусор, его часы отсоединяются и также собираются как мусор.  
  
 Дополнительные сведения об объектах часов см. в разделе [Общие сведения о анимации и системе управления временем](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об анимации](animation-overview.md)
