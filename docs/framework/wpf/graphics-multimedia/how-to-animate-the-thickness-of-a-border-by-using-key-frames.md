---
title: "Инструкция по Анимации толщины границы с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, толщины границы по ключевым кадрам"
  - "граница - толщина, анимация по ключевым кадрам"
  - "ключевые кадры, анимация толщины границы по"
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Инструкция по Анимации толщины границы с помощью ключевых кадров
В этом примере демонстрируется анимация свойства <xref:System.Windows.Controls.Control.BorderThickness%2A> элемента <xref:System.Windows.Controls.Border>.  
  
## Пример  
 В следующем примере для анимации свойства <xref:System.Windows.Controls.Control.BorderThickness%2A> элемента управления <xref:System.Windows.Controls.Border> используется класс <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>.  В этой анимации используются три полных кадра следующим образом:  
  
1.  В течение первой половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> для плавного увеличения толщины границы.  Пример использует <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> для создания гладкого линейного увеличения между значениями.  
  
2.  В конце следующей половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> для мгновенного увеличения толщины границы.  Дискретные полные кадры, как производные от <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>, создают внезапные переходы между значениями, т. е. движение анимации тряское.  
  
3.  В течение последних двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> для уменьшения толщины границы.  Полные кадры [Spline](GTMT), как производные <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>, создают переменный переход между значениями согласно значениям свойства <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>.  В этом ключевом кадре анимация начинается медленно и ускоряется экспоненциально к концу временного сегмента.  
  
 [!code-xml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Анимирование значения BorderThickness](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)