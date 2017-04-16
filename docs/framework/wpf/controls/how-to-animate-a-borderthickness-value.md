---
title: "Практическое руководство. Анимирование значения BorderThickness | Microsoft Docs"
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
  - "анимация, изменение толщины границ"
  - "граница - толщина, изменение в анимации"
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимирование значения BorderThickness
В этом примере демонстрируется анимация изменений толщины границы с помощью класса <xref:System.Windows.Media.Animation.ThicknessAnimation>.  
  
## Пример  
 В следующем примере анимируется толщина границы с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation>.  В примере используется свойство <xref:System.Windows.Controls.Border.BorderThickness%2A> элемента управления <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Полный пример см. на веб\-странице [Галерея примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## См. также  
 <xref:System.Windows.Media.Animation.ThicknessAnimation>   
 <xref:System.Windows.Controls.Border.BorderThickness%2A>   
 <xref:System.Windows.Controls.Border>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Анимация толщины границы с помощью ключевых кадров](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)