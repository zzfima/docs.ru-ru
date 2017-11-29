---
title: "Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbac99770b5cbb7dacb0468e1a892956fda6b79c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
В следующем примере <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> используется для анимации положения <xref:System.Windows.Media.Media3D.PerspectiveCamera> в трехмерной сцене. Кроме того <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для направления в трехмерной сцене указывает камера. Эти анимации используйте несколько ключевых кадров, создающих ряд эффектов анимации.  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания резкие «переходы» между значениями (без интерполяции).  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для создания переменного перехода между значениями в зависимости от <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> свойство. В следующем примере анимация начинается медленно, но ближе к концу временного отрезка, экспоненциально ускоряется.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Анимация положения и направления камеры в трехмерной сцене](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
