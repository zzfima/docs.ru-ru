---
title: "Советы и рекомендации по анимации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca88d95f760e44b6cdc319923215151eff4bf762
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="animation-tips-and-tricks"></a>Советы и рекомендации по анимации
При работе с анимации в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], существует ряд советы и рекомендации помогут улучшить анимациями высокую производительность и сократить число трудностей.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Общие проблемы  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Анимация расположения полосы прокрутки или ползунка замораживает их  
 При анимации положение полосы прокрутки или ползунка с помощью анимации, которая имеет <xref:System.Windows.Media.Animation.FillBehavior> из <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (значение по умолчанию), пользователь больше не будут иметь возможность перемещать полосы прокрутки или ползунка. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение целевого свойства. Чтобы остановить анимацию переопределять значение текущего свойства, удалить его или присвоить ему <xref:System.Windows.Media.Animation.FillBehavior> из <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Дополнительные сведения и пример см. в разделе [задать свойства после анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Анимация выходных данных анимации ничего не делает  
 Невозможна анимация объекта, являющегося выходным объектом другой анимации. Например, если вы используете <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> для анимации <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle> из <xref:System.Windows.Media.RadialGradientBrush> для <xref:System.Windows.Media.SolidColorBrush>, не удается анимировать любые свойства <xref:System.Windows.Media.RadialGradientBrush> или <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Невозможно изменить значение свойства после его анимации  
 В некоторых случаях может получиться так, что вы не сможете изменить значение свойства после его анимации, даже после завершения анимации. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение свойства. Чтобы остановить анимацию переопределять значение текущего свойства, удалить его или присвоить ему <xref:System.Windows.Media.Animation.FillBehavior> из <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Дополнительные сведения и пример см. в разделе [задать свойства после анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Изменение временной шкалы ничего не делает  
 Несмотря на то что большинство <xref:System.Windows.Media.Animation.Timeline> свойства, анимации и могут быть привязаны к данным, изменение значений свойств активного <xref:System.Windows.Media.Animation.Timeline> не дает эффекта. Это потому, что, когда <xref:System.Windows.Media.Animation.Timeline> — начался, система времени создается копия <xref:System.Windows.Media.Animation.Timeline> и использует его для создания <xref:System.Windows.Media.Animation.Clock> объекта. Изменение исходного объекта не влияет на сделанную системой копию.  
  
 Для <xref:System.Windows.Media.Animation.Timeline> в соответствии с изменениями, необходимо заново и используемая для замены ранее созданных часов его часов. Автоматическое повторное создание часов не выполняется. Ниже показано несколько способов применения изменений временной шкалы.  
  
-   Если временная шкала или принадлежит <xref:System.Windows.Media.Animation.Storyboard>, чтобы облегчить отражать изменения посредством применения ее раскадровки при помощи <xref:System.Windows.Media.Animation.BeginStoryboard> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод. Это имеет побочный эффект в виде перезапуска анимации. В коде, можно использовать <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метода для возврата раскадровки обратно в предыдущее положение.  
  
-   Если анимация применяется непосредственно к свойству с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод, вызовите <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод еще раз и передать его анимации, которая была изменена.  
  
-   При работе непосредственно на уровне часов создайте и примените новый набор часов и используйте его для замены предыдущего набора созданных часов.  
  
 Дополнительные сведения о шкалах времени и часах см. в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop не работает должным образом  
 Иногда при задании <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства <xref:System.Windows.Media.Animation.FillBehavior.Stop> кажется, что не дает эффекта, например, когда одна анимация «передается» на другой, так как он имеет <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> параметра <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 В следующем примере создается <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Media.TranslateTransform>. <xref:System.Windows.Media.TranslateTransform> Будет анимации для перемещения <xref:System.Windows.Shapes.Rectangle> вокруг <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Примеры в этом разделе используют определенные выше объекты для демонстрации нескольких случаев где <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство не работает, как можно ожидать его.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" и HandoffBehavior с несколькими анимациями  
 Иногда кажется, что анимация игнорирует его <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство при замене второй анимацией. Рассмотрим следующий пример, который создает два <xref:System.Windows.Media.Animation.Storyboard> и использует их для анимации <xref:System.Windows.Media.TranslateTransform> показано в предыдущем примере.  
  
 Первый <xref:System.Windows.Media.Animation.Storyboard>, `B1`, анимирует <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> от 0 до 350, которое перемещает прямоугольник на 350 пикселей вправо. При анимации достигает конца своего срока и останавливает воспроизведение, <xref:System.Windows.Media.TranslateTransform.X%2A> свойство возвращается в свое исходное значение 0. В результате прямоугольник перемещается вправо на 350 пикселей, а затем перепрыгивает обратно в исходное положение.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Второй <xref:System.Windows.Media.Animation.Storyboard>, `B2`, также анимирует <xref:System.Windows.Media.TranslateTransform.X%2A> свойство одной и той же <xref:System.Windows.Media.TranslateTransform>. Так как только <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства анимации в этой <xref:System.Windows.Media.Animation.Storyboard> не установлен, анимация использует текущее значение анимируемого свойства в качестве начального значения.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Если щелкнуть второй кнопки во время первого <xref:System.Windows.Media.Animation.Storyboard> — воспроизведение, можно ожидать следующее поведение:  
  
1.  Первая раскадровка заканчивается и отправляет прямоугольник обратно в исходное положение, поскольку анимация имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> из <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2.  Вторая раскадровка вступает в силу и анимируется от текущей позиции, которая теперь имеет значение 0, до 500.  
  
 **Но этого не происходит.** Прямоугольник не прыгает обратно; он продолжает перемещаться вправо. Это происходит потому, что вторая анимация использует текущее значение первой анимации в качестве своего начального значения и анимируется от этого значения до 500. Когда вторая анимация заменяет первый, так как <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> используется, <xref:System.Windows.Media.Animation.FillBehavior> первого анимация не имеет значения.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior и завершенное событие  
 В следующем примере демонстрируется другой скрипт, в котором <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не дает эффекта. Опять же, в примере используется раскадровки для анимации <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> от 0 до 350. Тем не менее, это время в примере регистрируется для <xref:System.Windows.Media.Animation.Timeline.Completed> события.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed> Обработчик событий запускает другой <xref:System.Windows.Media.Animation.Storyboard> анимирования то же свойство с его текущим значением 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Ниже приведен разметка, определяющая второй <xref:System.Windows.Media.Animation.Storyboard> как ресурс.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 При запуске <xref:System.Windows.Media.Animation.Storyboard>, можно ожидать <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> анимируется от 0 до 350, возвращается к значению 0 после ее завершения (так как он содержит <xref:System.Windows.Media.Animation.FillBehavior> параметра <xref:System.Windows.Media.Animation.FillBehavior.Stop>) и затем анимируется от 0 до 500. Вместо этого <xref:System.Windows.Media.TranslateTransform> выполняет анимацию от 0 до 350, а затем — до 500.  
  
 Это порядок, в котором [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] вызывает события и потому, что значения свойств кэшируются и не пересчитываются, если свойство является действительным. <xref:System.Windows.Media.Animation.Timeline.Completed> Событие обрабатывается первым, так как оно было вызвано временной шкалой корня (первая <xref:System.Windows.Media.Animation.Storyboard>). В настоящее время <xref:System.Windows.Media.TranslateTransform.X%2A> свойство по-прежнему возвращает значению анимируемого, поскольку он еще не стали недействительными. Второй <xref:System.Windows.Media.Animation.Storyboard> использует кэшированное значение в качестве начального значения и начинает анимацию.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Производительность  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Анимация продолжает выполняться после ухода со страницы  
 При переходе от <xref:System.Windows.Controls.Page> , содержащей выполняющуюся анимацию, эти анимации будут продолжать воспроизведение до <xref:System.Windows.Controls.Page> выполняет сборку мусора. В зависимости от используемой системы навигации страница, с которой ушли, может оставаться в памяти неограниченное количество времени, постоянно потребляя ресурсы на анимацию. Это наиболее заметно, когда страница содержит постоянно выполняющиеся анимации ("фоновые").  
  
 По этой причине рекомендуется использовать <xref:System.Windows.FrameworkElement.Unloaded> событий для удаления анимации, когда вы уходите со страницы.  
  
 Анимацию можно удалить разными способами. Следующие методы можно использовать для удаления анимации, принадлежащих <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Чтобы удалить <xref:System.Windows.Media.Animation.Storyboard> запуска с помощью триггера событий см. в разделе [как: Удаление раскадровки](http://msdn.microsoft.com/en-us/7fe39531-de2f-46a0-a69f-b783d04235ee).  
  
-   Чтобы использовать код для удаления <xref:System.Windows.Media.Animation.Storyboard>, в разделе <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> метод.  
  
 Следующий метод может использоваться независимо от того, как была запущена анимация.  
  
-   Чтобы удалить анимацию из определенного свойства, используйте <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> метод. Укажите в качестве первого параметра, анимируемого свойства и `null` вторым. Это удалит из свойства все часы анимации.  
  
 Дополнительные сведения о различных способах анимации свойств см. в разделе [Общие сведения о методах анимации свойства](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Использование составного HandoffBehavior потребляет системные ресурсы  
 При применении <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, или <xref:System.Windows.Media.Animation.AnimationClock> к свойству с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, любые <xref:System.Windows.Media.Animation.Clock> ранее связанную с ним объекты по-прежнему потребление системных ресурсов; система времени не будет Удаляет эти часы автоматически.  
  
 Чтобы избежать проблем с производительностью при применении большое число часов с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, необходимо удалить составляющую часами анимированное свойство после их завершения. Есть несколько способов удаления часов.  
  
-   Чтобы удалить все часы из свойства, используйте <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> или <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> метод анимированного объекта. Укажите в качестве первого параметра, анимируемого свойства и `null` вторым. Это удалит из свойства все часы анимации.  
  
-   Для удаления определенных <xref:System.Windows.Media.Animation.AnimationClock> из списка часов используйте <xref:System.Windows.Media.Animation.Clock.Controller%2A> свойство <xref:System.Windows.Media.Animation.AnimationClock> для получения <xref:System.Windows.Media.Animation.ClockController>, затем вызовите <xref:System.Windows.Media.Animation.ClockController.Remove%2A> метод <xref:System.Windows.Media.Animation.ClockController>. Обычно это делается <xref:System.Windows.Media.Animation.Clock.Completed> обработчика событий для часов. Обратите внимание, что только корневые часы могут управляться <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> свойство дочерних часов вернет `null`. Обратите внимание, что <xref:System.Windows.Media.Animation.Clock.Completed> событие не будет вызвано, если эффективная продолжительность часов является бесконечностью.  В этом случае пользователю будет необходимо определить, когда вызывать <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 В основном это проблема для анимации объектов, имеющих длинное время жизни.  Когда объект собирается как мусор, его часы отсоединяются и также собираются как мусор.  
  
 Дополнительные сведения об объектах часов см. в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
