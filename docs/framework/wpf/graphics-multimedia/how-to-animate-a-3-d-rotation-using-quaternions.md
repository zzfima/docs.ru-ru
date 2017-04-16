---
title: "Практическое руководство. Анимация трехмерного вращения с помощью кватернионов | Microsoft Docs"
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
  - "трехмерные преобразования, анимирование, с помощью кватернионов"
  - "анимация, трехмерные преобразования, с помощью кватернионов"
  - "кватернионы"
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Анимация трехмерного вращения с помощью кватернионов
В этом примере демонстрируется анимация поворота трехмерного объекта с помощью кватернионов.  
  
 В следующем примере кода <xref:System.Windows.Media.Media3D.QuaternionRotation3D> используется в качестве значения для свойства <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> класса <xref:System.Windows.Media.Media3D.RotateTransform3D>.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Это трехмерное вращение <xref:System.Windows.Media.Media3D.QuaternionRotation3D> анимируется с помощью <xref:System.Windows.Media.Animation.QuaternionAnimation> внутри <xref:System.Windows.Media.Animation.Storyboard> с использованием следующего кода.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Анимация трехмерного вращения с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Анимация трехмерного поворота с помощью Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)