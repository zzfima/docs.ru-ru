---
title: "Практическое руководство. Анимация 3-D вращения с помощью опорных кадров | Microsoft Docs"
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
  - "трехмерные преобразования, анимирование, с помощью ключевых кадров (Rotation3DAnimation)"
  - "анимация, трехмерные преобразования, с помощью ключевых кадров (Rotation3DAnimation)"
  - "ключевые кадры, Rotation3DAnimation"
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимация 3-D вращения с помощью опорных кадров
В следующем примере используется коллекция объектов <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>, чтобы заставить вращаться трехмерный объект, в то время как его ось вращения, в результате анимации, "качается".  Эта анимация использует следующие полные кадры:  
  
1.  Объект <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> используется для создания гладкой, линейной интерполяции между значениями.  
  
2.  Объект <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> используется для создания случайных переходов между значениями \(без интерполяции\).  
  
3.  Объект <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> используется для создания переменного перехода между значениями, в зависимости от свойства <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>.  В представленном ниже примере эта часть анимации начинается медленно, но ближе к концу сегмента времени экспоненциально ускоряется.  
  
## Пример  
 [!code-xml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## См. также  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Анимация трехмерного вращения с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Анимация трехмерного поворота с помощью Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Анимация трехмерного вращения с помощью кватернионов](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Анимация трехмерного поворота с помощью ключевых кадров \(QuaternionAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)