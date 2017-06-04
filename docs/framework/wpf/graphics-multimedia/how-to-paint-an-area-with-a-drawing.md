---
title: "Практическое руководство. Закраска области рисованием | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "кисти, рисование с помощью рисунков"
  - "объекты рисования, рисование с помощью"
  - "рисование, с помощью рисунков"
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Закраска области рисованием
В этом примере демонстрируется закраска области с помощью рисования.  Для закраски области с помощью рисования используется <xref:System.Windows.Media.DrawingBrush> и один или несколько объектов <xref:System.Windows.Media.Drawing>.  В следующем примере <xref:System.Windows.Media.DrawingBrush> используется для закраски объекта с помощью рисования двух эллипсов.  
  
## Пример  
 [!code-xml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 Следующий рисунок демонстрирует результат примера.  
  
 ![Вывод из DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm\_drawingbrush\_simple")  
  
 \(Центр фигуры является белым по причинам, описанным в разделе [Управление заливкой составных фигур](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).\)  
  
 Установив свойства <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> объекта <xref:System.Windows.Media.DrawingBrush>, можно создать повторяющийся узор.  В следующем примере объект закрашивается шаблонным узором, созданным рисованием двух эллипсов.  
  
 [!code-xml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 На следующем рисунке показан результат закраски <xref:System.Windows.Media.DrawingBrush> повторяющимся узором.  
  
 ![Мозаичный вывод из DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm\_drawingbrush\_tiled")  
  
 Дополнительные сведения о закраске рисованием см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).