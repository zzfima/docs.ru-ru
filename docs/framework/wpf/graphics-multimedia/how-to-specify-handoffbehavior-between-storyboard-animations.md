---
title: "Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21d4a39b9cbd2ee563edd22818630c18658e1d6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
 [Анимация и расчет времени](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
