---
title: Практическое руководство. Рисование ломаной, используя элемент Polyline
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 2abfa29f7aca4bfc8c5f91e36fd974093a98a9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Практическое руководство. Рисование ломаной, используя элемент Polyline
В этом примере показано, как рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью <xref:System.Windows.Shapes.Polyline> элемента.  
  
 Чтобы нарисовать ломаной линии, создайте <xref:System.Windows.Shapes.Polyline> элемента и использовать его <xref:System.Windows.Shapes.Polyline.Points%2A> свойство, чтобы указать вершинах фигуры. Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойства для описания ломаной линии структуры, так как выполняется без внешних проявлений линия без штриха.  
  
> [!NOTE]
>  Поскольку <xref:System.Windows.Shapes.Polyline> элемент не является замкнутой фигуры <xref:System.Windows.Shapes.Shape.Fill%2A> свойство не имеет значения, даже если закрыть намеренно контура фигуры. Для создания замкнутой фигуры с <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте <xref:System.Windows.Shapes.Polygon> элемента.  
  
 В следующем примере рисуется два <xref:System.Windows.Shapes.Polyline> элементов внутри <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек — перечень запятыми координат x и y пары.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения ломаных, можно использовать элементы ломаной линии (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
