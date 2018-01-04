---
title: "Практическое руководство. Повторение анимации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 591053d479b7d26757eb071f08ed4216fc0d57fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-repeat-an-animation"></a>Практическое руководство. Повторение анимации
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство <xref:System.Windows.Media.Animation.Timeline> для управления повторением анимации.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойство <xref:System.Windows.Media.Animation.Timeline> определяет, сколько раз анимации повторе его простой длительности. С помощью <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, можно указать, что <xref:System.Windows.Media.Animation.Timeline> повторяется для определенное число раз (итераций) или в течение указанного времени. В любом случае анимация проходит через столько запусков начала до конца, сколько требуется для запрошенного числа повторений или длительности.  
  
 По умолчанию временные шкалы имеют число повторов, равным 1,0, это означает, воспроизведение происходит один раз и не повторяется. Тем не менее если задать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство <xref:System.Windows.Media.Animation.Timeline> для <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, временная шкала повторяется бесконечно.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства для управления повторением анимации. В примере анимируется <xref:System.Windows.FrameworkElement.Width%2A> свойство пяти прямоугольников, каждый с помощью другой тип поведения.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Полный пример см. в разделе [пример поведения анимации времени](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>См. также  
 [Накапливание значений анимации в повторяющихся циклах](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Определение автоматического реверса для шкалы времени](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Анимация и расчет времени](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Пример поведения анимации с учетом времени](http://go.microsoft.com/fwlink/?LinkID=159970)
