---
title: Практическое руководство. Рисование ломаной с помощью элемента Polyline
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934961"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Практическое руководство. Рисование ломаной с помощью элемента Polyline
В этом примере показано, как нарисовать ломаную линию, которая представляет собой ряд соединенных линий, с <xref:System.Windows.Shapes.Polyline> помощью элемента.  
  
 Чтобы нарисовать ломаную линию, <xref:System.Windows.Shapes.Polyline> создайте элемент и используйте <xref:System.Windows.Shapes.Polyline.Points%2A> его свойство, чтобы указать вершины фигур. Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> свойства и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> для описания контура ломаной линии, так как линия без штриха невидима.  
  
> [!NOTE]
> Поскольку элемент не является замкнутой фигурой <xref:System.Windows.Shapes.Shape.Fill%2A> , свойство не действует, даже если намеренно закрывается контур фигуры. <xref:System.Windows.Shapes.Polyline> Чтобы создать замкнутую фигуру с <xref:System.Windows.Shapes.Shape.Fill%2A>помощью, <xref:System.Windows.Shapes.Polygon> используйте элемент.  
  
 В следующем примере рисуются <xref:System.Windows.Shapes.Polyline> два элемента <xref:System.Windows.Controls.Canvas>внутри.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]допустимый синтаксис для точек — это разделенный пробелами список пар координат x и y с разделителями-запятыми.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Хотя в этом примере используется <xref:System.Windows.Controls.Canvas> объект для размещения ломаных линий, можно использовать элементы ломаной линии (и все остальные элементы Shape) <xref:System.Windows.Controls.Panel> с <xref:System.Windows.Controls.Control> любым или, поддерживающим нетекстовое содержимое.  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Пример элементов Shape](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
