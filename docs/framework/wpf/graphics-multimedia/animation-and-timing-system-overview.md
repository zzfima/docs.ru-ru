---
title: "Общие сведения об анимации и системе управления временем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 484aa47744de95c849b237112f1a383c2c2cb0b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="animation-and-timing-system-overview"></a>Общие сведения об анимации и системе управления временем
В этом разделе описывается, как система управления временем использует анимацию, <xref:System.Windows.Media.Animation.Timeline>, и <xref:System.Windows.Media.Animation.Clock> классы для анимации свойства.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять содержимое этого раздела, необходимо знать, как использовать анимацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для анимации свойств, как описано в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). В нем также можно ознакомиться со свойствами зависимостей. Дополнительные сведения см. в разделе [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Временные шкалы и часы  
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) описано как <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени и анимации — это тип <xref:System.Windows.Media.Animation.Timeline> , выдает выходные значения. Сам по себе <xref:System.Windows.Media.Animation.Timeline>, не выполняет никаких действий не просто описывают сегмент времени. Он является временной шкалы <xref:System.Windows.Media.Animation.Clock> объект, который не работает. Аналогично, анимация не анимации фактически свойств: класс анимации описывает способ вычисления выходных значений, но это <xref:System.Windows.Media.Animation.Clock> , созданный для анимации, которая диски вывода анимации и применяет его свойства.  
  
 Объект <xref:System.Windows.Media.Animation.Clock> — это специальный тип объекта, который поддерживает состояние времени для выполнения <xref:System.Windows.Media.Animation.Timeline>. Он предоставляет три бита сведения, которые необходимы для анимации и системы управления временем: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, и <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. Объект <xref:System.Windows.Media.Animation.Clock> определяет его текущее время, ход выполнения и состояние с помощью поведения времени, описываемого его <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, и т. д.  
  
 В большинстве случаев <xref:System.Windows.Media.Animation.Clock> создается автоматически для временной шкалы. При анимации с помощью <xref:System.Windows.Media.Animation.Storyboard> или <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод, автоматически создаются для шкалы времени и анимации и применены к свойствам целевого часами. Можно также создать <xref:System.Windows.Media.Animation.Clock> явным образом с помощью <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> метод вашей <xref:System.Windows.Media.Animation.Timeline>. <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> Метод создает часы соответствующего типа для <xref:System.Windows.Media.Animation.Timeline> на которой он вызывается. Если <xref:System.Windows.Media.Animation.Timeline> содержит дочерние временные шкалы, он создает <xref:System.Windows.Media.Animation.Clock> объектов также для них. Итоговый <xref:System.Windows.Media.Animation.Clock> объекты располагаются в деревья, совпадает со структурой <xref:System.Windows.Media.Animation.Timeline> дерева объектов, из которой они созданы.  
  
 Существует различных типа часов для различных типов шкал времени. В следующей таблице показаны <xref:System.Windows.Media.Animation.Clock> типы, которые соответствуют некоторым другим <xref:System.Windows.Media.Animation.Timeline> типов.  
  
|Тип временной шкалы|Тип часов|Назначение часов|  
|-------------------|----------------|-------------------|  
|Анимация (наследует от <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Создает выходные значения для свойства зависимостей.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Обрабатывает файл мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Группирует и управляет дочерними <xref:System.Windows.Media.Animation.Clock> объектов|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Группирует и управляет дочерними <xref:System.Windows.Media.Animation.Clock> объектов|  
  
 Можно применить любой <xref:System.Windows.Media.Animation.AnimationClock> объекты, созданные для свойства зависимостей, совместимые с помощью <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> метод.  
  
 В сценариях с высокой нагрузкой, например анимации большого количества сходных объектов, управление использованием <xref:System.Windows.Media.Animation.Clock> может повысить производительность.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Часы и диспетчер времени  
 При анимации объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], это время диспетчер, который управляет <xref:System.Windows.Media.MediaPlayer.Clock%2A> объекты, созданные для временных шкал. Диспетчер времени — это корень дерева объектов <xref:System.Windows.Media.MediaPlayer.Clock%2A>, который управляет потоком времени в этом дереве.  Диспетчер времени создается автоматически для каждого приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и остается невидимым для разработчика приложения. Диспетчер времени "тикает" много раз в секунду; фактическое число тактов, возникающих каждую секунду, зависит от доступных системных ресурсов. Во время каждого из этих тактов, диспетчер времени вычисляет состояние всех <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> объектов в дереве времени.  
  
 На следующем рисунке показано отношение между диспетчером времени и <xref:System.Windows.Media.Animation.AnimationClock>и анимированное свойство зависимостей.  
  
 ![Определяет время компоненты системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Анимирование свойства  
  
 Когда диспетчер времени тактах обновляются время каждый <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> в приложении. Если <xref:System.Windows.Media.Animation.Clock> — <xref:System.Windows.Media.Animation.AnimationClock>, он использует <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> метод <xref:System.Windows.Media.Animation.AnimationTimeline> из которой он был создан для расчета его текущего выходного значения. <xref:System.Windows.Media.Animation.AnimationClock> Предоставляет <xref:System.Windows.Media.Animation.AnimationTimeline> с текущее местное время, входное значение, которое обычно является базовым значением свойства и конечное значение по умолчанию. При извлечении значения анимированного свойства с помощью <xref:System.Windows.DependencyObject.GetValue%2A> метода или метода доступа CLR, можно получить выходные данные его <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Группы часов  
 В предыдущем разделе описаны различные типы <xref:System.Windows.Media.Animation.Clock> объектов для различных типов шкал времени. На следующем рисунке показано отношение между диспетчером времени <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock>и анимированное свойство зависимостей. Объект <xref:System.Windows.Media.Animation.ClockGroup> создается для временных шкал, группу других временных шкал, например <xref:System.Windows.Media.Animation.Storyboard> класс, который группирует анимации и других временных шкалах.  
  
 ![Определяет время компоненты системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
ClockGroup  
  
#### <a name="composition"></a>Композиция  
 Можно связать несколько часов с одним свойством. При этом каждые часы используют выходное значение предыдущих часов в качестве своего базового значения. На следующем рисунке показано три <xref:System.Windows.Media.Animation.AnimationClock> объекты, которые применены к одному свойству. Clock1 использует базовое значение анимируемого свойства в качестве входных данных и для создания выходных данных. Clock2 принимает выходные данные от Clock1 в качестве входных данных и использует их для создания выходных данных. Clock3 принимает выходные данные от Clock2 в качестве входных данных и использует их для создания выходных данных. Когда несколько часов влияют на одно и то же свойство одновременно, считается, что они находятся в цепочке композиции.  
  
 ![Определяет время компоненты системы](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Цепочка композиции  
  
 Обратите внимание, что, несмотря на то, что связь создается между вход и Выход <xref:System.Windows.Media.Animation.AnimationClock> объекты в цепочке композиции, их поведение времени не меняется. <xref:System.Windows.Media.Animation.Clock> объекты (включая <xref:System.Windows.Media.Animation.AnimationClock> объектов) имеют иерархическую зависимость от их родительских <xref:System.Windows.Media.Animation.Clock> объектов.  
  
 Чтобы применить то же свойство несколько часов, используйте <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> при применении <xref:System.Windows.Media.Animation.Storyboard>, анимацию, или <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Такты и объединение событий  
 В дополнение к расчету выходных значений тикающий диспетчер времени выполняет и другие операции: он определяет состояние всех часов и вызывает соответствующие события.  
  
 Хотя такты меняются часто, между ними может возникать множество событий. Например <xref:System.Windows.Media.Animation.Clock> может остановлен, запущен и остановлен снова в этом случае его <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> значение будет изменено три раза. В теории <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> событие может быть вызвано несколько раз в одном такте; Однако временной механизм объединяет события, чтобы <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> события необходимо более одного раза одному такту. Это верно для всех событий синхронизации: не более одного каждого типа события для заданного <xref:System.Windows.Media.Animation.Clock> объекта.  
  
 При <xref:System.Windows.Media.Animation.Clock> изменяет состояние и возвращается обратно в исходное состояние между тактами (изменяющиеся из <xref:System.Windows.Media.Animation.ClockState.Active> для <xref:System.Windows.Media.Animation.ClockState.Stopped> и обратно в <xref:System.Windows.Media.Animation.ClockState.Active>), по-прежнему происходит связанного события.  
  
 Дополнительные сведения о временных событиях см. в разделе [Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Текущие и базовые значения свойств  
 Анимированное свойство может иметь два значения: базовое значение и текущее. При задании свойства с помощью метода доступа CLR или <xref:System.Windows.DependencyObject.SetValue%2A> метод, устанавливается его базовое значение. Если свойство не анимировано, его базовое и текущее значения совпадают.  
  
 При анимации свойства <xref:System.Windows.Media.Animation.AnimationClock> устанавливает свойство *текущей* значение. Получение значения свойства через метода доступа CLR или <xref:System.Windows.DependencyObject.GetValue%2A> метод возвращает выходные данные <xref:System.Windows.Media.Animation.AnimationClock> при <xref:System.Windows.Media.Animation.AnimationClock> — <xref:System.Windows.Media.Animation.ClockState.Active> или <xref:System.Windows.Media.Animation.ClockState.Filling>. Базовое значение этого свойства можно получить с помощью <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> метод.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
