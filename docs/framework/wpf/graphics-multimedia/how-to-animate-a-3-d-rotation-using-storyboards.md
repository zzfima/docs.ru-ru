---
title: "Практическое руководство. Анимация трехмерного вращения с помощью раскадровки | Microsoft Docs"
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
  - "трехмерные преобразования, анимирование, с раскадровками"
  - "анимация, трехмерные преобразования, с раскадровками"
  - "Раскадровки"
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Анимация трехмерного вращения с помощью раскадровки
В следующем примере показано, как заставить трехмерный объект вращаться во время его «качания», с помощью анимации свойств <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> и <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> объекта <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>.  Этот объект <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> задает преобразование вращения трехмерного объекта, поэтому анимирование его свойств приведет к созданию желаемого эффекта вращения.  В раскадровке <xref:System.Windows.Media.Animation.DoubleAnimation> используется для анимации свойства <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>, в то время как <xref:System.Windows.Media.Animation.Vector3DAnimation> используется для анимации свойства <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>.  
  
## Пример  
 [!code-xml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## См. также  
 [Анимация трехмерного поворота с помощью Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Анимация трехмерного поворота с помощью ключевых кадров \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)