---
title: Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141177"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
В этом примере <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> показано, как <xref:System.Windows.Media.Animation.Timeline> указать для неактивного анимированного свойства.  
  
## <a name="example"></a>Пример  
 Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит со значением анимированного свойства, когда <xref:System.Windows.Media.Animation.Timeline> оно не анимируется, то есть, когда оно неактивно, но его родитель <xref:System.Windows.Media.Animation.Timeline> находится внутри своего активного или удерживаемого периода. Например, остается ли анимированное свойство в конечном значении после окончания анимации или возвращается к значению, имевачтому до начала анимации?  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется для <xref:System.Windows.FrameworkElement.Width%2A> анимировать два прямоугольника. В каждом прямоугольнике используется другой <xref:System.Windows.Media.Animation.Timeline> объект.  
  
 Один <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> имеет, что <xref:System.Windows.Media.Animation.FillBehavior.Stop>установлен на , что приводит к ширине прямоугольника, чтобы <xref:System.Windows.Media.Animation.Timeline> вернуться к своей неанимированной значение, когда заканчивается. Другой <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>из, что приводит к ширине, чтобы <xref:System.Windows.Media.Animation.Timeline> остаться в его конечное значение, когда заканчивается.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Для полного примера, см [Анимация Пример Галерея](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Разделы руководства по анимации и таймерам](animation-and-timing-how-to-topics.md)
