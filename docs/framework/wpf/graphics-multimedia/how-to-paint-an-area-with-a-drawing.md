---
title: "Практическое руководство. Закраска области рисованием"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbb7c4aff56fae9b4cc0346f8086bc490269ec8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Практическое руководство. Закраска области рисованием
Этот пример показывает, как можно закрасить область рисунком. Закраска области с помощью drawing, использовании <xref:System.Windows.Media.DrawingBrush> и один или несколько <xref:System.Windows.Media.Drawing> объектов.   В следующем примере используется <xref:System.Windows.Media.DrawingBrush> для рисования объекта рисованием двух эллипсов.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Результат DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")  
  
 (Центр фигуры является белым, по причинам описано в [управление заливкой составных фигур](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)  
  
 Установив <xref:System.Windows.Media.DrawingBrush> объекта <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства, можно создать повторяющийся рисунок. Следующий пример выполняет заливку объекта шаблоном, созданным рисунком из двух эллипсов.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 На следующем рисунке показан закраски <xref:System.Windows.Media.DrawingBrush> выходных данных.  
  
 ![Мозаичный результат работы DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")  
  
 Дополнительные сведения о закраске рисованием см. в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md). Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, в разделе [Общие сведения об объектах Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).
