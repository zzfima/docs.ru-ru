---
title: "Практическое руководство. Анимирование свойства с помощью AnimationClock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 145ff1be88f1af6692a8cf374e871479ed38d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Практическое руководство. Анимирование свойства с помощью AnimationClock
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Clock> объекты для анимации свойства.  
  
 Есть три способа анимации свойства зависимостей:  
  
-   Создание <xref:System.Windows.Media.Animation.AnimationTimeline> и связать его с этим свойством, с помощью <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Используйте метод объекта <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> применить один метод <xref:System.Windows.Media.Animation.AnimationTimeline> к целевому свойству.  
  
-   Создание <xref:System.Windows.Media.Animation.AnimationClock> из <xref:System.Windows.Media.Animation.AnimationTimeline> и применить его к свойству.  
  
 <xref:System.Windows.Media.Animation.Storyboard>объекты и <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод позволяют анимировать свойства без непосредственного создания и распространения часов (примеры см. в разделе [анимации свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) и [анимировать свойство без С помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); часы создаются и распространяются автоматически.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать <xref:System.Windows.Media.Animation.AnimationClock> и применить его к двум аналогичным свойствам.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Пример, показывающий, как управлять в интерактивном режиме <xref:System.Windows.Media.Animation.Clock> после ее запуска в разделе [управление часами в интерактивном режиме](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>См. также  
 [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
