---
title: "Как анимировать 3-D поворот с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames) | Microsoft Docs"
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
  - "трехмерные преобразования, анимирование, по ключевым кадрам (QuaternionAnimationUsingKeyFrames)"
  - "анимация, трехмерные преобразования, по ключевым кадрам (QuaternionAnimationUsingKeyFrames)"
  - "ключевые кадры, QuaternionAnimationUsingKeyFrames"
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Как анимировать 3-D поворот с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)
В следующем примере используется <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>, чтобы выполнить поворот 3\-D объекта.  Эта анимация использует следующие полные кадры:  
  
1.  Объект <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> используется для создания гладкой, линейной интерполяции между значениями.  
  
2.  Объект <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> используется для создания случайных переходов между значениями \(без интерполяции\).  
  
3.  Объект <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> используется для создания переменного перехода между значениями, в зависимости от свойства <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>.  В представленном ниже примере эта часть анимации начинается медленно, но ближе к концу сегмента времени экспоненциально ускоряется.  
  
## Пример  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## См. также  
 [Анимация трехмерного вращения с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Анимация трехмерного поворота с помощью Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Анимация трехмерного вращения с помощью кватернионов](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Анимация трехмерного поворота с помощью ключевых кадров \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)