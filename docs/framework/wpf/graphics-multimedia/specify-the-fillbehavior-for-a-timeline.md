---
title: Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: c88deeb679a3e8f2027d6bb2e817edc1ade5926d
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519858"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
В этом примере показано, как указать <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для неактивного <xref:System.Windows.Media.Animation.Timeline> анимированного свойства.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Свойство <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит с значение анимированного свойства, если оно не анимировано, то есть когда <xref:System.Windows.Media.Animation.Timeline> неактивна, но его родительский <xref:System.Windows.Media.Animation.Timeline> находится в своем активном периоде или периоде удержания. Например, она анимированного свойства по-прежнему со своей стороны значение после окончания анимации или делает это вернуться к значению, которое было до начала анимации?  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.FrameworkElement.Width%2A> двух прямоугольников. Каждый прямоугольник использует другое <xref:System.Windows.Media.Animation.Timeline> объекта.  
  
 Один <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> , имеет значение <xref:System.Windows.Media.Animation.FillBehavior.Stop>, чего ширина прямоугольника, вернуться к его не анимированное значение, если <xref:System.Windows.Media.Animation.Timeline> заканчивается. Другой <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> из <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, чего ширина оставаться в конце значения при <xref:System.Windows.Media.Animation.Timeline> заканчивается.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Полный пример см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Анимация и расчет времени](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
