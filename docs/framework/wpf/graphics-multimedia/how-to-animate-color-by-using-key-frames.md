---
title: "Практическое руководство. Анимация цвета с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, цветов по ключевым кадрам"
  - "цвета, анимация по ключевым кадрам"
  - "ключевые кадры, анимация цветов"
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Анимация цвета с помощью ключевых кадров
В этом примере показана анимация цвета <xref:System.Windows.Media.SolidColorBrush.Color%2A> объекта <xref:System.Windows.Media.SolidColorBrush> с помощью полных кадров.  
  
## Пример  
 В следующем примере для анимации цвета <xref:System.Windows.Media.SolidColorBrush.Color%2A> кисти <xref:System.Windows.Media.SolidColorBrush> используется класс <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>.  В этой анимации используются три полных кадра следующим образом:  
  
1.  В течение первых двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.LinearColorKeyFrame> для постепенного изменение цвета от зеленого к красному.  Линейные полные кадры, такие как <xref:System.Windows.Media.Animation.LinearColorKeyFrame>, создают гладкий линейный переход между значениями.  
  
2.  Во время окончания следующей половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> для быстрого изменения цвета с красного на желтый.  Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> совершают мгновенные переходы между значениями, т. е. изменение цвета в этой части анимации происходит быстро, но заметно.  
  
3.  В течение последних двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.SplineColorKeyFrame> для обратного преобразования цвета — на этот раз от желтого к зеленому.  Полные [сплайновые](GTMT) кадры, такие как <xref:System.Windows.Media.Animation.SplineColorKeyFrame>, создают переменный переход между значениями в соответствии со значениями свойства <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>.  В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)