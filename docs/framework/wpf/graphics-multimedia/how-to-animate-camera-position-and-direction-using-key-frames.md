---
title: "Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, направление камеры с помощью ключевых кадров"
  - "анимация, позиция камеры с помощью ключевых кадров"
  - "направление камеры, анимация по ключевым кадрам"
  - "позиция камеры, анимация по ключевым кадрам"
  - "ключевые кадры, анимация направления камеры"
  - "ключевые кадры, анимация позиции камеры"
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
В следующем примере <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> используется для анимации положения <xref:System.Windows.Media.Media3D.PerspectiveCamera> в 3D\-сцене.  Кроме того, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для анимации направления камеры, указанного в 3D\-сцене.  Эти анимации используют несколько полных кадров, создающих ряд эффектов анимации:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания резких «прыжков» между значениями \(без интерполяции\).  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для создания переменного перехода между значениями в зависимости от свойства <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>.  В следующем примере анимация начинается медленно, но ближе к концу временного сегмента экспоненциально ускоряется.  
  
## Пример  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## См. также  
 [Анимация положения и направления камеры в трехмерной сцене](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)