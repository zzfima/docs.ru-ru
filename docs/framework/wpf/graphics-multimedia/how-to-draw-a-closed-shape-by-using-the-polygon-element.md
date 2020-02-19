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
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="ecca3-102">Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"</span><span class="sxs-lookup"><span data-stu-id="ecca3-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="ecca3-103">В этом примере показано, как нарисовать замкнутую фигуру с помощью элемента <xref:System.Windows.Shapes.Polygon>.</span><span class="sxs-lookup"><span data-stu-id="ecca3-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="ecca3-104">Чтобы нарисовать замкнутую фигуру, создайте элемент <xref:System.Windows.Shapes.Polygon> и используйте его свойство <xref:System.Windows.Shapes.Polygon.Points%2A> для указания вершин фигуры.</span><span class="sxs-lookup"><span data-stu-id="ecca3-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="ecca3-105">Автоматически рисуется линия, соединяющая первую и последнюю точки.</span><span class="sxs-lookup"><span data-stu-id="ecca3-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="ecca3-106">Наконец, укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="ecca3-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecca3-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ecca3-107">Example</span></span>  
 <span data-ttu-id="ecca3-108">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]допустимым синтаксисом для точек является разделенный пробелами список пар координат x и y с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="ecca3-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="ecca3-109">Несмотря на то, что в примере используется <xref:System.Windows.Controls.Canvas> для размещения многоугольников, можно использовать элементы многоугольников (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="ecca3-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="ecca3-110">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="ecca3-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
