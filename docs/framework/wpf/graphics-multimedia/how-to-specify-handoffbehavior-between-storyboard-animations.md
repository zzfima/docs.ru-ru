---
title: Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: c4728dc1cb4eeeff55e533b8d91e4512d9cc1d94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560555"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки
В этом примере показано, как указать поведение перемещения между анимациями раскадровки. <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Свойство <xref:System.Windows.Media.Animation.BeginStoryboard> указывает, как новая анимация взаимодействовать с любыми существующими анимациями, которые уже применены к свойству.  
  
## <a name="example"></a>Пример  
 В следующем примере создается две кнопки, увеличивающиеся при перемещении курсора мыши над ними и уменьшаются при перемещении курсора немедленно. Если указатель мыши находится над кнопки и быстро удалить курсор, вторая анимация будут применены до завершения первой. При перекрытии двух объектов анимации следующим образом, можно увидеть разницу между <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> значения <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> и <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Значение <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> объединяет перекрывающиеся анимации, вызывая плавный переход между анимации при значение <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> вызывает новой анимацией немедленно заменить ранее перекрывающиеся анимации.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Анимация и расчет времени](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
