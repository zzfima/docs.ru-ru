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
ms.openlocfilehash: d065d3cead1ed9746a9615ce2bb6d3ec4cbd614d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855434"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Практическое руководство. Рисование ломаной, используя элемент Polyline
В этом примере показано, как рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью <xref:System.Windows.Shapes.Polyline> элемент.  
  
 Чтобы Рисование ломаной, создайте <xref:System.Windows.Shapes.Polyline> элемента и использование его <xref:System.Windows.Shapes.Polyline.Points%2A> свойство, чтобы указать вершины фигуры. Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойств, описывающих ломаной линии структуры, так как в строку без штриха является невидимым.  
  
> [!NOTE]
>  Так как <xref:System.Windows.Shapes.Polyline> элемент не является замкнутой фигуры, <xref:System.Windows.Shapes.Shape.Fill%2A> не оказывает никакого влияния, даже если намеренно закрыть контура фигуры. Для создания замкнутой фигуры с <xref:System.Windows.Shapes.Shape.Fill%2A>, использовать <xref:System.Windows.Shapes.Polygon> элемент.  
  
 В следующем примере рисуется два <xref:System.Windows.Shapes.Polyline> элементов внутри <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек является список с разделителями запятыми координат x и y пар.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> должен содержать ломаные линии, можно использовать элементы polyline (и все остальные элементы фигуры) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающий нетекстовое содержимое.  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037)  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
