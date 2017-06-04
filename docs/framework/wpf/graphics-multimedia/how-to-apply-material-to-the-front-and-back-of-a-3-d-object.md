---
title: "Практическое руководство. Применение материала к лицевой и обратной стороне трехмерного объекта | Microsoft Docs"
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
  - "трехмерные объекты, применение класса Material"
  - "классы, Материал"
  - "Material - класс, применение к обеим сторонам трехмерного объекта"
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Применение материала к лицевой и обратной стороне трехмерного объекта
В следующем примере демонстрируется применение материала <xref:System.Windows.Media.Media3D.Material> к лицевой и обратной стороне трехмерного объекта и анимация объекта для отображения обеих сторон.  Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> класса <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения красной кисти <xref:System.Windows.Media.Brush> к лицевой стороне объекта, а свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> класса <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения синей кисти <xref:System.Windows.Media.Brush> к обратной стороне объекта.  Следующий код демонстрирует применение материалов к объекту:  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## См. также  
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Анимация свойств материалов в трехмерной сцене](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [Применение эмиссионного материала к трехмерному объекту](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)