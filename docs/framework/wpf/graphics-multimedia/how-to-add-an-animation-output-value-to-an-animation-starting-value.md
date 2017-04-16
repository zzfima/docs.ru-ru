---
title: "Практическое руководство. Добавление выходного значения анимации к начальному значению анимации | Microsoft Docs"
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
  - "анимация"
  - "IsAdditive - свойство"
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Добавление выходного значения анимации к начальному значению анимации
В этом примере описывается порядок добавления выходного значения анимации к начальному значению анимации.  
  
## Пример  
 Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> определяет необходимость добавления выходного значения анимации к начальному \(базовому\) значению анимированного свойства.  Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> можно использовать с большинством базовых анимаций и с большинством анимаций по ключевым кадрам.  Дополнительные сведения см. в разделах [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В следующем примере показан эффект от использования свойства <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=fullName> с объектом класса <xref:System.Windows.Media.Animation.DoubleAnimation> и свойства <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=fullName> с объектом класса <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## См. также  
 [Накапливание значений анимации в повторяющихся циклах](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)