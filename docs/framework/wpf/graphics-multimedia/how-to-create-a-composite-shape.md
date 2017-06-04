---
title: "Практическое руководство. Создание составной фигуры | Microsoft Docs"
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
  - "составные фигуры"
  - "графика, составные фигуры"
  - "фигуры, составной"
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание составной фигуры
В данном примере демонстрируется создание составных фигур с помощью объектов класса <xref:System.Windows.Media.Geometry> и их отображение с помощью элемента <xref:System.Windows.Shapes.Path>.  В примере объекты <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry> и <xref:System.Windows.Media.RectangleGeometry> используются вместе с <xref:System.Windows.Media.GeometryGroup> для создания составной фигуры.  Затем геометрические объекты рисуются с помощью элемента <xref:System.Windows.Shapes.Path>.  
  
## Пример  
 [!code-xml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Составная геометрическая фигура, созданная с использованием GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.png "wcpsdk\_graphicsmm\_compositegeometryexample1")  
Составные геометрические объекты  
  
 Более сложные фигуры, такие как многоугольники и фигуры с фрагментами кривых, можно создать с помощью объекта <xref:System.Windows.Media.PathGeometry>.  Пример, показывающий, как создать фигуру с помощью <xref:System.Windows.Media.PathGeometry>, см. в разделе [Создание фигуры с помощью PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Хотя данный пример отображает фигуру на экране при помощи элемента <xref:System.Windows.Shapes.Path>, объекты <xref:System.Windows.Media.Geometry> также могут использоваться для описания содержимого <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>.  Помимо этого их можно использовать для отсечения и проверки попадания курсора.  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).