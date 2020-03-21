---
title: Практическое руководство. Повторение анимации
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141553"
---
# <a name="how-to-repeat-an-animation"></a>Практическое руководство. Повторение анимации
В этом примере <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> показано, <xref:System.Windows.Media.Animation.Timeline> как использовать свойство объекта для управления повторным поведением анимации.  
  
## <a name="example"></a>Пример  
 Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> элемента <xref:System.Windows.Media.Animation.Timeline> управления, сколько раз анимация повторяет свою простую продолжительность. С <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>помощью этого можно <xref:System.Windows.Media.Animation.Timeline> указать, что повторяется определенное количество раз (количество итерации) или за определенный период времени. В любом случае анимация проходит столько от начала до конца, что ему нужно для заполнения запрошенного подсчета или продолжительности.  
  
 По умолчанию, сроки имеют повторный подсчет 1,0, что означает, что они играют один раз и не повторяются. Однако, если <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> вы установите свойство <xref:System.Windows.Media.Animation.Timeline> к, <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>сроки повторяется на неопределенный срок.  
  
 В следующем примере показано, как использовать свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> для управления повторным поведением анимации. Пример оживляет <xref:System.Windows.FrameworkElement.Width%2A> свойство пяти прямоугольников с каждым прямоугольником, используя другой тип повторного поведения.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Для полного примера [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)  
  
## <a name="see-also"></a>См. также раздел

- [Накапливание значений анимации в повторяющихся циклах](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Определение автоматического реверса для шкалы времени](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Разделы руководства по анимации и таймерам](animation-and-timing-how-to-topics.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Пример поведения анимации с учетом времени](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
