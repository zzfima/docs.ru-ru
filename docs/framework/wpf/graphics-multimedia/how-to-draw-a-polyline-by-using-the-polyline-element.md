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
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="7b1ea-102">Практическое руководство. Рисование ломаной, используя элемент Polyline</span><span class="sxs-lookup"><span data-stu-id="7b1ea-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="7b1ea-103">В этом примере показано, как нарисовать ломаную линию, которая представляет собой ряд соединенных линий, с помощью элемента <xref:System.Windows.Shapes.Polyline>.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="7b1ea-104">Чтобы нарисовать ломаную линию, создайте элемент <xref:System.Windows.Shapes.Polyline> и используйте его свойство <xref:System.Windows.Shapes.Polyline.Points%2A> для указания вершин фигуры.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="7b1ea-105">Наконец, используйте свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> для описания контура ломаной линии, так как линия без штриха невидима.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b1ea-106">Поскольку элемент <xref:System.Windows.Shapes.Polyline> не является замкнутой фигурой, свойство <xref:System.Windows.Shapes.Shape.Fill%2A> не действует, даже если намеренно закрывается контур фигуры.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="7b1ea-107">Чтобы создать замкнутую фигуру с <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте элемент <xref:System.Windows.Shapes.Polygon>.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="7b1ea-108">В следующем примере в <xref:System.Windows.Controls.Canvas>рисуются два элемента <xref:System.Windows.Shapes.Polyline>.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b1ea-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7b1ea-109">Example</span></span>  
 <span data-ttu-id="7b1ea-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]допустимым синтаксисом для точек является разделенный пробелами список пар координат x и y с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="7b1ea-111">Хотя в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения ломаных линий, можно использовать элементы ломаной линии (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="7b1ea-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="7b1ea-112">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="7b1ea-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1ea-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7b1ea-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="7b1ea-114">Пример элементов Shape</span><span class="sxs-lookup"><span data-stu-id="7b1ea-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="7b1ea-115">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="7b1ea-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
