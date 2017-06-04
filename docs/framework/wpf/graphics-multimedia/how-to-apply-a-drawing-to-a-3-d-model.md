---
title: "Практическое руководство. Применение рисования к трехмерной модели | Microsoft Docs"
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
  - "трехмерные модели, применение рисунков к"
  - "объекты рисования, применение к трехмерным моделям"
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Применение рисования к трехмерной модели
В этом примере показано использование <xref:System.Windows.Media.DrawingBrush> в качестве объекта <xref:System.Windows.Media.Media3D.Material>, применяемого к модели [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  
  
 В следующем коде определяется <xref:System.Windows.Media.DrawingGroup> как содержимое объекта <xref:System.Windows.Media.DrawingBrush>.  <xref:System.Windows.Media.DrawingBrush> задается как свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> объекта <xref:System.Windows.Media.Media3D.DiffuseMaterial>, применяемое к [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] плоскости.  
  
 **Примечание.** Часто желательно определить сложные объекты и значения, как на рисунке ниже, в качестве ресурсов, которые могут повторно использоваться и упростить код.  Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)