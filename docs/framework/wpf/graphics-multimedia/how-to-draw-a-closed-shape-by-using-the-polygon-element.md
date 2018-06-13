---
title: Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 4105139e159783cf0197f4e56c82001835077cbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559466"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="97164-102">Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"</span><span class="sxs-lookup"><span data-stu-id="97164-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="97164-103">В этом примере показано, как Рисование замкнутой фигуры с помощью <xref:System.Windows.Shapes.Polygon> элемента.</span><span class="sxs-lookup"><span data-stu-id="97164-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="97164-104">Чтобы нарисовать замкнутую фигуру, создайте <xref:System.Windows.Shapes.Polygon> элемента и использовать его <xref:System.Windows.Shapes.Polygon.Points%2A> свойство, чтобы указать вершинах фигуры.</span><span class="sxs-lookup"><span data-stu-id="97164-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="97164-105">Автоматически отображается линия, соединяющая точки первым и последним.</span><span class="sxs-lookup"><span data-stu-id="97164-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="97164-106">Наконец, укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, или оба.</span><span class="sxs-lookup"><span data-stu-id="97164-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97164-107">Пример</span><span class="sxs-lookup"><span data-stu-id="97164-107">Example</span></span>  
 <span data-ttu-id="97164-108">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек — перечень запятыми координат x и y пары.</span><span class="sxs-lookup"><span data-stu-id="97164-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="97164-109">Несмотря на то, что в этом примере <xref:System.Windows.Controls.Canvas> для хранения многоугольников, можно использовать элементы многоугольника (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.</span><span class="sxs-lookup"><span data-stu-id="97164-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="97164-110">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="97164-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
