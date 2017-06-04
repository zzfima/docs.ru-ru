---
title: "Как создать составной рисунок | Microsoft Docs"
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
  - "классы, DrawingGroup"
  - "составные рисунки"
  - "DrawingGroup - класс"
  - "объекты рисования, составной"
  - "графика, составные рисунки"
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Как создать составной рисунок
В этом примере показано использование объекта <xref:System.Windows.Media.DrawingGroup> для создания сложных рисунков путем объединения нескольких объектов <xref:System.Windows.Media.Drawing> в один составной рисунок.  
  
## Пример  
 В следующем примере используется объект <xref:System.Windows.Media.DrawingGroup> для создания составного рисунка из объектов <xref:System.Windows.Media.GeometryDrawing> и <xref:System.Windows.Media.ImageDrawing>.  На следующем рисунке показан результат данного примера.  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
Составной рисунок, созданный с помощью DrawingGroup  
  
 Обратите внимание на серую границу, которая обозначает границы рисунка.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Можно использовать объект <xref:System.Windows.Media.DrawingGroup> для применения к рисункам <xref:System.Windows.Media.DrawingGroup.Transform%2A>, параметра <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> или <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>.  Так как <xref:System.Windows.Media.DrawingGroup> является также объектом <xref:System.Windows.Media.Drawing>, он может содержать другие объекты <xref:System.Windows.Media.DrawingGroup>.  
  
 Следующий пример аналогичен предыдущему, за исключением того, что он использует дополнительные объекты <xref:System.Windows.Media.DrawingGroup> для применения к некоторым из его рисунков эффектов точеного рисунка и установки маски прозрачности.  На следующем рисунке показан результат данного примера.  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.png "graphicsmm\_multiple")  
Составной рисунок, состоящий из нескольких объектов DrawingGroup  
  
 Обратите внимание на серую границу, которая обозначает границы рисунка.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>   
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>   
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>   
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>   
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>   
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)