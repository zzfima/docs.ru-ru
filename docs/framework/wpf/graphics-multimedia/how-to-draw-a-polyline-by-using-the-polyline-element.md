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
ms.locfileid: "33561765"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="e22ae-102">Практическое руководство. Рисование ломаной, используя элемент Polyline</span><span class="sxs-lookup"><span data-stu-id="e22ae-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="e22ae-103">В этом примере показано, как рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью <xref:System.Windows.Shapes.Polyline> элемента.</span><span class="sxs-lookup"><span data-stu-id="e22ae-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="e22ae-104">Чтобы нарисовать ломаной линии, создайте <xref:System.Windows.Shapes.Polyline> элемента и использовать его <xref:System.Windows.Shapes.Polyline.Points%2A> свойство, чтобы указать вершинах фигуры.</span><span class="sxs-lookup"><span data-stu-id="e22ae-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="e22ae-105">Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойства для описания ломаной линии структуры, так как выполняется без внешних проявлений линия без штриха.</span><span class="sxs-lookup"><span data-stu-id="e22ae-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e22ae-106">Поскольку <xref:System.Windows.Shapes.Polyline> элемент не является замкнутой фигуры <xref:System.Windows.Shapes.Shape.Fill%2A> свойство не имеет значения, даже если закрыть намеренно контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="e22ae-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="e22ae-107">Для создания замкнутой фигуры с <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте <xref:System.Windows.Shapes.Polygon> элемента.</span><span class="sxs-lookup"><span data-stu-id="e22ae-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="e22ae-108">В следующем примере рисуется два <xref:System.Windows.Shapes.Polyline> элементов внутри <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e22ae-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e22ae-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e22ae-109">Example</span></span>  
 <span data-ttu-id="e22ae-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек — перечень запятыми координат x и y пары.</span><span class="sxs-lookup"><span data-stu-id="e22ae-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="e22ae-111">Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения ломаных, можно использовать элементы ломаной линии (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.</span><span class="sxs-lookup"><span data-stu-id="e22ae-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="e22ae-112">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="e22ae-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22ae-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e22ae-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="e22ae-114">Пример элементов фигуры</span><span class="sxs-lookup"><span data-stu-id="e22ae-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="e22ae-115">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="e22ae-115">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
