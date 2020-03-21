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
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187651"
---
# <a name="animation-tips-and-tricks"></a>Советы и рекомендации по анимации
При работе с анимацией в WPF, Есть ряд советов и приемов, которые могут сделать ваши анимации работать лучше и сэкономить разочарование.  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>Общие проблемы  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Анимация расположения полосы прокрутки или ползунка замораживает их  
 Если вы оживляете положение панели прокрутки или <xref:System.Windows.Media.Animation.FillBehavior> ползунка с помощью анимации, <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> которая имеет значение по умолчанию), пользователь больше не сможет перемещать бар прокрутки или ползунок. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение целевого свойства. Чтобы остановить анимацию от переопределения текущего значения свойства, удалите его, или дать ему <xref:System.Windows.Media.Animation.FillBehavior> . <xref:System.Windows.Media.Animation.FillBehavior.Stop> Для получения дополнительной информации и примера [см.](how-to-set-a-property-after-animating-it-with-a-storyboard.md)  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Анимация выходных данных анимации ничего не делает  
 Невозможна анимация объекта, являющегося выходным объектом другой анимации. Например, если вы <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> используете для <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> анимировать <xref:System.Windows.Media.RadialGradientBrush> от <xref:System.Windows.Media.SolidColorBrush>до, вы не можете оживить <xref:System.Windows.Media.RadialGradientBrush> любые свойства или <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Невозможно изменить значение свойства после его анимации  
 В некоторых случаях может получиться так, что вы не сможете изменить значение свойства после его анимации, даже после завершения анимации. Это происходит из-за того, что, хотя анимация завершена, она по-прежнему переопределяет базовое значение свойства. Чтобы остановить анимацию от переопределения текущего значения свойства, удалите его, или дать ему <xref:System.Windows.Media.Animation.FillBehavior> . <xref:System.Windows.Media.Animation.FillBehavior.Stop> Для получения дополнительной информации и примера [см.](how-to-set-a-property-after-animating-it-with-a-storyboard.md)  
  
### <a name="changing-a-timeline-has-no-effect"></a>Изменение временной шкалы ничего не делает  
 Хотя <xref:System.Windows.Media.Animation.Timeline> большинство свойств являются анимативными и могут быть связаны данными, изменение значений свойств активного, <xref:System.Windows.Media.Animation.Timeline> кажется, не имеет никакого эффекта. Это потому, что, когда система <xref:System.Windows.Media.Animation.Timeline> синхронизации начинается, система синхронизации делает копию <xref:System.Windows.Media.Animation.Timeline> и использует его для создания <xref:System.Windows.Media.Animation.Clock> объекта. Изменение исходного объекта не влияет на сделанную системой копию.  
  
 Для <xref:System.Windows.Media.Animation.Timeline> отражения изменений его часы должны быть регенерированы и использованы для замены ранее созданных часов. Автоматическое обновление часов не поддерживается. Ниже показано несколько способов применения изменений временной шкалы.  
  
- Если шкала времени принадлежит или <xref:System.Windows.Media.Animation.Storyboard>принадлежит, вы можете заставить ее отражать изменения, повторно применяя свою раскадровку с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> или метода. <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Это имеет побочный эффект в виде перезапуска анимации. В коде <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> можно использовать метод для продвижения раскадровки к прежней позиции.  
  
- Если с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода анимация была <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> применена непосредственно к свойству, позвоните по методу и передайте его измененной анимации.  
  
- При работе непосредственно на уровне часов создайте и примените новый набор часов и используйте его для замены предыдущего набора созданных часов.  
  
 Для получения дополнительной информации о сроках и часах, см [Анимация и синхронизация системы Обзор](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop не работает должным образом  
 Есть моменты, <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> когда <xref:System.Windows.Media.Animation.FillBehavior.Stop> установка свойства, кажется, не имеют никакого эффекта, например, когда одна анимация "руки прочь" к другому, потому что она имеет <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> параметр <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 Следующий пример <xref:System.Windows.Controls.Canvas>создает <xref:System.Windows.Shapes.Rectangle> , <xref:System.Windows.Media.TranslateTransform>a и a . Будет <xref:System.Windows.Media.TranslateTransform> анимирован, <xref:System.Windows.Shapes.Rectangle> чтобы <xref:System.Windows.Controls.Canvas>переместить вокруг .  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Примеры в этом разделе используют предыдущие объекты <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для демонстрации нескольких случаев, когда свойство ведет себя не так, как вы могли бы ожидать.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" и HandoffBehavior с несколькими анимациями  
 Иногда кажется, что анимация <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> игнорирует свое свойство, когда она заменяется второй анимацией. Возьмем следующий пример, <xref:System.Windows.Media.Animation.Storyboard> который создает два объекта и <xref:System.Windows.Media.TranslateTransform> использует их для анимировать то же самое показано в предыдущем примере.  
  
 Первый <xref:System.Windows.Media.Animation.Storyboard> `B1`, , оживляет <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> свойство от 0 до 350, который перемещает прямоугольник 350 пикселей вправо. Когда анимация достигает конца своей продолжительности <xref:System.Windows.Media.TranslateTransform.X%2A> и перестает играть, свойство возвращается к исходной стоимости, 0. В результате прямоугольник перемещается вправо на 350 пикселей, а затем перепрыгивает обратно в исходное положение.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Второй <xref:System.Windows.Media.Animation.Storyboard>, `B2`, также оживляет <xref:System.Windows.Media.TranslateTransform.X%2A> имущество <xref:System.Windows.Media.TranslateTransform>же . Поскольку <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> только свойство анимации в этом <xref:System.Windows.Media.Animation.Storyboard> набор, анимация использует текущее значение свойства он оживляет в качестве исходного значения.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Если вы нажмете <xref:System.Windows.Media.Animation.Storyboard> вторую кнопку во время игры первой, можно ожидать следующего поведения:  
  
1. Первый раскадровка заканчивается и отправляет прямоугольник обратно в исходное положение, потому что анимация имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> . <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
2. Вторая раскадровка вступает в силу и анимируется от текущей позиции, которая теперь имеет значение 0, до 500.  
  
 **Но этого не происходит.** Прямоугольник не прыгает обратно; он продолжает перемещаться вправо. Это происходит потому, что вторая анимация использует текущее значение первой анимации в качестве своего начального значения и анимируется от этого значения до 500. Когда вторая анимация заменяет <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> первую, <xref:System.Windows.Media.Animation.FillBehavior> потому что используется, первая анимация не имеет значения.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior и завершенное событие  
 Следующие примеры демонстрируют другой <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> сценарий, в котором, как представляется, не имеют никакого эффекта. Опять же, пример использует раскадровку <xref:System.Windows.Media.TranslateTransform.X%2A> для <xref:System.Windows.Media.TranslateTransform> анимировать свойство от 0 до 350. Однако на этот раз пример <xref:System.Windows.Media.Animation.Timeline.Completed> регистрируется для события.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Обработчик <xref:System.Windows.Media.Animation.Timeline.Completed> событий <xref:System.Windows.Media.Animation.Storyboard> запускает другой, который оживляет то же свойство от его текущего значения до 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Ниже приводится разметка, которая <xref:System.Windows.Media.Animation.Storyboard> определяет второй ресурс.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>При запуске, вы можете <xref:System.Windows.Media.TranslateTransform.X%2A> ожидать <xref:System.Windows.Media.TranslateTransform> свойство анимировать от 0 до 350, а затем вернуться <xref:System.Windows.Media.Animation.FillBehavior> к <xref:System.Windows.Media.Animation.FillBehavior.Stop>0 после его завершения (потому что он имеет параметр), а затем анимировать от 0 до 500. Вместо этого, <xref:System.Windows.Media.TranslateTransform> оживляет от 0 до 350, а затем до 500.  
  
 Это связано с порядком, в котором WPF поднимает события, и потому, что значения свойств кэшируются и не пересчитываются, если свойство не является недействительным. Событие <xref:System.Windows.Media.Animation.Timeline.Completed> обрабатывается сначала, потому что оно было вызвано корневой временной шкалой (первый). <xref:System.Windows.Media.Animation.Storyboard> В настоящее <xref:System.Windows.Media.TranslateTransform.X%2A> время, свойство по-прежнему возвращает свою анимированную ценность, потому что он не был признан недействительным еще. Второй <xref:System.Windows.Media.Animation.Storyboard> использует кэшированное значение в качестве исходного значения и начинает анимировать.  
  
<a name="performancesection"></a>
## <a name="performance"></a>Производительность  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Анимация продолжает выполняться после ухода со страницы  
 При переходе от <xref:System.Windows.Controls.Page> а, содержащего запущенные анимации, <xref:System.Windows.Controls.Page> эти анимации будут продолжать воспроизводиться до тех пор, пока не будет собран мусор. В зависимости от используемой системы навигации страница, с которой ушли, может оставаться в памяти неограниченное количество времени, постоянно потребляя ресурсы на анимацию. Это наиболее заметно, когда страница содержит постоянно выполняющиеся анимации ("фоновые").  
  
 По этой причине рекомендуется использовать <xref:System.Windows.FrameworkElement.Unloaded> событие для удаления анимации при переходе со страницы.  
  
 Анимацию можно удалить разными способами. Следующие методы могут быть использованы для <xref:System.Windows.Media.Animation.Storyboard>удаления анимации, которые принадлежат к .  
  
- Чтобы удалить <xref:System.Windows.Media.Animation.Storyboard> запуск события, см. [Как: Удалить раскадровку.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90))  
  
- Чтобы использовать код <xref:System.Windows.Media.Animation.Storyboard>для удаления, см. <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Следующий метод может использоваться независимо от того, как была запущена анимация.  
  
- Чтобы удалить анимацию из определенного <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> свойства, используйте метод. Укажите свойство, анимированное `null` в качестве первого параметра, и как второй. Это удалит из свойства все часы анимации.  
  
 Для получения дополнительной информации о различных способах анимации свойств, [см.](property-animation-techniques-overview.md)  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Использование составного HandoffBehavior потребляет системные ресурсы  
 При <xref:System.Windows.Media.Animation.Storyboard>применении, <xref:System.Windows.Media.Animation.AnimationTimeline>или <xref:System.Windows.Media.Animation.AnimationClock> к <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>свойству, <xref:System.Windows.Media.Animation.Clock> используюему, любые объекты, ранее связанные с этим свойством, продолжают потреблять ресурсы системы; система синхронизации не будет удалять эти часы автоматически.  
  
 Чтобы избежать проблем с производительностью при использовании <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>большого количества часов, следует удалить сочинение часов из анимированного свойства после их завершения. Есть несколько способов удаления часов.  
  
- Чтобы удалить все часы из <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> свойства, используйте или <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> метод анимированного объекта. Укажите свойство, анимированное `null` в качестве первого параметра, и как второй. Это удалит из свойства все часы анимации.  
  
- Чтобы удалить <xref:System.Windows.Media.Animation.AnimationClock> конкретный из списка часов, <xref:System.Windows.Media.Animation.Clock.Controller%2A> используйте <xref:System.Windows.Media.Animation.AnimationClock> свойство <xref:System.Windows.Media.Animation.ClockController>для получения, <xref:System.Windows.Media.Animation.ClockController.Remove%2A> а <xref:System.Windows.Media.Animation.ClockController>затем позвонить метод . Обычно это делается <xref:System.Windows.Media.Animation.Clock.Completed> в обработчике событий для часов. Обратите внимание, что только корневые часы могут управляться <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> имущество ребенка часы `null`вернутся . Отметим также, что <xref:System.Windows.Media.Animation.Clock.Completed> событие не будет называться, если эффективная продолжительность часов является вечной.  В этом случае пользователю необходимо определить, <xref:System.Windows.Media.Animation.ClockController.Remove%2A>когда звонить.  
  
 В основном это проблема для анимации объектов, имеющих длинное время жизни.  Когда объект собирается как мусор, его часы отсоединяются и также собираются как мусор.  
  
 Для получения дополнительной информации об объектах часов, см [Анимация и синхронизация системы Обзор](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
