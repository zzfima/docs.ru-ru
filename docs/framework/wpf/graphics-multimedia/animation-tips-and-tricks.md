---
title: "Советы и рекомендации по анимации | Microsoft Docs"
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
  - "анимированные объекты [WPF], устранение неполадок"
  - "советы и рекомендации по анимации [WPF]"
  - "анимация [WPF], FillBehavior - свойство"
  - "анимация [WPF], использование системных ресурсов"
  - "устранение неполадок производительности [WPF], анимация"
  - "советы и рекомендации [WPF], анимация"
  - "устранение неполадок [WPF], анимация"
  - "устранение неполадок анимации [WPF]"
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Советы и рекомендации по анимации
При работе с анимацией в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] некоторые советы и рекомендации помогут улучшить выполнение анимаций и избавят разработчика от разочарований.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="generalissuessection"></a>   
## Общие проблемы  
  
### Анимация расположения полосы прокрутки или ползунка замораживает их  
 При анимации расположения полосы прокрутки или ползунка с помощью анимации, имеющей <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior> \(значение по умолчанию\), пользователь больше не сможет перемещать полосу прокрутки или ползунок.  Это происходит потому, что несмотря на завершение анимации она по\-прежнему переопределяет базовое значение целевого свойства.  Чтобы прекратить переопределение анимацией текущего значения свойства, удалите его или присвойте ему значение <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior>.  Дополнительные сведения и пример см. в разделе [Установка свойства после его анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Анимация выходных данных анимации не дает эффекта  
 Невозможна анимация объекта, являющегося выходным для другой анимации.  Например, при использовании <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> для анимации <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> из <xref:System.Windows.Media.RadialGradientBrush> в <xref:System.Windows.Media.SolidColorBrush> невозможна анимация ни одного из свойств <xref:System.Windows.Media.RadialGradientBrush> или <xref:System.Windows.Media.SolidColorBrush>.  
  
### Невозможно изменить значение свойства после его анимации  
 В некоторых случаях нельзя изменить значение свойства после анимации, даже после того, как анимация завершена.  Это происходит потому, что несмотря на завершение анимации она по\-прежнему переопределяет базовое значение свойства.  Чтобы прекратить переопределение анимацией текущего значения свойства, удалите его или присвойте ему значение <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior>.  Дополнительные сведения и пример см. в разделе [Установка свойства после его анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Изменение временной шкалы не дает эффекта  
 Несмотря на то, что большинство свойств <xref:System.Windows.Media.Animation.Timeline> являются анимируемыми и могут быть привязаны к данным, изменение значений свойств активного <xref:System.Windows.Media.Animation.Timeline> не дает никакого эффекта.  Это происходит потому, что после начала <xref:System.Windows.Media.Animation.Timeline> система времени создает копию <xref:System.Windows.Media.Animation.Timeline> и использует ее для создания объекта <xref:System.Windows.Media.Animation.Clock>.  Изменение исходного объекта не влияет на копию системы.  
  
 Для того, чтобы <xref:System.Windows.Media.Animation.Timeline> мог отражать изменения, его часы должны быть повторно созданы и использованы для замены ранее созданных часов.  Автоматическое обновление часов не поддерживается.  Ниже приведены несколько способов применения изменений шкалы времени:  
  
-   Если шкала времени принадлежит <xref:System.Windows.Media.Animation.Storyboard>, можно заставить ее отражать изменения посредством применения ее раскадровки при помощи метода <xref:System.Windows.Media.Animation.BeginStoryboard> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  Это имеет побочный эффект в виде перезапуска анимации.  В коде можно использовать метод <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> для возврата раскадровки обратно в предыдущее положение.  
  
-   Если анимация применяется непосредственно к свойству с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>, снова вызовите метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> и передайте ему измененную анимацию.  
  
-   Если работа ведется непосредственно на уровне часов, создайте и примените новый набор часов и используйте их для замены предыдущего набора созданных часов.  
  
 Дополнительные сведения о шкалах времени и часах см. в разделе [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### FillBehavior.Stop не работает как ожидалось  
 Иногда присвоение свойству <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> значения <xref:System.Windows.Media.Animation.FillBehavior> не дает эффекта, например, когда одна анимация «передается» к другой, так как ее параметр <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> имеет значение <xref:System.Windows.Media.Animation.HandoffBehavior>.  
  
 В следующем примере создаются объекты <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Media.TranslateTransform>.  <xref:System.Windows.Media.TranslateTransform> будет анимирован для перемещения <xref:System.Windows.Shapes.Rectangle> вокруг <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Примеры в этом разделе используют определенные выше объекты для демонстрации нескольких случаев, в которых свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не действует так, как ожидалось.  
  
#### FillBehavior\="Stop" и HandoffBehavior с несколькими анимациями  
 Иногда кажется, что анимация игнорирует свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> при замене второй анимацией.  Рассмотрим следующий пример, в котором создается два объекта <xref:System.Windows.Media.Animation.Storyboard>, которые используются для анимации <xref:System.Windows.Media.TranslateTransform>, показанного в предыдущем примере.  
  
 Первый <xref:System.Windows.Media.Animation.Storyboard>, `B1`, анимирует свойство <xref:System.Windows.Media.TranslateTransform.X%2A> класса <xref:System.Windows.Media.TranslateTransform> от 0 до 350, которое перемещает прямоугольник на 350 пикселей вправо.  Когда анимация завершается и останавливает воспроизведение, свойство <xref:System.Windows.Media.TranslateTransform.X%2A> возвращается к исходному значению, равному 0.  В результате, прямоугольник перемещается вправо на 350 пикселей, а затем переходит обратно в исходное положение.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Второй <xref:System.Windows.Media.Animation.Storyboard>, `B2` также анимирует свойство <xref:System.Windows.Media.TranslateTransform.X%2A> того же <xref:System.Windows.Media.TranslateTransform>.  Так как установлено только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> анимации в этом <xref:System.Windows.Media.Animation.Storyboard>, анимация использует текущее значение анимируемого свойства в качестве начального значения.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 При нажатии второй кнопки во время воспроизведения первого <xref:System.Windows.Media.Animation.Storyboard>, можно ожидать следующее поведение:  
  
1.  Первая раскадровка заканчивается и отправляет прямоугольник обратно в исходное положение, поскольку анимация имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> в значении <xref:System.Windows.Media.Animation.FillBehavior>.  
  
2.  Вторая раскадровка вступает в действие и выполняет анимацию от текущего положения, которое сейчас равно 0, до положения 500.  
  
 **Но это не происходит.** Вместо этого, прямоугольник не возвращается обратно, а продолжает перемещаться вправо.  Это происходит потому, что вторая анимация использует текущее значение первой анимации в качестве начального значения и производит анимацию от этого значения до 500.  Когда вторая анимация заменяет первую из\-за использования <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior>, объект <xref:System.Windows.Media.Animation.FillBehavior> первой анимации не имеет значения.  
  
#### FillBehavior и завершенное событие  
 В следующем примере демонстрируется другой скрипт, в котором <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>, кажется, не дает эффекта.  В примере опять используется раскадровка для анимации свойства <xref:System.Windows.Media.TranslateTransform.X%2A> объекта <xref:System.Windows.Media.TranslateTransform> от 0 до 350.  Однако на этот раз в примере регистрируется событие <xref:System.Windows.Media.Animation.Timeline.Completed>.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Обработчик событий <xref:System.Windows.Media.Animation.Timeline.Completed> запускает другую <xref:System.Windows.Media.Animation.Storyboard>, которая анимирует то же свойство от его текущего значения до 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Ниже приведена разметка, определяющая вторую <xref:System.Windows.Media.Animation.Storyboard> в качестве ресурса.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 При запуске <xref:System.Windows.Media.Animation.Storyboard> ожидается, что свойство <xref:System.Windows.Media.TranslateTransform.X%2A> объекта <xref:System.Windows.Media.TranslateTransform> анимируется от 0 до 350, возвращается к значению 0 после завершения \(поскольку оно имеет значение <xref:System.Windows.Media.Animation.FillBehavior> функции <xref:System.Windows.Media.Animation.FillBehavior>\), а затем анимируется от 0 до 500.  Вместо этого <xref:System.Windows.Media.TranslateTransform> анимируется от 0 до 350, а затем до 500.  
  
 Это происходит из\-за последовательности, в которой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] вызывает события, а также из\-за того, что значения свойств кэшируются и не пересчитываются, если свойство является действительным.  Событие <xref:System.Windows.Media.Animation.Timeline.Completed> обрабатывается первым, так как оно было вызвано временной шкалой корня \(первая <xref:System.Windows.Media.Animation.Storyboard>\).  На этот раз свойство <xref:System.Windows.Media.TranslateTransform.X%2A> по\-прежнему возвращает анимированное значение, так как оно еще не было объявлено недействительным.  Вторая <xref:System.Windows.Media.Animation.Storyboard> использует кэшированное значение в качестве начального значения и начинает анимацию.  
  
<a name="performancesection"></a>   
## Производительность  
  
### Анимация продолжает выполняться после ухода со страницы  
 При покидании <xref:System.Windows.Controls.Page>, содержащей выполняющуюся анимацию, эти анимации будут продолжать воспроизведение до сборки мусора <xref:System.Windows.Controls.Page>.  В зависимости от используемой системы переходов страница, с которой вы ушли, может оставаться в памяти неограниченное количество времени, тем самым потребляя ресурсы анимацией.  Это наиболее заметно, если страница содержит постоянно выполняющиеся анимации \(«анимации окружения»\).  
  
 По этой причине целесообразно использовать событие <xref:System.Windows.FrameworkElement.Unloaded> для удаления анимации при покидании страницы.  
  
 Существуют различные способы удалить анимацию.  Следующие методы могут использоваться для удаления анимаций, которые принадлежат <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Чтобы удалить запущенную с помощью триггера событий <xref:System.Windows.Media.Animation.Storyboard>, обратитесь к разделу [How to: Remove a Storyboard](http://msdn.microsoft.com/ru-ru/7fe39531-de2f-46a0-a69f-b783d04235ee).  
  
-   Чтобы использовать код для удаления <xref:System.Windows.Media.Animation.Storyboard>, см. метод <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>.  
  
 Следующий метод может использоваться независимо от того, как была запущена анимация.  
  
-   Чтобы удалить анимацию из определенного свойства, используйте метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>.  Укажите анимируемое свойство в качестве первого параметра и `null` \- в качестве второго.  Это удалит все часы анимации из свойства.  
  
 Дополнительные сведения о различных способах анимации свойств см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### Использование составного HandoffBehavior потребляет системные ресурсы  
 При применении <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline> или <xref:System.Windows.Media.Animation.AnimationClock> к свойству с помощью <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior> любые объекты <xref:System.Windows.Media.Animation.Clock>, ранее связанные с этом свойством, продолжают потреблять системные ресурсы. Система времени не удаляет эти часы автоматически.  
  
 Чтобы избежать проблем с производительностью при применении большого количества часов с помощью <xref:System.Windows.Media.Animation.HandoffBehavior>, следует удалить созданные часы из свойства анимации после ее завершения.  Существует несколько способов удаления часов.  
  
-   Чтобы удалить все часы из свойства, воспользуйтесь методами <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> или <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> анимированного объекта.  Укажите анимируемое свойство в качестве первого параметра и `null` \- в качестве второго.  Это удалит все часы анимации из свойства.  
  
-   Для удаления определенных <xref:System.Windows.Media.Animation.AnimationClock> из списка часов используйте свойство <xref:System.Windows.Media.Animation.Clock.Controller%2A> объекта <xref:System.Windows.Media.Animation.AnimationClock>, чтобы получить <xref:System.Windows.Media.Animation.ClockController>, затем вызовите метод <xref:System.Windows.Media.Animation.ClockController.Remove%2A> объекта <xref:System.Windows.Media.Animation.ClockController>.  Обычно это выполняется в обработчике событий <xref:System.Windows.Media.Animation.Clock.Completed> для часов.  Обратите внимание, что только корневые часы могут управляться через <xref:System.Windows.Media.Animation.ClockController>; свойство <xref:System.Windows.Media.Animation.Clock.Controller%2A> дочерних часов вернет `null`.  Кроме того, обратите внимание, что событие <xref:System.Windows.Media.Animation.Clock.Completed> не будет вызвано, если эффективная продолжительность часов является бесконечностью.  В этом случае пользователю необходимо будет определить, когда вызвать <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 В основном, эта проблема анимации объектов, имеющих длинное время жизни.  Если объект уничтожается сборщиком мусора, его часы также будут отключены и собраны как мусор.  
  
 Дополнительные сведения об объектах часов см. в разделе [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)