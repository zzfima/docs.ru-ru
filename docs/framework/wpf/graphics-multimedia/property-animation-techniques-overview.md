---
title: Общие сведения о методах анимации свойств
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 0b4bf6d4963f32ad83f762fce73c805197ff9c9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181843"
---
# <a name="property-animation-techniques-overview"></a>Общие сведения о методах анимации свойств
В этом разделе описываются различные подходы к анимации свойств: раскадровки, локальные анимации, часы и покадровая анимация.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с базовыми средствами анимации, которые описаны в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
<a name="summary"></a>
## <a name="different-ways-to-animate"></a>Различные способы анимации  
 Так как существует множество различных сценариев для анимации свойств, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько подходов к анимации свойств.  
  
 Для каждого подхода в следующей таблице указано, можно ли применять его к конкретным экземплярам, использовать в стилях, в шаблонах элементов управления или в шаблонах данных, можно ли использовать его в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и позволяет ли этот подход интерактивно управлять анимацией.  Применение к конкретным экземплярам подразумевает применение анимации или раскадровки непосредственно к экземплярам объектов, а не в стилях, шаблонах элементов управления или шаблонах данных.  
  
|Подход к анимации|Сценарии|Поддерживает XAML|Интерактивное управление|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Раскадровка|В-экземпляр, <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate>,<xref:System.Windows.DataTemplate>|Да|Да|  
|Локальная анимация|Применение к конкретным экземплярам|нет|нет|  
|Часы|Применение к конкретным экземплярам|нет|Да|  
|Покадровая анимация|Применение к конкретным экземплярам|нет|Недоступно|  
  
<a name="storyboard_animations"></a>
## <a name="storyboard-animations"></a>Раскадровка  
 Используйте, <xref:System.Windows.Media.Animation.Storyboard> когда вы хотите определить и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]применить анимацию в, интерактивно контролировать анимацию после их запуска, создать <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate> сложное дерево анимации, или анимировать в , или <xref:System.Windows.DataTemplate>. Для объекта, который будет <xref:System.Windows.Media.Animation.Storyboard>анимирован, <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>он должен быть или, <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>он должен быть использован для установки или . Дополнительные сведения см. в разделе [Общие сведения о раскадровке](storyboards-overview.md).  
  
 A <xref:System.Windows.Media.Animation.Storyboard> — это специальный тип контейнера, <xref:System.Windows.Media.Animation.Timeline> который предоставляет информацию о таргетинге для содержащихся в нем анимаций. Чтобы оживить с <xref:System.Windows.Media.Animation.Storyboard>, вы заполните следующие три шага.  
  
1. Объявить <xref:System.Windows.Media.Animation.Storyboard> a и одну или несколько анимаций.  
  
2. Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> и прилагаемые свойства для указания целевого объекта и свойства каждой анимации.  
  
3. (только код) Определите <xref:System.Windows.NameScope> для <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>или . Зарегистрируйте имена объектов, чтобы <xref:System.Windows.FrameworkElement> оживить <xref:System.Windows.FrameworkContentElement>это или .  
  
4. Начните <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Начало <xref:System.Windows.Media.Animation.Storyboard> применяет анимацию к свойствам, которые они анимируют, и запускает их. Существует два способа <xref:System.Windows.Media.Animation.Storyboard>начать: вы можете <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> использовать метод, предоставляемый <xref:System.Windows.Media.Animation.Storyboard> классом, или вы можете использовать <xref:System.Windows.Media.Animation.BeginStoryboard> действие. Единственный способ оживить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] это использовать <xref:System.Windows.Media.Animation.BeginStoryboard> действие. Действие <xref:System.Windows.Media.Animation.BeginStoryboard> может быть использовано <xref:System.Windows.EventTrigger> <xref:System.Windows.Trigger>в, <xref:System.Windows.DataTrigger>свойстве, или .  
  
 В следующей таблице показаны <xref:System.Windows.Media.Animation.Storyboard> различные места, где поддерживается каждый метод начала: каждый экземпляр, стиль, шаблон управления и шаблон данных.  
  
|Раскадровка запускается с помощью метода...|Применение к конкретным экземплярам|Style|Шаблон элемента управления|Шаблон данных|Пример|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>и<xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>и свойство<xref:System.Windows.Trigger>|нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>и<xref:System.Windows.DataTrigger>|нет|Да|Да|Да|[Практическое руководство. Запуск анимации при изменении данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|Метод<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|нет|нет|нет|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Для получения <xref:System.Windows.Media.Animation.Storyboard> дополнительной информации [Storyboards Overview](storyboards-overview.md)об объектах см.  
  
## <a name="local-animations"></a>Локальная анимация  
 Локальные анимации обеспечивают удобный способ оживить свойство <xref:System.Windows.Media.Animation.Animatable> зависимости любого объекта. Используйте локальную анимацию, когда необходимо применить одну анимацию к свойству и не требуется интерактивно управлять анимацией после ее запуска. В <xref:System.Windows.Media.Animation.Storyboard> отличие от анимации, локальная анимация может оживить <xref:System.Windows.FrameworkElement> объект, <xref:System.Windows.FrameworkContentElement>который не связан с a или a. Вы также не должны определить <xref:System.Windows.NameScope> для этого типа анимации.  
  
 Локальные анимации могут использоваться только в коде. Их нельзя определить в стилях, шаблонах элементов управления и шаблонах данных. После запуска локальной анимации управлять ей в интерактивном режиме нельзя.  
  
 Для анимации с помощью локальной анимации выполните следующие действия.  
  
1. Создайте объект <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2. Используйте <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод объекта, который требуется оживить, <xref:System.Windows.Media.Animation.AnimationTimeline> чтобы применить свойство, которое вы указываете.  
  
 Ниже приводится следующий <xref:System.Windows.Controls.Button>пример, как оживить ширину и цвет фона .  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Часы  
 Используйте <xref:System.Windows.Media.MediaPlayer.Clock%2A> объекты, когда вы хотите <xref:System.Windows.Media.Animation.Storyboard> анимировать без использования, и вы хотите создать сложные деревья синхронизации или интерактивные анимации управления после их запуска. Объекты Clock можно использовать для анимации <xref:System.Windows.Media.Animation.Animatable> свойства зависимости любого объекта.  
  
 Вы не <xref:System.Windows.Media.Animation.Clock> можете использовать объекты непосредственно для аниматора в стилях, шаблонах управления или шаблонах данных. (Система анимации и синхронизации действительно использует <xref:System.Windows.Media.Animation.Clock> объекты для анимации в стилях, шаблонах <xref:System.Windows.Media.Animation.Clock> управления и <xref:System.Windows.Media.Animation.Storyboard>шаблонах данных, но она должна создавать эти объекты для вас из . Для получения дополнительной информации о взаимосвязи [Animation and Timing System Overview](animation-and-timing-system-overview.md)между <xref:System.Windows.Media.Animation.Storyboard> объектами и <xref:System.Windows.Media.Animation.Clock> объектами см.  
  
 Чтобы применить <xref:System.Windows.Media.Animation.Clock> сингл к свойству, вы выполните следующие шаги.  
  
1. Создайте объект <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2. Используйте <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> метод <xref:System.Windows.Media.Animation.AnimationTimeline> создания <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3. Используйте <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> метод объекта, который вы хотите оживить, <xref:System.Windows.Media.Animation.AnimationClock> чтобы применить к указанному свойству.  
  
 Ниже приводится следующий <xref:System.Windows.Media.Animation.AnimationClock> пример, как создать и применить его к двум аналогичным свойствам.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Чтобы создать дерево временной шкалы и использовать его анимации свойств, выполните следующие действия.  
  
1. Использование <xref:System.Windows.Media.Animation.ParallelTimeline> <xref:System.Windows.Media.Animation.AnimationTimeline> и объекты для создания дерева времени.  
  
2. <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> Используйте корень <xref:System.Windows.Media.Animation.ParallelTimeline> для создания <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3. Итерировать через <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> и <xref:System.Windows.Media.Animation.ClockGroup> применять свои <xref:System.Windows.Media.Animation.Clock> детские объекты. Для <xref:System.Windows.Media.Animation.AnimationClock> каждого ребенка <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> используйте метод объекта, который вы хотите <xref:System.Windows.Media.Animation.AnimationClock> оживить, чтобы применить к указанному свойству  
  
 Дополнительные сведения об объектах часов см. в разделе [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Покадровая анимация: обход анимации и системы управления временем  
 Этот подход следует использовать, если требуется полностью обойти систему анимации WPF [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Один из сценариев для такого подхода — анимация физики, при которой на каждом шаге анимации требуется пересчитывать объекты на основе последнего набора итераций объектов.  
  
 Покадровую анимацию нельзя определить в стилях, шаблонах элементов управления или шаблонах данных.  
  
 Чтобы оживить кадр за кадром, вы <xref:System.Windows.Media.CompositionTarget.Rendering> регистрируетесь для случая объекта, который содержит объекты, которые вы хотите анимировать. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий выполняются все вычисления, необходимые для эффекта анимации, и задаются свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы получить время презентации для <xref:System.EventArgs> текущего кадра, связанные с этим событием могут быть отлиты как, <xref:System.Windows.Media.RenderingEventArgs>которые обеспечивают <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> свойство, которое можно использовать для получения времени рендеринга текущего кадра.  
  
 Дополнительные сведения см. на странице <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
- [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)
- [Общие сведения о свойствах зависимости](../advanced/dependency-properties-overview.md)
