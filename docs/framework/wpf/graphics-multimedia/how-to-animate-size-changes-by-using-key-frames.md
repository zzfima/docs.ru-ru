---
title: "Практическое руководство. Анимация изменений размера с использованием ключевых кадров | Microsoft Docs"
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
  - "анимация, изменение размеров с помощью ключевых кадров"
  - "ключевые кадры, анимация изменения размеров"
  - "изменение размеров, анимация по ключевым кадрам"
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Анимация изменений размера с использованием ключевых кадров
В этом примере показано, как анимировать изменения размера с использованием полных кадров.  
  
## Пример  
 В следующем примере для анимации свойства <xref:System.Windows.Media.ArcSegment.Size%2A> элемента управления <xref:System.Windows.Media.ArcSegment> используется класс <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>.  В этой анимации используются три полных кадра следующим образом:  
  
1.  В течение первой половины секунды анимации используется экземпляр класса <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>, чтобы плавно увеличить размер дуги.  Линейные полные кадры, такие как <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>, создают плавный линейный переход между значениями.  
  
2.  В конце следующей половины секунды используется экземпляр класса <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>, чтобы резко увеличить размер дуги.  Дискретные полные кадры, такие как <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>, создают резкие переходы между значениями, то есть изменения размера происходят внезапно и не остаются незамеченными.  
  
3.  В течение последних двух секунд используется экземпляр класса <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> для увеличения размера дуги.  Полные [сплайновые](GTMT) кадры, такие как <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>, создают переменный переход между значениями в соответствии со значениями свойства <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>.  В этом примере увеличение размера дуги сначала происходит медленно, а затем экспоненциально ускоряется к концу временного сегмента.  
  
 [!code-xml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.ArcSegment.Size%2A>   
 <xref:System.Windows.Media.ArcSegment>   
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)