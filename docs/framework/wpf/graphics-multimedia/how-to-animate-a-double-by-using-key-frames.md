---
title: "Инструкция по Анимации типа Double с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, Double по ключевым кадрам"
  - "Двойные, анимация по ключевым кадрам"
  - "ключевые кадры, анимация Double по"
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Инструкция по Анимации типа Double с помощью ключевых кадров
В этом примере демонстрируется анимация значения свойства, которое принимает <xref:System.Double> с помощью полных кадров.  
  
## Пример  
 В следующем примере прямоугольник перемещается по экрану.  В примере используется класс <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> для анимации свойства <xref:System.Windows.Media.TranslateTransform.X%2A> из <xref:System.Windows.Media.TranslateTransform>, примененного к <xref:System.Windows.Shapes.Rectangle>.  Эта анимация, которая повторяется бесконечно, использует три полных кадра следующим способом:  
  
1.  В течение первых трех секунд используется экземпляр класса <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> для перемещения прямоугольника по пути с равномерной скоростью от его начальной позиции в позицию 500.  Линейные полные кадры, такие как <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> создают гладкий линейный переход между значениями.  
  
2.  В конце четвертый секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> для мгновенного перемещения прямоугольника к следующей позиции.  Дискретные полные кадры, такие как <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> создают резкие переходы между значениями.  В этом примере прямоугольник находится в начальной позиции и затем внезапно появляется в позиции 500.  
  
3.  В последние две секунды используется экземпляр класса <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> чтобы возвратить прямоугольник назад, в его начальное положение.  Полные кадры [Spline](GTMT) такие, как <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> создают изменяющийся переход между значениями согласно значению свойства <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>.  В этом примере прямоугольник начинает перемещаться медленно и затем экспоненциально ускоряется к концу временного сегмента.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Для совместимости с другими примерами анимации версии кода этого примера используют объект <xref:System.Windows.Media.Animation.Storyboard>, чтобы применить <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  Альтернативно, когда применяется единственная анимация в коде, проще использовать метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> вместо использования <xref:System.Windows.Media.Animation.Storyboard>.  Пример см. в разделе [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## См. также  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Shapes.Rectangle>   
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)