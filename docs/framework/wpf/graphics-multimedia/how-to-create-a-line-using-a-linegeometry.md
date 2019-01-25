---
title: Как выполнить Создание линии с помощью LineGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: fbf44f627ede0fe3bdf7e629728a1e3b858fd30e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690570"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Как выполнить Создание линии с помощью LineGeometry
В этом примере показано, как использовать <xref:System.Windows.Media.LineGeometry> класс, который описывает строку. Объект <xref:System.Windows.Media.LineGeometry> определяется его начальную и конечную точки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать и отобразить <xref:System.Windows.Media.LineGeometry>.  Объект <xref:System.Windows.Shapes.Path> элемент используется для отображения линии.  Поскольку линия не имеет площади, <xref:System.Windows.Shapes.Path> объекта <xref:System.Windows.Shapes.Shape.Fill%2A> не задан; вместо этого <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> используются свойства.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Объект LineGeometry, соединяющий точки (10,20) и (100,130)  
  
 Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>. Эти геометрические объекты, а также более сложные, могут также создаваться с использованием <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>. Дополнительные сведения см. в разделе [Общие сведения о геометрии](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>См. также
- [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Создание фигуры с помощью объекта PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
