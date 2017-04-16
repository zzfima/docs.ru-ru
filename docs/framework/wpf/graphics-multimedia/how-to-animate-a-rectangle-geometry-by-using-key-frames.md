---
title: "Практическое руководство. Анимация прямоугольника с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, объектов RectangleGeometry с помощью ключевых кадров"
  - "ключевые кадры, анимация объектов RectangleGeometry"
  - "RectangleGeometry - объекты, анимация по ключевым кадрам"
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
В этом примере демонстрируется анимация свойства <xref:System.Windows.Media.RectangleGeometry.Rect%2A> элемента управления <xref:System.Windows.Media.RectangleGeometry> с помощью полных кадров.  
  
## Пример  
 В следующем примере для анимации свойства <xref:System.Windows.Media.RectangleGeometry.Rect%2A> элемента управления <xref:System.Windows.Media.RectangleGeometry> используется класс <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>.  В этой анимации используются три полных кадра следующим образом:  
  
1.  В течение первых двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.LinearRectKeyFrame> для анимации постепенного изменения позиции, ширины и высоты прямоугольника.  Линейные полные кадры, такие как <xref:System.Windows.Media.Animation.LinearRectKeyFrame>, создают гладкий линейный переход между значениями.  
  
2.  Во время окончания следующей половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> для внезапного уменьшения высоты прямоугольника.  Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> совершают мгновенные переходы между значениями, т. е. уменьшение высоты происходит быстро, но заметно.  
  
3.  В течение последних двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.SplineRectKeyFrame> для обратного преобразования прямоугольника к исходному размеру и расположению.  Полные [сплайновые](GTMT) кадры, такие как <xref:System.Windows.Media.Animation.SplineRectKeyFrame>, создают переменный переход между значениями в соответствии со значениями свойства <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>.  В этом примере изменение начинается медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.RectangleGeometry>   
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>   
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)