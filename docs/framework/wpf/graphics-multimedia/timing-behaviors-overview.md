---
title: "Общие сведения о характере поведения во времени | Microsoft Docs"
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
  - "поведения, учет времени"
  - "поведение с учетом времени"
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Общие сведения о характере поведения во времени
В этом разделе описывается характер изменения во времени поведения анимации и других объектов <xref:System.Windows.Media.Animation.Timeline>.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Для понимания этого раздела требуется знакомство с основными возможностями анимации.  Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="timelinetypes"></a>   
## Типы временной шкалы  
 <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени.  Он предоставляет свойства, позволяющие задать длину этого сегмента, время его запуска, количество повторов, скорость течения времени в этом сегменте и многое другое.  
  
 Классы, которые наследуют классу временной шкалы, обеспечивают дополнительные функциональные возможности, такие как анимация и воспроизведение мультимедиа.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие типы <xref:System.Windows.Media.Animation.Timeline>.  
  
|Тип шкалы времени|Описание|  
|-----------------------|--------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Абстрактный базовый класс для объектов <xref:System.Windows.Media.Animation.Timeline>, порождающих выходные значения для свойств анимации.|  
|<xref:System.Windows.Media.MediaTimeline>|Создает выходные данные из файла мультимедиа.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Тип шкалы времени <xref:System.Windows.Media.Animation.TimelineGroup>, который группирует дочерние объекты <xref:System.Windows.Media.Animation.Timeline> и управляет ими.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Тип <xref:System.Windows.Media.Animation.ParallelTimeline>, который предоставляет целевые сведения о содержащихся в нем объектах временной шкалы.|  
|<xref:System.Windows.Media.Animation.Timeline>|Абстрактный базовый класс, определяющий характер поведения во времени.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Абстрактный класс для объектов <xref:System.Windows.Media.Animation.Timeline>, которые могут содержать другие объекты <xref:System.Windows.Media.Animation.Timeline>.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## Свойства, управляющие длиной временной шкалы  
 <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени, а длину временной шкалы можно описать различными способами.  В следующей таблице приводятся разные термины для описания длины временной шкалы.  
  
|Термин|Описание|Свойства||||  
|------------|--------------|--------------|-|-|-|  
|Простая длительность|Интервал времени, который требуется, чтобы временная шкала совершила одну итерацию.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Одно повторение|Интервал времени, который требуется, чтобы временная шкала совершила воспроизведение в прямом направлении один раз, и, если свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> имеет значение true, то еще воспроизведение в обратном направлении один раз.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Активный период|Интервал времени, который требуется, чтобы временная шкала выполнила все повторения, заданные ее свойством <xref:System.Windows.Media.Animation.RepeatBehavior>.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### Свойство Duration  
 Как было сказано выше, временная шкала представляет собой сегмент времени.  Длина этого сегмента определяется свойством <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы.  Когда временная шкала достигает конца своей длительности, воспроизведение прекращается.  Если временная шкала имеет дочерние временные шкалы, то они также останавливают воспроизведение.  В случае анимации свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A> определяет, как долго анимация выполняет переход от ее начального значения до конечного.  Длительность временной шкалы иногда называют *простой длительностью*, чтобы различать продолжительность одной итерации и общий интервал времени анимации, включая повторения.  Можно указать длительность, используя значение времени окончания, а также специальные значения <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>.  Длительность анимации должна приводить к значению <xref:System.Windows.Duration.TimeSpan%2A> для осуществления перехода между значениями.  
  
 В следующем примере показана <xref:System.Windows.Media.Animation.DoubleAnimation> с <xref:System.Windows.Media.Animation.Timeline.Duration%2A> в пять секунд.  
  
  
  
 Контейнеры временной шкалы, например <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.ParallelTimeline>, по умолчанию имеют продолжительность <xref:System.Windows.Duration.Automatic%2A>, то есть они автоматически завершаются после того, как их последний дочерний элемент останавливает воспроизведение.  В следующем примере показана <xref:System.Windows.Media.Animation.Storyboard>, чья продолжительность <xref:System.Windows.Media.Animation.Timeline.Duration%2A> установлена в пять секунд, т.е. время, которое необходимо для завершения всех дочерних объектов <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
  
  
 Установив продолжительность <xref:System.Windows.Media.Animation.Timeline.Duration%2A> контейнера временной шкалы в значение <xref:System.Windows.Duration.TimeSpan%2A>, можно принудительно продлить или укоротить воспроизведение его дочерних объектов <xref:System.Windows.Media.Animation.Timeline>.  Если задать значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A> меньше, чем длина контейнера временной шкалы его дочерних объектов <xref:System.Windows.Media.Animation.Timeline>, то дочерние объекты <xref:System.Windows.Media.Animation.Timeline> остановят воспроизведение одновременно с контейнером.  В следующем примере устанавливается <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.Storyboard> из предыдущего примера в три секунды.  В результате первая <xref:System.Windows.Media.Animation.DoubleAnimation> останавливается после трех секунд, когда анимируемая ширина прямоугольника достигает 60.  
  
  
  
<a name="repeatinganimations"></a>   
### Свойство RepeatBehavior  
 Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> определяет, сколько раз будет повторяться простая длительность.  С помощью свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> можно указать число воспроизведений временной шкалы \(итерация <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>\) или общий интервал времени ее воспроизведения \(повторение <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>\).  В любом случае, анимация осуществляет столько проходов от начала до конца, сколько требуется для выполнения заполнения запрошенного числа повторов или длительности.  По умолчанию временные шкалы имеют число итераций, равное `1.0`, то есть воспроизведение происходит один раз и не повторяется.  
  
 В следующем примере свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> используется, чтобы заставить <xref:System.Windows.Media.Animation.DoubleAnimation> воспроизвести ее простую длительность два раза, указав счетчик итераций.  
  
  
  
 В следующем примере с помощью свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, задается воспроизведение <xref:System.Windows.Media.Animation.DoubleAnimation> половины простой длительности.  
  
  
  
 Если установить свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> в <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, то <xref:System.Windows.Media.Animation.Timeline> будет повторяться до остановки в интерактивном режиме или до остановки системой времени.  В следующем примере с помощью свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, задается бесконечное воспроизведение <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
  
  
 Дополнительный пример см. в разделе [Повторение анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### Свойство AutoReverse  
 Свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> указывает, будет ли каждая итерация <xref:System.Windows.Media.Animation.Timeline> воспроизводиться еще и в обратном направлении.  В следующем примере для свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> анимации <xref:System.Windows.Media.Animation.DoubleAnimation> задается значение `true`; в результате чего анимация выполняется от нуля до 100, а затем от 100 до нуля.  Воспроизведение длится всего 10 секунд.  
  
  
  
 Если значение <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> задано для свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline>, а свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> шкалы <xref:System.Windows.Media.Animation.Timeline> имеет значение `true`, то простое повторение состоит из одной прямой итерации и одной обратной.  В следующем примере для свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> анимации <xref:System.Windows.Media.Animation.DoubleAnimation> из предыдущего примера в значение <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>, равное двум.  В результате анимация <xref:System.Windows.Media.Animation.DoubleAnimation> воспроизводится в течение 20 секунд: в прямом направлении в течение пяти секунд, в обратном направлении в течение пяти секунд, снова в прямом в течение пяти секунд, а затем в обратном направлении в течение пяти секунд.  
  
  
  
 Если контейнер временной шкалы имеет дочерние объекты<xref:System.Windows.Media.Animation.Timeline>, то они изменяют направление вместе с контейнером временной шкалы.  Дополнительные примеры см. в разделе [Определение автоматического реверса для шкалы времени](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## Свойство BeginTime  
 Свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> позволяет указать, когда должна запускаться временная шкала.  Время начала временной шкалы измеряется относительно ее родительской шкалы времени.  Время начала в ноль секунд означает, что временная шкала начинается сразу после запуска ее родителя; любое другое значение задает смещение между началом воспроизведения родительской временной шкалы и дочерней.  Например, время начала, равное двум секундам, означает, что временная шкала начинает воспроизведение, когда ее родительская шкала уже будет воспроизводиться в течение двух секунд.  По умолчанию все временные шкалы имеют нулевое время начала.  Можно также установить начало временной шкалы в `null`, что предотвратит ее запуск.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно указать значение Null с помощью [Расширение разметки x:NULL](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
 Обратите внимание, что время начала не применяется при каждом повторении временной шкалы из\-за установки <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  Если необходимо создать анимацию с <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, равным 10 секундам, и <xref:System.Windows.Media.Animation.RepeatBehavior>, имеющим значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, то будет выполнена 10\-секундная задержка перед воспроизведением анимации первый раз, но не для каждого успешного повторения.  Однако если родительская шкала анимации была перезапущена или повторена, то 10\-секундная задержка будет происходить.  
  
 Свойство<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> удобно использовать для сдвига временной шкалы.  В следующем примере создается <xref:System.Windows.Media.Animation.Storyboard>, который имеет два дочерних объекта <xref:System.Windows.Media.Animation.DoubleAnimation>.  Первая анимация имеет длительность <xref:System.Windows.Media.Animation.Timeline.Duration%2A> пять секунд, а вторая ― длительность <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 секунды.  В примере устанавливается время начала <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> второй анимации<xref:System.Windows.Media.Animation.DoubleAnimation>, равное 5 секундам, так что она начинает воспроизведение после завершения первой <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
  
  
<a name="fillbehaviorproperty"></a>   
## Свойство FillBehavior  
 Когда <xref:System.Windows.Media.Animation.Timeline> достигает конца своей общей активной продолжительности, свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> определяет, должна ли она остановиться или сохранить последнее значение.  Анимация со свойством <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>, имеющим значение <xref:System.Windows.Media.Animation.FillBehavior>, сохраняет свое выходное значение: свойство, для которого выполнялась анимация, сохраняет последнее значение анимации.  Значение <xref:System.Windows.Media.Animation.FillBehavior> указывает, что по завершении анимация прекращает воздействовать на целевое свойство.  
  
 В следующем примере создается <xref:System.Windows.Media.Animation.Storyboard>, который имеет два дочерних объекта <xref:System.Windows.Media.Animation.DoubleAnimation>.  Оба объекта <xref:System.Windows.Media.Animation.DoubleAnimation> анимируют свойство <xref:System.Windows.FrameworkElement.Width%2A> класса <xref:System.Windows.Shapes.Rectangle> от 0 до 100.  У элементов <xref:System.Windows.Shapes.Rectangle> есть неанимируемые значения <xref:System.Windows.FrameworkElement.Width%2A> из 500 [аппаратно\-независимых пикселей](GTMT).  
  
-   Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> первой анимации <xref:System.Windows.Media.Animation.DoubleAnimation> по умолчанию устанавливается в значение <xref:System.Windows.Media.Animation.FillBehavior>.  В результате ширина прямоугольника остается равной 100 после завершения анимации <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
-   Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> второй анимации <xref:System.Windows.Media.Animation.DoubleAnimation> устанавливается в значение <xref:System.Windows.Media.Animation.FillBehavior>.  В результате свойство <xref:System.Windows.FrameworkElement.Width%2A> второго прямоугольника <xref:System.Windows.Shapes.Rectangle> возвращается к значению 500 после завершения анимации <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
  
  
<a name="speedproperties"></a>   
## Свойства, управляющие скоростью временной шкалы  
 Класс <xref:System.Windows.Media.Animation.Timeline> предоставляет три свойства для задания скорости шкалы:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> ― указывает скорость относительно родительской шкалы, в которой течет время для <xref:System.Windows.Media.Animation.Timeline>.  Значения больше единицы увеличивают скорость <xref:System.Windows.Media.Animation.Timeline> и ее дочерних объектов <xref:System.Windows.Media.Animation.Timeline>; значения между 0 и единицей замедляют скорость.  Значение, равное единице, указывает, что время <xref:System.Windows.Media.Animation.Timeline> течет с той же скоростью, что и у родителя.  Установка <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> для контейнера временной шкалы также влияет на все его дочерние объекты <xref:System.Windows.Media.Animation.Timeline>.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> ― указывает процент длительности <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, затраченный на ускорение.  Пример см. в разделе [Ускорение или замедление анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> ― указывает процент длительности <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, затраченный на замедление.  Пример см. в разделе [Ускорение или замедление анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970)