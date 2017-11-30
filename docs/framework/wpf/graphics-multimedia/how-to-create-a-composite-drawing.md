---
title: "Как создать составной рисунок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7789f9aa94db32d3dc61ccf01ef9ddfe1e777a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-composite-drawing"></a>Как создать составной рисунок
В этом примере показано, как использовать <xref:System.Windows.Media.DrawingGroup> для создания сложных рисунков путем объединения нескольких <xref:System.Windows.Media.Drawing> объектов в один составной рисунок.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.DrawingGroup> для создания составного рисунка из <xref:System.Windows.Media.GeometryDrawing> и <xref:System.Windows.Media.ImageDrawing> объектов. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
Составной рисунок, который создается с помощью DrawingGroup  
  
 Обратите внимание, серую границу, которая обозначает границы рисунка.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Можно использовать <xref:System.Windows.Media.DrawingGroup> для применения <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> параметр <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, или <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> к рисункам. Поскольку <xref:System.Windows.Media.DrawingGroup> также <xref:System.Windows.Media.Drawing>, он может содержать другие <xref:System.Windows.Media.DrawingGroup> объекты.  
  
 Следующий пример похож на предыдущем примере, за исключением того, что он использует дополнительные <xref:System.Windows.Media.DrawingGroup> объектов для применения эффектов растрового изображения и маски непрозрачности к некоторым из его рисунков. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
Составной рисунок, состоящий из нескольких объектов DrawingGroup  
  
 Обратите внимание, серую границу, которая обозначает границы рисунка.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, в разделе [Общие сведения об объектах Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
