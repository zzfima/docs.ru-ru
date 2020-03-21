---
title: Общие сведения о характере поведения во времени
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145401"
---
# <a name="timing-behaviors-overview"></a>Общие сведения о характере поведения во времени
Эта тема описывает время поведения анимации <xref:System.Windows.Media.Animation.Timeline> и других объектов.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с базовыми средствами анимации. Для получения дополнительной информации смотрите [обзор анимации](animation-overview.md).  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>Типы временных шкал  
 A <xref:System.Windows.Media.Animation.Timeline> представляет собой отрезок времени. Он предоставляет свойства, с помощью которых вы сможете задать длину этого сегмента, время запуска сегмента, количество повторов сегмента, скорость течения времени в этом сегменте и многое другое.  
  
 Классы, которые унаследованы от класса временной шкалы, предоставляют дополнительные функции, такие как анимация и воспроизведение мультимедиа. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет следующие <xref:System.Windows.Media.Animation.Timeline> типы.  
  
|Тип временной шкалы|Описание|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Абстрактный <xref:System.Windows.Media.Animation.Timeline> базовый класс для объектов, генерирующих значения вывода для анимативных свойств.|  
|<xref:System.Windows.Media.MediaTimeline>|Формирует выходные данные из файла мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Тип <xref:System.Windows.Media.Animation.TimelineGroup> этих групп и <xref:System.Windows.Media.Animation.Timeline> управления детскими объектами.|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ParallelTimeline> Тип, содержащий информацию о таргетинге для содержащихся в ней объектов Хроники.|  
|<xref:System.Windows.Media.Animation.Timeline>|Абстрактный базовый класс, который определяет поведение во времени.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Абстрактный класс <xref:System.Windows.Media.Animation.Timeline> для <xref:System.Windows.Media.Animation.Timeline> объектов, которые могут содержать другие объекты.|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>Свойства, которые управляют длиной временной шкалы  
 A <xref:System.Windows.Media.Animation.Timeline> представляет собой отрезок времени, и продолжительность временной шкалы может быть описана по-разному. В следующей таблице приведены несколько терминов для описания длины временной шкалы.  
  
|Термин|Описание|Свойства||||  
|----------|-----------------|----------------|-|-|-|  
|Простая длительность|Длительность, необходимая для одной итерации временной шкалы вперед.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Одно повторение|Продолжительность времени, необходимого для временной шкалы, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> чтобы играть вперед один раз, и, если свойство верно, играть назад один раз.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Период активности|Продолжительность времени, необходимого для временной шкалы для завершения <xref:System.Windows.Media.Animation.RepeatBehavior> всех повторений, указанных в ее свойстве.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Свойство Duration  
 Как упоминалось ранее, временная шкала представляет собой сегмент времени. Длина этого сегмента определяется временной <xref:System.Windows.Media.Animation.Timeline.Duration%2A>шкалой . Когда временная шкала достигает окончания своей длительности, воспроизведение прекращается. Если у временной шкалы есть дочерние временные шкалы, их воспроизведение также останавливается. В случае анимации указывается, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> сколько времени занимает переход анимации от исходного значения к исходному значению. Продолжительность временной шкалы иногда называют ее *простой продолжительностью,* чтобы различать продолжительность одной итерации и общее время воспроизведения анимации, включая повторения. Вы можете указать продолжительность, используя конечное значение <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Duration.Forever%2A>времени или специальные значения или . Длительность анимации должна быть <xref:System.Windows.Duration.TimeSpan%2A> решена к значению, чтобы она мог переходить между значениями.  
  
 Следующий пример <xref:System.Windows.Media.Animation.DoubleAnimation> показывает <xref:System.Windows.Media.Animation.Timeline.Duration%2A> с пятью секундами.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Сроки контейнера, <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Media.Animation.ParallelTimeline>такие как и, имеют продолжительность по умолчанию, что означает, что они автоматически заканчиваются, когда их последний ребенок перестает играть. В следующем примере показано, <xref:System.Windows.Media.Animation.Storyboard> чье <xref:System.Windows.Media.Animation.Timeline.Duration%2A> решение составляет пять секунд, <xref:System.Windows.Media.Animation.DoubleAnimation> продолжительность времени, которое требуется всем детским объектам.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Установив временную шкалу <xref:System.Windows.Media.Animation.Timeline.Duration%2A> контейнера <xref:System.Windows.Duration.TimeSpan%2A> к значению, можно заставить играть <xref:System.Windows.Media.Animation.Timeline> дольше или короче, чем будут играть его детские объекты. Если вы <xref:System.Windows.Media.Animation.Timeline.Duration%2A> установите значение, меньшее длина объектов детской <xref:System.Windows.Media.Animation.Timeline> строки контейнера, объекты ребенка <xref:System.Windows.Media.Animation.Timeline> перестают воспроизвром при этом воплощаться в хронику контейнера. В следующем примере <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.Storyboard> приведены из предыдущих примеров до трех секунд. В результате первый <xref:System.Windows.Media.Animation.DoubleAnimation> перестает прогрессировать через три секунды, когда он анимировал ширину целевого прямоугольника до 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>Свойство RepeatBehavior  
 Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> элемента <xref:System.Windows.Media.Animation.Timeline> контроля, сколько раз он повторяет свою простую продолжительность. Используя <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство, можно указать, сколько раз воспроизводится шкала времени (итерация) <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>или общее время, в течение которых она должна играть (повтор). В любом случае анимация пройдет такое количество циклов от начала до конца, которое необходимо для получения необходимого количества повторов или необходимой длительности. По умолчанию, сроки имеют итерацию `1.0`кол, что означает, что они играют один раз и не повторяются вообще.  
  
 В следующем примере <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> используется <xref:System.Windows.Media.Animation.DoubleAnimation> свойство для воспроизведения в два раза ее простой продолжительности, указав количество итераций.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Следующий пример <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> использует свойство, чтобы сделать <xref:System.Windows.Media.Animation.DoubleAnimation> игру для половины его простой продолжительности.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Если вы <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> установите <xref:System.Windows.Media.Animation.Timeline> свойство <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> <xref:System.Windows.Media.Animation.Timeline> к, повторяет до тех пор, пока остановился в интерактивном режиме или по системе синхронизации. В следующем примере используется <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> свойство, чтобы сделать игру на неопределенный срок.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Для дополнительного примера [см.](how-to-repeat-an-animation.md)  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>Свойство AutoReverse  
 Свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> определяет, <xref:System.Windows.Media.Animation.Timeline> будет ли он играть в обратном направлении в конце каждой форвардной итерации. Следующий пример устанавливает <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> к <xref:System.Windows.Media.Animation.DoubleAnimation> свойству a to `true`; в результате он оживляет от нуля до 100, а затем от 100 до нуля. Суммарное время воспроизведения составляет 10 секунд.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 При использовании <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> значения для <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> указания <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойства и <xref:System.Windows.Media.Animation.Timeline> свойства, которое есть, `true`одно повторение состоит из одной вперед итерации с последующим одной обратной итерацией.  Следующий пример <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> устанавливает <xref:System.Windows.Media.Animation.DoubleAnimation> из предыдущего примера до <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> двух. В результате, <xref:System.Windows.Media.Animation.DoubleAnimation> играет в течение 20 секунд: вперед в течение пяти секунд, назад в течение пяти секунд, вперед в течение 5 секунд снова, а затем назад в течение пяти секунд.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Если в временной <xref:System.Windows.Media.Animation.Timeline> шкале контейнера есть объекты ребенка, они меняются при этом. Дополнительные [примеры см.](how-to-specify-whether-a-timeline-automatically-reverses.md)  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>Свойство BeginTime  
 Свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> позволяет указать, когда начинается шкала времени.  Время запуска временной шкалы задается относительно ее родительской временной шкалы. Время запуска в ноль секунд означает, что временная шкала запускается сразу после запуска ее родительской шкалы; любое другое значение задает смещение времени запуска дочерней шкалы от времени запуска родительской. Например, время запуска, равное двум секундам, означает, что временная шкала начнет воспроизведение в момент, когда ее родительская временная шкала достигнет времени в две секунды. По умолчанию время запуска для всех временных шкал установлено в ноль секунд. Вы также можете установить время начала `null`временной шкалы, что предотвращает начало временной шкалы. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вы указать null с помощью [x:Null расширение разметки](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Обратите внимание, что время начала не применяется каждый <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> раз, когда временная шкала повторяется из-за ее настройки. Если бы вы создали анимацию с <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 10 <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>секундами и а, то была бы 10-секундная задержка, прежде чем анимация играла в первый раз, но не для каждого последующего повторения. Однако при перезапуске или при повторе родительской временной шкалы возникла бы 10-секундная задержка.  
  
 Свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> полезно для ошеломляющие сроки. Следующий пример <xref:System.Windows.Media.Animation.Storyboard> создает, который <xref:System.Windows.Media.Animation.DoubleAnimation> имеет два объекта ребенка. Первая <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимация имеет пять секунд, а <xref:System.Windows.Media.Animation.Timeline.Duration%2A> вторая - 3 секунды. Пример устанавливает <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> секунду <xref:System.Windows.Media.Animation.DoubleAnimation> до 5 секунд, так что он <xref:System.Windows.Media.Animation.DoubleAnimation> начинает играть после первого конца.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>Свойство FillBehavior  
 <xref:System.Windows.Media.Animation.Timeline> Когда достигает конца своей общей активной продолжительности, <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство определяет, останавливается ли оно или удерживает его последнее значение. Анимация с <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "держит" свою выходную стоимость: анимированное свойство сохраняет последнее значение анимации. Значение <xref:System.Windows.Media.Animation.FillBehavior.Stop> причин, по которым анимация перестают влиять на целевое свойство после ее окончания.  
  
 Следующий пример <xref:System.Windows.Media.Animation.Storyboard> создает, который <xref:System.Windows.Media.Animation.DoubleAnimation> имеет два объекта ребенка. Оба <xref:System.Windows.Media.Animation.DoubleAnimation> объекта оживляют <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> от 0 до 100. Элементы <xref:System.Windows.Shapes.Rectangle> имеют неанимированные <xref:System.Windows.FrameworkElement.Width%2A> значения 500 «независимых пикселей устройства».  
  
- Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> первого <xref:System.Windows.Media.Animation.DoubleAnimation> устанавливается <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>на значение по умолчанию. В результате ширина прямоугольника остается на уровне 100 после <xref:System.Windows.Media.Animation.DoubleAnimation> окончания.  
  
- Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> второго <xref:System.Windows.Media.Animation.DoubleAnimation> устанавливается <xref:System.Windows.Media.Animation.FillBehavior.Stop>на . В результате, <xref:System.Windows.FrameworkElement.Width%2A> второй <xref:System.Windows.Shapes.Rectangle> возвращается к 500 после <xref:System.Windows.Media.Animation.DoubleAnimation> окончания.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Свойства, которые управляют скоростью временной шкалы  
 Класс <xref:System.Windows.Media.Animation.Timeline> предоставляет три свойства для определения его скорости:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>- Определяет этот показатель, по отношению к его родителю, в это время прогрессирует для <xref:System.Windows.Media.Animation.Timeline>. Значения, превышающее один, <xref:System.Windows.Media.Animation.Timeline> увеличивают скорость <xref:System.Windows.Media.Animation.Timeline> и его детских объектов; значения между нулем и одним замедляют его. Значение одного указывает <xref:System.Windows.Media.Animation.Timeline> на то, что прогрессирует с той же скоростью, что и его родитель. Настройка <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> временной шкалы контейнера влияет <xref:System.Windows.Media.Animation.Timeline> и на все его детские объекты.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>- Определяет процент <xref:System.Windows.Media.Animation.Timeline.Duration%2A> от временной шкалы, потраченной на ускорение. Например, [см. Как: Ускорить или утихать анимацию.](how-to-accelerate-or-decelerate-an-animation.md)
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>- Определяет процент от срока, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> потраченного на замедление. Например, [см. Как: Ускорить или утихать анимацию.](how-to-accelerate-or-decelerate-an-animation.md)  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)
- [Общие сведения о временных событиях](timing-events-overview.md)
- [Как-к темам](animation-and-timing-how-to-topics.md)
- [Пример поведения анимации с учетом времени](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
