---
title: "Практическое руководство. Анимация расположения объекта с помощью PointAnimation | Microsoft Docs"
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
  - "анимация, PointAnimation"
  - "классы, PointAnimation"
  - "графика [WPF], анимация"
  - "PointAnimation - класс"
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Анимация расположения объекта с помощью PointAnimation
В этом примере показано использование класса <xref:System.Windows.Media.Animation.PointAnimation> для анимации объекта вдоль <xref:System.Windows.Shapes.Path>.  
  
## Пример  
 В следующем примере эллипс перемещается вдоль <xref:System.Windows.Shapes.Path> от одной точки на экране к другой.  Пример анимирует положение <xref:System.Windows.Media.EllipseGeometry> с помощью <xref:System.Windows.Media.Animation.PointAnimation> для анимации свойства <xref:System.Windows.Media.EllipseGeometry.Center%2A>.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## См. также  
 <xref:System.Windows.Media.Animation.PointAnimation>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.EllipseGeometry>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)