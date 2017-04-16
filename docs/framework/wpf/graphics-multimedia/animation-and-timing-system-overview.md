---
title: "Общие сведения об анимации и системе управления временем | Microsoft Docs"
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
  - "анимация [WPF]"
  - "синхронизирующая система [WPF]"
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения об анимации и системе управления временем
В этом подразделе описывается, как система управления временем использует анимацию, <xref:System.Windows.Media.Animation.Timeline> и классы <xref:System.Windows.Media.Animation.Clock> для анимации свойств.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы понять содержимое этого раздела, необходимо знать, как использовать анимацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для анимации свойств, описанной в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  В нем также можно ознакомиться с [зависимыми свойствами](GTMT). Дополнительные сведения см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## Шкала времени и часы  
 В [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) описывается, как <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени, а анимация является типом <xref:System.Windows.Media.Animation.Timeline>, который создает значения для выходных данных.  Сам по себе параметр <xref:System.Windows.Media.Animation.Timeline> не содержит ничего, кроме описания сегмента времени.  Реальную работу выполняет объект <xref:System.Windows.Media.Animation.Clock> шкалы времени.  Аналогично, анимация тоже фактически не выполняет анимирования свойств. Класс анимации описывает способ расчета выходных значений, а для анимации создается <xref:System.Windows.Media.Animation.Clock> и применяет анимацию к свойствам.  
  
 <xref:System.Windows.Media.Animation.Clock> представляет собой особый тип объекта, который поддерживает состояние выполнения, связанное с временем, для <xref:System.Windows.Media.Animation.Timeline>.  Он предоставляет три бита информации, необходимые для анимации и системы управления временем: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A> и <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>.  <xref:System.Windows.Media.Animation.Clock> определяет его текущее время, ход выполнения и состояние с помощью поведения времени, описываемого его <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и т. д.  
  
 В большинстве случаев <xref:System.Windows.Media.Animation.Clock> создается автоматически для шкалы времени.  При выполнении анимации с использованием объекта <xref:System.Windows.Media.Animation.Storyboard> или метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> для шкалы времени и анимации автоматически создаются часы, которые затем применяется к их целевым свойствам.  Можно также создать <xref:System.Windows.Media.Animation.Clock> явным образом с помощью метода <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> <xref:System.Windows.Media.Animation.Timeline>.  Метод <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=fullName> создает часы соответствующего типа для <xref:System.Windows.Media.Animation.Timeline>, на котором они вызываются.  Если <xref:System.Windows.Media.Animation.Timeline> содержит шкалы времени для дочерних элементов, для них также создаются объекты <xref:System.Windows.Media.Animation.Clock>.  Полученные объекты <xref:System.Windows.Media.Animation.Clock> располагаются в деревьях в соответствии со структурой дерева объектов <xref:System.Windows.Media.Animation.Timeline>, в котором они создаются.  
  
 Существуют различные типы часов для различных типов шкал времени.  В следующей таблице показаны типы <xref:System.Windows.Media.Animation.Clock>, которые соответствуют некоторым другим типам <xref:System.Windows.Media.Animation.Timeline>.  
  
|Тип шкалы времени|Тип часов|Назначение часов|  
|-----------------------|---------------|----------------------|  
|Анимация \(наследует от <xref:System.Windows.Media.Animation.AnimationTimeline>\)|<xref:System.Windows.Media.Animation.AnimationClock>|Создает выходные значения для свойства зависимостей.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Обрабатывает файл мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Группирует и управляет дочерними объектами <xref:System.Windows.Media.Animation.Clock>|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Группирует и управляет дочерними объектами <xref:System.Windows.Media.Animation.Clock>|  
  
 Объекты <xref:System.Windows.Media.Animation.AnimationClock> можно применить к совместимым свойствам зависимостей с помощью метода <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A>.  
  
 В скриптах с высокой нагрузкой, например при анимации большого количества сходных объектов, управление использованием объекта <xref:System.Windows.Media.Animation.Clock> может повысить производительность.  
  
<a name="timemanager"></a>   
## Часы и диспетчер времени  
 При анимации объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управление объектами <xref:System.Windows.Media.MediaPlayer.Clock%2A>, создаваемыми для шкал времени, осуществляется с помощью диспетчера времени.  Диспетчер времени является корнем дерева объектов <xref:System.Windows.Media.MediaPlayer.Clock%2A> и управляет потоком времени в этом дереве.  Для каждого приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] автоматически создается диспетчер времени, невидимый для разработчиков приложений. Диспетчер времени "тикает" много раз в секунду; фактическое число квантов, возникающих каждую секунду, варьируется в зависимости доступных ресурсов системы.  Во время каждого из этих квантов времени диспетчер времени вычисляет состояние всех объектов <xref:System.Windows.Media.Animation.ClockState> <xref:System.Windows.Media.Animation.Clock> в дереве расчета времени.  
  
 На следующем рисунке показана связь между диспетчером времени и <xref:System.Windows.Media.Animation.AnimationClock>, а также анимированными свойствами зависимостей.  
  
 ![компоненты временной системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm\_clocks\_1clock1prop")  
Анимирование свойства  
  
 Когда диспетчер времени "тикает", он обновляет время каждого <xref:System.Windows.Media.Animation.ClockState> <xref:System.Windows.Media.Animation.Clock> в приложении.  Если <xref:System.Windows.Media.Animation.Clock> является <xref:System.Windows.Media.Animation.AnimationClock>, он использует метод <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> для <xref:System.Windows.Media.Animation.AnimationTimeline>, из которого он был создан, для расчета его текущего выходного значения.  <xref:System.Windows.Media.Animation.AnimationClock> предоставляет <xref:System.Windows.Media.Animation.AnimationTimeline> текущее местное время, входное значение, которое обычно является базовым значением свойства и исходным значением по умолчанию для места назначения.  После получения значения анимированного свойства с помощью метода <xref:System.Windows.DependencyObject.GetValue%2A> или метода доступа CLR, предоставляются выходные данные его <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### Группы часов  
 В предыдущем разделе описаны различные типы объектов <xref:System.Windows.Media.Animation.Clock> для различных типов шкал времени.  На следующем рисунке показана связь между диспетчером времени, <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock> и анимированными свойствами зависимостей.  <xref:System.Windows.Media.Animation.ClockGroup> создается для шкал времени, которые группируют другие шкалы времени, такие как класс <xref:System.Windows.Media.Animation.Storyboard>, который группирует анимацию и другие шкалы времени.  
  
 ![компоненты временной системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm\_clocks\_2clock1clockgroup2prop")  
ClockGroup  
  
#### Композиция  
 Это позволяет связать несколько часов с одним свойством. При этом каждые часы используют выходное значение предыдущих часов в качестве базового значения.  Ниже показаны три объекта <xref:System.Windows.Media.Animation.AnimationClock>, примененные к одному и тому же свойству.  Часы 1 используют базовое значение анимированного свойства в качестве входных данных и для создания выходных данных.  Часы 2 принимают выходные данные от Часов 1 в качестве входных данных и использует их для создания выходных данных.  Часы 3 принимают выходные данные от Часов 2 в качестве входных данных и использует их для создания выходных данных.  Когда несколько часов влияют на одно и то же свойство одновременно, считается, что они находятся в цепочке композиции.  
  
 ![компоненты временной системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm\_clocks\_2clock1prop")  
Цепочка композиции  
  
 Обратите внимание, что хотя связь создается между входными и выходными данными объектов <xref:System.Windows.Media.Animation.AnimationClock> в цепочке композиции, их поведение времени не меняется. Объекты <xref:System.Windows.Media.Animation.Clock> \(включая <xref:System.Windows.Media.Animation.AnimationClock>\) имеют иерархическую зависимость от их родительских объектов <xref:System.Windows.Media.Animation.Clock>.  
  
 Чтобы применить несколько часов к одному свойству, используйте <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior> при применении <xref:System.Windows.Media.Animation.Storyboard>, анимации и <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### Объединение квантов времени и событий  
 В дополнение к расчету выходных значений тикающий диспетчер времени выполняет и другие операции: он определяет состояние всех часов и вызывает соответствующие события.  
  
 Хотя такты меняются часто, между ними может возникать множество событий.  Например, <xref:System.Windows.Media.Animation.Clock> может быть остановлен, запущен и остановлен снова. При этом значение <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> изменится три раза.  Теоретически событие <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> может быть вызвано несколько раз в одном такте. Однако ядро времени объединяет события, поэтому событие <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> не может быть вызвано более одного раза за такт.  Это относится ко всем событиям расчета времени. Для заданного объекта <xref:System.Windows.Media.Animation.Clock> может быть вызвано не более одного события каждого типа.  
  
 Когда <xref:System.Windows.Media.Animation.Clock> изменяет состояние и возвращается обратно в исходное состояние между тактами \(например, изменение из <xref:System.Windows.Media.Animation.ClockState> в <xref:System.Windows.Media.Animation.ClockState> и обратно в <xref:System.Windows.Media.Animation.ClockState>\), связанное событие все равно возникнет.  
  
 Дополнительные сведения о событиях расчета времени см. в разделе [Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## Текущие и базовые значения свойств  
 Анимированное свойство может иметь два значения: базовое и текущее.  При установке свойства с помощью метода доступа CLR или метода <xref:System.Windows.DependencyObject.SetValue%2A> устанавливается его базовое значение.  Если свойство не анимировано, его базовое и текущее значение совпадают.  
  
 При анимации свойства <xref:System.Windows.Media.Animation.AnimationClock> задает *текущее* значение свойства.  При извлечении значения свойства с помощью метода доступа CLR или метода <xref:System.Windows.DependencyObject.GetValue%2A> возвращаются выходные данные <xref:System.Windows.Media.Animation.AnimationClock>, если <xref:System.Windows.Media.Animation.AnimationClock> является <xref:System.Windows.Media.Animation.ClockState> или <xref:System.Windows.Media.Animation.ClockState>.  Можно получить базовое значение свойства с помощью метода <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A>.  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)