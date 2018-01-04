---
title: "Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry"
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
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a8254bd60da379d006bc50ab3a935cd83b83d0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry
В этом примере описывается использование <xref:System.Windows.Media.RectangleGeometry> класса для описания прямоугольник.  
  
## <a name="example"></a>Пример  
 В следующем примере показано создание и отображение <xref:System.Windows.Media.RectangleGeometry>.  Относительное положение и размеры прямоугольника определяются <xref:System.Windows.Rect> структуры. Относительное положение устанавливается `50,50` и высоту и ширину `25` создает квадрат. Рисования внутренней прямоугольника с <xref:System.Windows.Media.Brushes.LemonChiffon%2A> кисти и его контура отрисовывается с <xref:System.Windows.Media.Brushes.Black%2A> штриха толщиной `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Практическое руководство](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Shapes.Path> элемента для визуализации <xref:System.Windows.Media.RectangleGeometry>, существует множество способов для использования <xref:System.Windows.Media.RectangleGeometry> объектов. Например <xref:System.Windows.Media.RectangleGeometry> может использоваться для указания <xref:System.Windows.UIElement.Clip%2A> из <xref:System.Windows.UIElement> или <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> из <xref:System.Windows.Media.GeometryDrawing>.  
  
 Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>. Эти геометрические объекты, а также более сложные, можно также создать с помощью <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Создание фигуры с помощью объекта PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
