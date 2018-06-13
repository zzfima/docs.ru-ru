---
title: Практическое руководство. Установка длительности анимации
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: df9e12e1bd3a365c3013d0f75df663bd46186ee2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561379"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Практическое руководство. Установка длительности анимации
Объект <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени и длина этого сегмента определяется по временной шкале <xref:System.Windows.Duration>. Когда <xref:System.Windows.Media.Animation.Timeline> достигает конца его длительности воспроизведение прекращается. Если <xref:System.Windows.Media.Animation.Timeline> имеет дочерние временные шкалы, они также останавливают воспроизведение. В случае анимации <xref:System.Windows.Duration> указывает, как долго анимация выполняет переход от ее начального значения до конечного.  
  
 Можно указать <xref:System.Windows.Duration> с определенным, ограниченным временем или специальные значения <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>. Длительность анимации всегда должен иметь значение времени, поскольку анимация всегда должен иметь определенную, ограниченную длину — в противном случае анимации не узнает, как переход между заданными значениями. Шкалы времени контейнера (<xref:System.Windows.Media.Animation.TimelineGroup> объектов), таких как <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.ParallelTimeline>, имеют длительность по умолчанию <xref:System.Windows.Duration.Automatic%2A>, то есть они автоматически завершаются после их последний дочерний элемент останавливает воспроизведение.  
  
 В следующем примере, ширину, высоту и заполнения цвет <xref:System.Windows.Shapes.Rectangle> выполняется анимация. Длительность, установленная для анимации или контейнера, оказывает эффекты анимации, включая управление скоростью анимации, а также путем переопределения длительность дочерние временные шкалы с длительностью контейнера временной шкалы.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Duration>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
