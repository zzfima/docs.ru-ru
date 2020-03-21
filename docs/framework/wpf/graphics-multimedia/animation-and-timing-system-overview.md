---
title: Общие сведения об анимации и системе управления временем
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: d0ac2a8160a1e6f9bcdb333593ec207954b391aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187706"
---
# <a name="animation-and-timing-system-overview"></a>Общие сведения об анимации и системе управления временем
В этой теме описывается, <xref:System.Windows.Media.Animation.Timeline>как <xref:System.Windows.Media.Animation.Clock> система синхронизации использует анимацию и классы для анимации свойств.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять содержимое этого раздела, необходимо знать, как использовать анимацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для анимации свойств, как описано в разделе [Общие сведения об эффектах анимации](animation-overview.md). В нем также можно ознакомиться со свойствами зависимостей. Дополнительные сведения см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>
## <a name="timelines-and-clocks"></a>Временные шкалы и часы  
 [Обзор анимации](animation-overview.md) описал, <xref:System.Windows.Media.Animation.Timeline> как а представляет собой сегмент времени, <xref:System.Windows.Media.Animation.Timeline> а анимация — это тип, который производит значения вывода. Сам по <xref:System.Windows.Media.Animation.Timeline>себе, не делает ничего, кроме просто описать сегмент времени. Это объект Временной шкалы, <xref:System.Windows.Media.Animation.Clock> который делает реальную работу. Аналогичным образом, анимация на самом деле не оживляет свойства: класс анимации описывает, как должны быть вычисляются значения вывода, но это то, <xref:System.Windows.Media.Animation.Clock> что было создано для анимации, которая управляет выходом анимации и применяет его к свойствам.  
  
 A <xref:System.Windows.Media.Animation.Clock> — это особый тип объекта, который поддерживает состояние <xref:System.Windows.Media.Animation.Timeline>времени выполнения для . Он предоставляет три бита информации, которые имеют <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>важное значение для анимации и системы синхронизации: , <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>и <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. A <xref:System.Windows.Media.Animation.Clock> определяет его текущее время, прогресс и состояние, используя <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.Duration%2A>поведение <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>времени, описанное его : , и так далее.  
  
 В большинстве <xref:System.Windows.Media.Animation.Clock> случаев a создается автоматически для вашей Временной шкалы. При анимации с помощью <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> или метода часы автоматически создаются для ваших временных линий и анимаций и применяются к их целевым свойствам. Вы также можете <xref:System.Windows.Media.Animation.Clock> создать явно <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> с помощью метода вашего <xref:System.Windows.Media.Animation.Timeline>. Метод <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> создает часы соответствующего типа, <xref:System.Windows.Media.Animation.Timeline> для которого он называется. Если <xref:System.Windows.Media.Animation.Timeline> в графике ребенка <xref:System.Windows.Media.Animation.Clock> содержатся детские сроки, он создает объекты и для них. Полученные <xref:System.Windows.Media.Animation.Clock> объекты расположены на деревьях, которые соответствуют структуре <xref:System.Windows.Media.Animation.Timeline> дерева объектов, из которых они создаются.  
  
 Существует различных типа часов для различных типов шкал времени. В следующей <xref:System.Windows.Media.Animation.Clock> таблице показаны типы, <xref:System.Windows.Media.Animation.Timeline> соответствующие некоторым типам.  
  
|Тип временной шкалы|Тип часов|Назначение часов|  
|-------------------|----------------|-------------------|  
|Анимация (наследует от <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Создает выходные значения для свойства зависимостей.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Обрабатывает файл мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Группы и <xref:System.Windows.Media.Animation.Clock> управление своими детскими объектами|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Группы и <xref:System.Windows.Media.Animation.Clock> управление своими детскими объектами|  
  
 Вы можете <xref:System.Windows.Media.Animation.AnimationClock> применить любые объекты, которые вы <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> создаете, к совместимым свойствам зависимости с помощью метода.  
  
 В сценариях, связанных с производительностью, таких как анимация большого количества подобных объектов, управление собственным <xref:System.Windows.Media.Animation.Clock> использованием может обеспечить преимущества производительности.  
  
<a name="timemanager"></a>
## <a name="clocks-and-the-time-manager"></a>Часы и диспетчер времени  
 Когда вы оживляют [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]объекты в, это менеджер <xref:System.Windows.Media.MediaPlayer.Clock%2A> времени, который управляет объектами, созданными для ваших временных линий. Диспетчер времени — это корень дерева объектов <xref:System.Windows.Media.MediaPlayer.Clock%2A>, который управляет потоком времени в этом дереве.  Диспетчер времени создается автоматически для каждого приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и остается невидимым для разработчика приложения. Диспетчер времени "тикает" много раз в секунду; фактическое число тактов, возникающих каждую секунду, зависит от доступных системных ресурсов. Во время каждого из этих тиков диспетчер времени <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> вычисляет состояние всех объектов в дереве синхронизации.  
  
 На следующей иллюстрации показаны отношения <xref:System.Windows.Media.Animation.AnimationClock>между диспетчером времени и анимированным свойством зависимости.  
  
 ![Компоненты временной системы](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Анимирование свойства  
  
 Когда диспетчер времени тикает, он обновляет <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> время каждого в приложении. Если <xref:System.Windows.Media.Animation.Clock> это <xref:System.Windows.Media.Animation.AnimationClock>, он <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> использует метод, <xref:System.Windows.Media.Animation.AnimationTimeline> из которого он был создан для расчета его текущего значения вывода. Поставляет <xref:System.Windows.Media.Animation.AnimationClock> <xref:System.Windows.Media.Animation.AnimationTimeline> с текущим местным временем, входное значение, которое, как правило, базовое значение свойства, и значение назначения по умолчанию. При получении значения анимированного свойства <xref:System.Windows.DependencyObject.GetValue%2A> с помощью метода или его аксессуара CLR вы получаете выход его. <xref:System.Windows.Media.Animation.AnimationClock>  
  
#### <a name="clock-groups"></a>Группы часов  
 В предыдущем разделе описано, <xref:System.Windows.Media.Animation.Clock> как существуют различные типы объектов для различных типов временных линий. На следующей иллюстрации показаны отношения <xref:System.Windows.Media.Animation.ClockGroup>между <xref:System.Windows.Media.Animation.AnimationClock>временной менеджером, а, и анимированным свойством зависимости. A <xref:System.Windows.Media.Animation.ClockGroup> создается для временных линий, которые <xref:System.Windows.Media.Animation.Storyboard> группируют другие временные линии, такие как класс, который группирует анимацию и другие временные линии.  
  
 ![Компоненты временной системы](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
ClockGroup  
  
#### <a name="composition"></a>Создание  
 Можно связать несколько часов с одним свойством. При этом каждые часы используют выходное значение предыдущих часов в качестве своего базового значения. На следующей <xref:System.Windows.Media.Animation.AnimationClock> иллюстрации показаны три объекта, применяемые к тому же свойству. Clock1 использует базовое значение анимируемого свойства в качестве входных данных и для создания выходных данных. Clock2 принимает выходные данные от Clock1 в качестве входных данных и использует их для создания выходных данных. Clock3 принимает выходные данные от Clock2 в качестве входных данных и использует их для создания выходных данных. Когда несколько часов влияют на одно и то же свойство одновременно, считается, что они находятся в цепочке композиции.  
  
 ![Компоненты временной системы](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Цепочка композиции  
  
 Обратите внимание, что, хотя связь создается <xref:System.Windows.Media.Animation.AnimationClock> между входным и выходным объектов в цепочке композиции, их поведение времени не влияет; <xref:System.Windows.Media.Animation.Clock> объекты <xref:System.Windows.Media.Animation.AnimationClock> (включая объекты) имеют иерархическую зависимость от родительских <xref:System.Windows.Media.Animation.Clock> объектов.  
  
 Чтобы применить несколько часов к тому <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> же свойству, используйте при <xref:System.Windows.Media.Animation.Storyboard>применении, анимация, или. <xref:System.Windows.Media.Animation.AnimationClock>  
  
#### <a name="ticks-and-event-consolidation"></a>Такты и объединение событий  
 В дополнение к расчету выходных значений тикающий диспетчер времени выполняет и другие операции: он определяет состояние всех часов и вызывает соответствующие события.  
  
 Хотя такты меняются часто, между ними может возникать множество событий. Например, <xref:System.Windows.Media.Animation.Clock> может быть остановлен, запущен и остановлен снова, и в этом случае его <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> значение изменится три раза. <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> Теоретически, событие может быть поднято несколько раз одним тиком; однако, механизм синхронизации консолидирует события, так что <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> событие может быть поднято не чаще одного раза за тик. Это относится ко всем событиям синхронизации: не более одного <xref:System.Windows.Media.Animation.Clock> события каждого типа поднимается для данного объекта.  
  
 Когда <xref:System.Windows.Media.Animation.Clock> коммутирует состояния и возвращается обратно в исходное <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Stopped> состояние между <xref:System.Windows.Media.Animation.ClockState.Active>тиками (например, изменение от вкл и обратно к), связанное событие все еще происходит.  
  
 Дополнительные сведения о временных событиях см. в разделе [Общие сведения о временных событиях](timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>
## <a name="current-values-and-base-values-of-properties"></a>Текущие и базовые значения свойств  
 Анимированное свойство может иметь два значения: базовое значение и текущее. При установке свойства с помощью <xref:System.Windows.DependencyObject.SetValue%2A> аксессуара CLR или метода вы устанавливаете его базовое значение. Если свойство не анимировано, его базовое и текущее значения совпадают.  
  
 При анимировать свойство <xref:System.Windows.Media.Animation.AnimationClock> *устанавливается текущая* стоимость свойства. Получение стоимости свойства через его clR-аксессуар <xref:System.Windows.DependencyObject.GetValue%2A> или метод возвращает <xref:System.Windows.Media.Animation.AnimationClock> выход, <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling>когда <xref:System.Windows.Media.Animation.AnimationClock> является или . Вы можете получить базовое значение свойства <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> с помощью метода.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о временных событиях](timing-events-overview.md)
- [Общие сведения о характере поведения во времени](timing-behaviors-overview.md)
