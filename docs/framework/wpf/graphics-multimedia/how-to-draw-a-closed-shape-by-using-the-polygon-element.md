---
title: Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452978"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"
В этом примере показано, как нарисовать замкнутую фигуру с помощью элемента <xref:System.Windows.Shapes.Polygon>. Чтобы нарисовать замкнутую фигуру, создайте элемент <xref:System.Windows.Shapes.Polygon> и используйте его свойство <xref:System.Windows.Shapes.Polygon.Points%2A> для указания вершин фигуры. Автоматически рисуется линия, соединяющая первую и последнюю точки. Наконец, укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>или и то, и другое.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]допустимым синтаксисом для точек является разделенный пробелами список пар координат x и y с разделителями-запятыми.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Несмотря на то, что в примере используется <xref:System.Windows.Controls.Canvas> для размещения многоугольников, можно использовать элементы многоугольников (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).
