---
title: "Практическое руководство. Анимация точки с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, объектов Point по ключевым кадрам"
  - "ключевые кадры, анимация объектов Point"
  - "Point - объекты, анимация по ключевым кадрам"
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Анимация точки с помощью ключевых кадров
В этом примере показано использование класса <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> для анимации точки <xref:System.Windows.Point>.  
  
## Пример  
 В следующем примере показано перемещение эллипса по треугольному пути.  В примере класс <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> используется для анимации свойства <xref:System.Windows.Media.EllipseGeometry.Center%2A> элемента управления <xref:System.Windows.Media.EllipseGeometry>.  В этой анимации используются три полных кадра следующим образом:  
  
1.  В течение первой половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.LinearPointKeyFrame> для перемещения эллипса по пути с равномерной частотой из начального положения.  Линейные полные кадры, такие как <xref:System.Windows.Media.Animation.LinearPointKeyFrame>, создают плавную линейную интерполяцию по значениям.  
  
2.  В конце следующей половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> для мгновенного перемещения эллипса в следующее положение вдоль пути.  Дискретные полные кадры, такие как <xref:System.Windows.Media.Animation.DiscretePointKeyFrame>, создают резкие переходы между значениями.  
  
3.  В течение последних двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.SplinePointKeyFrame> для возврата эллипса в начальное положение.  Полные кадры со [сплайновой](GTMT) интерполяцией, такие как <xref:System.Windows.Media.Animation.SplinePointKeyFrame>, создают переменный переход между значениями в соответствии со значениями свойства <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>.  В этом примере анимация начинается медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Для совместимости с другими примерами анимации версии кода этого примера используют объект <xref:System.Windows.Media.Animation.Storyboard>, чтобы применить кадры <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.  Однако при применении одной анимации в коде проще использовать метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> вместо <xref:System.Windows.Media.Animation.Storyboard>.  Пример см. в разделе [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## См. также  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.EllipseGeometry>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)