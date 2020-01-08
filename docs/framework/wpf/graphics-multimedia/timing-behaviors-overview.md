---
title: Общие сведения о характере поведения во времени
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559954"
---
# <a name="timing-behaviors-overview"></a>Общие сведения о характере поведения во времени
В этом разделе описываются временные поведения анимации и других <xref:System.Windows.Media.Animation.Timeline> объектов.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Для понимания этого раздела необходимо ознакомиться с базовыми средствами анимации. Дополнительные сведения см. в разделе [Общие сведения об анимации](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Типы временных шкал  
 <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени. Он предоставляет свойства, с помощью которых вы сможете задать длину этого сегмента, время запуска сегмента, количество повторов сегмента, скорость течения времени в этом сегменте и многое другое.  
  
 Классы, которые унаследованы от класса временной шкалы, предоставляют дополнительные функции, такие как анимация и воспроизведение мультимедиа. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие типы <xref:System.Windows.Media.Animation.Timeline>.  
  
|Тип временной шкалы|Описание|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Абстрактный базовый класс для <xref:System.Windows.Media.Animation.Timeline> объектов, создающих выходные значения для свойств анимации.|  
|<xref:System.Windows.Media.MediaTimeline>|Формирует выходные данные из файла мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Тип <xref:System.Windows.Media.Animation.TimelineGroup>, группирующий и управляющий дочерними <xref:System.Windows.Media.Animation.Timeline> объектами.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Тип <xref:System.Windows.Media.Animation.ParallelTimeline>, предоставляющий сведения о нацеливании для объектов временной шкалы, которые она содержит.|  
|<xref:System.Windows.Media.Animation.Timeline>|Абстрактный базовый класс, который определяет поведение во времени.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Абстрактный класс для <xref:System.Windows.Media.Animation.Timeline> объектов, которые могут содержать другие объекты <xref:System.Windows.Media.Animation.Timeline>.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Свойства, которые управляют длиной временной шкалы  
 <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени, а длина временной шкалы может быть описана различными способами. В следующей таблице приведены несколько терминов для описания длины временной шкалы.  
  
|Термин|Описание|Свойства||||  
|----------|-----------------|----------------|-|-|-|  
|Простая длительность|Длительность, необходимая для одной итерации временной шкалы вперед.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Одно повторение|Длительность однократного воспроизведения временной шкалы и, если свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> имеет значение true, воспроизведение выполняется назад.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Период активности|Продолжительность времени, затрачиваемого на выполнение всех повторений, указанных в свойстве <xref:System.Windows.Media.Animation.RepeatBehavior>.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>значение <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>значение <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Свойство Duration  
 Как упоминалось ранее, временная шкала представляет собой сегмент времени. Длина этого сегмента определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A>временной шкалы. Когда временная шкала достигает окончания своей длительности, воспроизведение прекращается. Если у временной шкалы есть дочерние временные шкалы, их воспроизведение также останавливается. В случае анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> указывает время, затрачиваемое анимацией на переход от начального значения к конечному значению. Длительность временной шкалы иногда называется его *простой длительностью*, чтобы различать продолжительность отдельной итерации и общее время воспроизведения анимации, включая повторения. Длительность можно указать с помощью значения конечного времени или специальных значений <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>. Длительность анимации должна разрешаться в <xref:System.Windows.Duration.TimeSpan%2A> значение, чтобы оно могло переходить между значениями.  
  
 В следующем примере показан <xref:System.Windows.Media.Animation.DoubleAnimation> с <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 секунд.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Временные шкалы контейнера, такие как <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.ParallelTimeline>, имеют длительность <xref:System.Windows.Duration.Automatic%2A>по умолчанию, что означает, что они автоматически завершаются при прекращении воспроизведения последней дочерней точки. В следующем примере показан <xref:System.Windows.Media.Animation.Storyboard>, в котором <xref:System.Windows.Media.Animation.Timeline.Duration%2A> разрешается в пять секунд, время, необходимое для завершения всех дочерних <xref:System.Windows.Media.Animation.DoubleAnimation> объектов.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Установив для <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы контейнера значение <xref:System.Windows.Duration.TimeSpan%2A>, можно принудить к игре дольше или короче, чем его дочерние <xref:System.Windows.Media.Animation.Timeline>ные объекты. Если для <xref:System.Windows.Media.Animation.Timeline.Duration%2A> задано значение, меньшее, чем длина дочернего объекта <xref:System.Windows.Media.Animation.Timeline> временной шкалы контейнера, дочерние <xref:System.Windows.Media.Animation.Timeline>ные объекты прекращают воспроизведение, когда выполняется временная шкала контейнера. В следующем примере задается <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.Storyboard> из предыдущих примеров в три секунды. В результате первая <xref:System.Windows.Media.Animation.DoubleAnimation> прекращается через три секунды, когда она анимируется по ширине целевого прямоугольника до 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>Свойство RepeatBehavior  
 Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> определяет, сколько раз оно повторяется просто. С помощью свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> можно указать, сколько раз будет воспроизводиться временная шкала (итерация <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) или Общая длительность времени воспроизведения (повторение <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). В любом случае анимация пройдет такое количество циклов от начала до конца, которое необходимо для получения необходимого количества повторов или необходимой длительности. По умолчанию временные шкалы имеют число итераций `1.0`. Это означает, что они воспроизводятся один раз и не повторяются.  
  
 В следующем примере свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> используется для того, чтобы <xref:System.Windows.Media.Animation.DoubleAnimation> воспроизводить в два раза больше простой, указывая число итераций.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 В следующем примере используется свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> для воспроизведения <xref:System.Windows.Media.Animation.DoubleAnimation> в течение половины простой длительности.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Если для свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> задано значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, <xref:System.Windows.Media.Animation.Timeline> повторяется до остановки в интерактивном режиме или системы времени. В следующем примере свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> используется для того, чтобы <xref:System.Windows.Media.Animation.DoubleAnimation> воспроизводится неограниченное время.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Дополнительные примеры см. в разделе [повторение анимации](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>Свойство AutoReverse  
 Свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> указывает, будет ли <xref:System.Windows.Media.Animation.Timeline> воспроизводиться в конце каждой прямой итерации в обратном направлении. В следующем примере для свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> задается значение `true`; в результате он анимируется от нуля до 100, а затем от 100 до нуля. Суммарное время воспроизведения составляет 10 секунд.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 При использовании значения <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> для указания <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> и свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> этого <xref:System.Windows.Media.Animation.Timeline> `true`, одно повторение состоит из одной прямой итерации, за которой следует одна обратная итерация.  В следующем примере задается <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> из предыдущего примера в <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> из двух. В результате <xref:System.Windows.Media.Animation.DoubleAnimation> играет в течение 20 секунд: вперед в течение пяти секунд, назад в течение 5 секунд и затем обратно в течение пяти секунд.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Если временная шкала контейнера содержит дочерние объекты <xref:System.Windows.Media.Animation.Timeline>, они отменяются при выполнении временной шкалы контейнера. Дополнительные примеры см. [в разделе Указание автоматической отмены временной шкалы](how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>Свойство BeginTime  
 Свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> позволяет указать время запуска временной шкалы.  Время запуска временной шкалы задается относительно ее родительской временной шкалы. Время запуска в ноль секунд означает, что временная шкала запускается сразу после запуска ее родительской шкалы; любое другое значение задает смещение времени запуска дочерней шкалы от времени запуска родительской. Например, время запуска, равное двум секундам, означает, что временная шкала начнет воспроизведение в момент, когда ее родительская временная шкала достигнет времени в две секунды. По умолчанию время запуска для всех временных шкал установлено в ноль секунд. Вы также можете задать время начала временной шкалы, чтобы `null`, что предотвращает запуск временной шкалы. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]значение NULL указывается с помощью [расширения разметки x:NULL](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Обратите внимание, что время начала не применяется каждый раз, когда повторяется временная шкала из-за настройки <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>. Если бы вы создавали анимацию с <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>ом в течение 10 секунд и <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, то до первого воспроизведения анимации будет возникнет 10-секундная задержка, но не для каждого последующего повторения. Однако при перезапуске или при повторе родительской временной шкалы возникла бы 10-секундная задержка.  
  
 Свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> удобно использовать для сдвига временных шкал. В следующем примере создается <xref:System.Windows.Media.Animation.Storyboard> с двумя дочерними объектами <xref:System.Windows.Media.Animation.DoubleAnimation>. Первая анимация имеет <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 секунд, а вторая — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 секунды. В примере задается <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> второй <xref:System.Windows.Media.Animation.DoubleAnimation> равным 5 секундам, чтобы начало воспроизводилось после завершения первого <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>Свойство FillBehavior  
 Когда <xref:System.Windows.Media.Animation.Timeline> достигает конца общей активной длительности, свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> указывает, будет ли оно остановлено или содержит свое последнее значение. Анимация с <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>ом <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "содержит" свое выходное значение: свойство, для которого выполняется анимация, сохраняет последнее значение анимации. Значение <xref:System.Windows.Media.Animation.FillBehavior.Stop> приводит к тому, что анимация останавливается на ее целевом свойстве после ее завершения.  
  
 В следующем примере создается <xref:System.Windows.Media.Animation.Storyboard> с двумя дочерними объектами <xref:System.Windows.Media.Animation.DoubleAnimation>. Оба <xref:System.Windows.Media.Animation.DoubleAnimation> объектов позволяют анимировать <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> от 0 до 100. Элементы <xref:System.Windows.Shapes.Rectangle> имеют неанимированные <xref:System.Windows.FrameworkElement.Width%2A> значения 500 [независимые от устройства Пиксели].  
  
- Свойству <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> первого <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, а в качестве значения по умолчанию. В результате ширина прямоугольника остается в 100 после окончания <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
- Свойству <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> второго <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение <xref:System.Windows.Media.Animation.FillBehavior.Stop>. В результате <xref:System.Windows.FrameworkElement.Width%2A> второй <xref:System.Windows.Shapes.Rectangle> возвращается к 500 после завершения <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Свойства, которые управляют скоростью временной шкалы  
 Класс <xref:System.Windows.Media.Animation.Timeline> предоставляет три свойства для указания скорости:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> — указывает скорость относительных показателей относительно родительского <xref:System.Windows.Media.Animation.Timeline>объекта. Значения, превышающие единицу, увеличивают скорость <xref:System.Windows.Media.Animation.Timeline> и ее дочерние объекты <xref:System.Windows.Media.Animation.Timeline>; значения от нуля до одного замедления. Значение 1 указывает, что <xref:System.Windows.Media.Animation.Timeline> выполняется по той же ставке, что и ее родительский элемент. Параметр <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> временной шкалы контейнера влияет также на все дочерние объекты <xref:System.Windows.Media.Animation.Timeline>.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> — указывает процентную долю <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, потраченную на ускорение. Пример см. в разделе [как ускорить или замедлить анимацию](how-to-accelerate-or-decelerate-an-animation.md). 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> — указывает процент <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, потраченный на замедление. Пример см. в разделе [как ускорить или замедлить анимацию](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об анимации](animation-overview.md)
- [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)
- [Общие сведения о временных событиях](timing-events-overview.md)
- [Практические руководства](animation-and-timing-how-to-topics.md)
- [Пример поведения анимации с учетом времени](https://go.microsoft.com/fwlink/?LinkID=159970)
