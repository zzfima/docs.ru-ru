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
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452965"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Практическое руководство. Рисование ломаной, используя элемент Polyline
В этом примере показано, как нарисовать ломаную линию, которая представляет собой ряд соединенных линий, с помощью элемента <xref:System.Windows.Shapes.Polyline>.  
  
 Чтобы нарисовать ломаную линию, создайте элемент <xref:System.Windows.Shapes.Polyline> и используйте его свойство <xref:System.Windows.Shapes.Polyline.Points%2A> для указания вершин фигуры. Наконец, используйте свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> для описания контура ломаной линии, так как линия без штриха невидима.  
  
> [!NOTE]
> Поскольку элемент <xref:System.Windows.Shapes.Polyline> не является замкнутой фигурой, свойство <xref:System.Windows.Shapes.Shape.Fill%2A> не действует, даже если намеренно закрывается контур фигуры. Чтобы создать замкнутую фигуру с <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте элемент <xref:System.Windows.Shapes.Polygon>.  
  
 В следующем примере в <xref:System.Windows.Controls.Canvas>рисуются два элемента <xref:System.Windows.Shapes.Polyline>.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]допустимым синтаксисом для точек является разделенный пробелами список пар координат x и y с разделителями-запятыми.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Хотя в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения ломаных линий, можно использовать элементы ломаной линии (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
