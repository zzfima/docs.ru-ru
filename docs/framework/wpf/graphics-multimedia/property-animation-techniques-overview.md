---
title: "Общие сведения о методах анимации свойств | Microsoft Docs"
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
  - "анимация, свойства, методы для"
  - "свойства, методы для анимации"
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о методах анимации свойств
В данном разделе описываются различные подходы к анимации свойств: раскадровки, локальные анимации, часы и покадровая анимация.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо ознакомиться с базовыми средствами анимации, описанными в [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="summary"></a>   
## Различные способы анимации  
 Поскольку существует множество различных скриптов для анимации свойств, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько подходов к анимации свойств.  
  
 В следующей таблице показывает для каждого подхода, можно ли использовать его с каждым экземпляром, в стилях, шаблонах элементов управления или шаблонах данных; может ли он использоваться в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и позволяет ли подход интерактивно управлять анимацией.  "Для каждого экземпляра" относится к способу применения анимации или раскадровки непосредственно к экземплярам объекта, а не к стилю, шаблону элемента управления или шаблону данных.  
  
|Метод анимации|Сценарии|Поддерживает XAML|Интерактивно управляемый|  
|--------------------|--------------|-----------------------|------------------------------|  
|Анимация с помощью Storyboard|"Для каждого экземпляра", <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Да|Да|  
|Локальная анимация|"Для каждого экземпляра"|Нет|Нет|  
|Анимация часов|"Для каждого экземпляра"|Нет|Да|  
|Покадровая анимация|"Для каждого экземпляра"|Нет|Неприменимо|  
  
<a name="storyboard_animations"></a>   
## Анимации с помощью Storyboard  
 Используйте <xref:System.Windows.Media.Animation.Storyboard>, если требуется определить и применить анимацию в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], управлять анимациями в интерактивном режиме после запуска, создать сложные деревья анимаций или создать анимации в <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> или <xref:System.Windows.DataTemplate>.  Объект, анимируемый с помощью <xref:System.Windows.Media.Animation.Storyboard>, должен быть <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, или он должен использоваться для задания <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  Дополнительные сведения см. в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 <xref:System.Windows.Media.Animation.Storyboard> представляет собой особый тип контейнера <xref:System.Windows.Media.Animation.Timeline>, предоставляющий сведения о содержащихся в нем анимациях.  Для анимации с помощью <xref:System.Windows.Media.Animation.Storyboard> необходимо выполнить следующие три действия.  
  
1.  Объявите <xref:System.Windows.Media.Animation.Storyboard> и одну или несколько анимаций.  
  
2.  Используйте [вложенные свойства](GTMT) <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> для указания конечного объекта и свойства каждой анимации.  
  
3.  \(Только код\) Определите <xref:System.Windows.NameScope> элемента <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  Зарегистрируйте имена объектов анимации с помощью <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  
  
4.  Запустите <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Запуск <xref:System.Windows.Media.Animation.Storyboard> применяет анимации к анимируемым свойствам и запускает их.  Существует два способа запуска <xref:System.Windows.Media.Animation.Storyboard>: можно использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>, предоставленный классом <xref:System.Windows.Media.Animation.Storyboard>, или использовать действие <xref:System.Windows.Media.Animation.BeginStoryboard>.  Единственным способом анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является использование действия <xref:System.Windows.Media.Animation.BeginStoryboard>. Действие <xref:System.Windows.Media.Animation.BeginStoryboard> можно использовать в триггере <xref:System.Windows.EventTrigger>, триггере <xref:System.Windows.Trigger> свойства или в триггере <xref:System.Windows.DataTrigger>.  
  
 В следующей таблице приведены различные способы запуска <xref:System.Windows.Media.Animation.Storyboard>: для каждого экземпляра, стиля, шаблона элемента управления и шаблона данных.  
  
|Запуск раскадровки при помощи…|"Для каждого экземпляра"|Стиль|Шаблон элемента управления|Шаблон данных|Пример|  
|------------------------------------|------------------------------|-----------|--------------------------------|-------------------|------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и свойство <xref:System.Windows.Trigger>|Нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.DataTrigger>|Нет|Да|Да|Да|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/ru-ru/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|Нет|Нет|Нет|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Animation.Storyboard> содержатся в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## Локальные анимации  
 Локальные анимации предоставляют удобный способ анимации [свойства зависимостей](GTMT) любого объекта <xref:System.Windows.Media.Animation.Animatable>.  Используйте локальную анимацию, когда необходимо применить одну анимацию к свойству и нет необходимости в управлении анимацией в интерактивном режиме после запуска.  В отличие от анимации <xref:System.Windows.Media.Animation.Storyboard> локальная анимации может анимировать объект, не связанный с <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  Кроме того, нет необходимости определять <xref:System.Windows.NameScope> для данного типа анимации.  
  
 Локальные анимации могут использоваться только в коде и не могут определяться в стилях, шаблонах элементов управления и шаблонах данных.  После запуска локальной анимацией нельзя управлять в интерактивном режиме.  
  
 Для анимации с помощью локальной анимации необходимо выполнить следующие действия.  
  
1.  Создайте объект <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2.  Используйте метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> объекта, который требуется анимировать, чтобы применить к указанному свойству <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
 В следующем примере показана анимация ширины и цвета фона кнопки <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## Анимации часов  
 Используйте объекты <xref:System.Windows.Media.MediaPlayer.Clock%2A>, когда требуется выполнять анимацию без использования <xref:System.Windows.Media.Animation.Storyboard> и создавать сложные временные деревья или управлять анимациями в интерактивном режиме после их запуска.  Можно использовать объекты Clock для анимации [свойства зависимостей](GTMT) любого объекта <xref:System.Windows.Media.Animation.Animatable>.  
  
 Объекты <xref:System.Windows.Media.Animation.Clock> нельзя использовать непосредственно для анимации в стилях, шаблонах элементов управления или шаблонах данных.  \(Анимация и система расчета времени фактически используют объекты <xref:System.Windows.Media.Animation.Clock> для анимации в стилях, шаблонах элементов управления и шаблонах данных, но необходимо создать эти объекты <xref:System.Windows.Media.Animation.Clock> с помощью <xref:System.Windows.Media.Animation.Storyboard>.  Дополнительные сведения об отношении между объектами <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.Clock> см. в разделе [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)\)  
  
 Чтобы применить один элемент <xref:System.Windows.Media.Animation.Clock> к свойству, выполните следующие действия.  
  
1.  Создайте объект <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2.  Используйте метод <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> элемента <xref:System.Windows.Media.Animation.AnimationTimeline> для создания <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Используйте метод <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> объекта, который требуется анимировать, чтобы применить к указанному свойству <xref:System.Windows.Media.Animation.AnimationClock>.  
  
 В следующем примере показано создание <xref:System.Windows.Media.Animation.AnimationClock> и применение его к двум аналогичным свойствам.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Чтобы создать дерево времени и использовать его для анимации свойств, выполните следующие действия.  
  
1.  Используйте объекты <xref:System.Windows.Media.Animation.ParallelTimeline> и <xref:System.Windows.Media.Animation.AnimationTimeline> для создания дерева времени.  
  
2.  Используйте <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> элемента <xref:System.Windows.Media.Animation.ParallelTimeline> для создания <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Пройдите по <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> элемента <xref:System.Windows.Media.Animation.ClockGroup> и примените его дочерние объекты <xref:System.Windows.Media.Animation.Clock>.  Для каждого дочернего объекта <xref:System.Windows.Media.Animation.AnimationClock> используйте метод <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> объекта, который требуется анимировать, чтобы применить <xref:System.Windows.Media.Animation.AnimationClock> к указанному свойству.  
  
 Дополнительные сведения об объектах Clock см. в разделе [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## Покадровая анимация: обход анимации и системы управления временем  
 Этот подход следует использовать, если требуется полностью обойти систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Одним скриптом при таком подходе является анимация физики, при которой на каждом шаге анимации требуется пересчитывать объекты на основе последних результатов взаимодействия между объектами.  
  
 Покадровые анимации не могут быть определены внутри стилей, шаблонов элементов управления и шаблонов данных.  
  
 Для анимации "кадр\-за\-кадром" производится регистрация события <xref:System.Windows.Media.CompositionTarget.Rendering> объекта, содержащего объекты, которые требуется анимировать.  Этот метод обработчика событий вызывается один раз за кадр.  Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] маршалирует сохраненные данные отрисовки в [визуальном дереве](GTMT) через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий могут выполняться любые вычисления, необходимые для эффекта анимации, и задаваться свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы определить продолжительность текущего кадра, <xref:System.EventArgs>, связанные с этим событием, могут быть приведены к <xref:System.Windows.Media.RenderingEventArgs>, предоставляющим свойство <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>, которое можно использовать для получения времени отрисовки текущего кадра.  
  
 Дополнительные сведения см. на странице <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)