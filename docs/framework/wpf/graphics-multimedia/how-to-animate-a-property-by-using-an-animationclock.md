---
title: "Практическое руководство. Анимирование свойства с помощью AnimationClock | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, свойства, с помощью AnimationClock"
  - "AnimationClock"
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Анимирование свойства с помощью AnimationClock
В этом примере показано использование объектов <xref:System.Windows.Media.Animation.Clock> для анимации свойства.  
  
 Существует три способа анимации [свойства зависимостей](GTMT):  
  
-   Создание <xref:System.Windows.Media.Animation.AnimationTimeline> и его соединение с этим свойством при помощи <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Использование метода объекта <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> для применения одного <xref:System.Windows.Media.Animation.AnimationTimeline> к целевому свойству.  
  
-   Создание <xref:System.Windows.Media.Animation.AnimationClock> из <xref:System.Windows.Media.Animation.AnimationTimeline> и применение его к свойству.  
  
 Объекты <xref:System.Windows.Media.Animation.Storyboard> и метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> позволяют анимировать свойства без непосредственного создания и распространения часов \(примеры см. в разделе [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)\); часы создаются и распространяются автоматически.  
  
## Пример  
 В следующем примере показано создание <xref:System.Windows.Media.Animation.AnimationClock> и применение его к двум аналогичным свойствам.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Пример, показывающий управление элементом <xref:System.Windows.Media.Animation.Clock> в интерактивном режиме после его запуска, см. в разделе [Управление часами в интерактивном режиме](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## См. также  
 [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)