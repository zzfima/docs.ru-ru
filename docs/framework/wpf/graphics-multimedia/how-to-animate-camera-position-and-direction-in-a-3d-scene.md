---
title: "Практическое руководство. Изменение положения и направления камеры в 3D-сцене | Microsoft Docs"
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
  - "трехмерные сцены, анимация направления камеры"
  - "трехмерные сцены, анимация позиции камеры"
  - "анимация, направление камеры в трехмерных сценах"
  - "анимация, позиция камеры в трехмерных сценах"
  - "направление камеры, анимация в трехмерных сценах"
  - "позиция камеры, анимация в трехмерных сценах"
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Изменение положения и направления камеры в 3D-сцене
В следующем примере демонстрируется анимация положения и направления камеры в 3D\-сцене.  Это выполняется с помощью <xref:System.Windows.Media.Animation.Point3DAnimation> и <xref:System.Windows.Media.Animation.Vector3DAnimation> для анимации соответствующих свойств <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> и <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> из <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  Подобную анимацию можно использовать для изменения обзора сцены со стороны наблюдателя при возникновении события.  
  
## Пример  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>   
 <xref:System.Windows.Media.Animation.Point3DAnimation>   
 [Анимация положения и направления камеры с помощью ключевых кадров](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)