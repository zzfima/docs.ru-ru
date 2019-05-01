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
ms.openlocfilehash: 4f55ecc206be0ef4947923047e796c36131c70ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003214"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="01e4d-102">Практическое руководство. Рисование ломаной с помощью элемента Polyline</span><span class="sxs-lookup"><span data-stu-id="01e4d-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="01e4d-103">В этом примере показано, как рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью <xref:System.Windows.Shapes.Polyline> элемент.</span><span class="sxs-lookup"><span data-stu-id="01e4d-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="01e4d-104">Чтобы Рисование ломаной, создайте <xref:System.Windows.Shapes.Polyline> элемента и использование его <xref:System.Windows.Shapes.Polyline.Points%2A> свойство, чтобы указать вершины фигуры.</span><span class="sxs-lookup"><span data-stu-id="01e4d-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="01e4d-105">Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойств, описывающих ломаной линии структуры, так как в строку без штриха является невидимым.</span><span class="sxs-lookup"><span data-stu-id="01e4d-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01e4d-106">Так как <xref:System.Windows.Shapes.Polyline> элемент не является замкнутой фигуры, <xref:System.Windows.Shapes.Shape.Fill%2A> не оказывает никакого влияния, даже если намеренно закрыть контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="01e4d-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="01e4d-107">Для создания замкнутой фигуры с <xref:System.Windows.Shapes.Shape.Fill%2A>, использовать <xref:System.Windows.Shapes.Polygon> элемент.</span><span class="sxs-lookup"><span data-stu-id="01e4d-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="01e4d-108">В следующем примере рисуется два <xref:System.Windows.Shapes.Polyline> элементов внутри <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="01e4d-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01e4d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="01e4d-109">Example</span></span>  
 <span data-ttu-id="01e4d-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек является список с разделителями запятыми координат x и y пар.</span><span class="sxs-lookup"><span data-stu-id="01e4d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="01e4d-111">Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> должен содержать ломаные линии, можно использовать элементы polyline (и все остальные элементы фигуры) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающий нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="01e4d-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="01e4d-112">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="01e4d-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e4d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="01e4d-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="01e4d-114">Пример элементов-фигур</span><span class="sxs-lookup"><span data-stu-id="01e4d-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="01e4d-115">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="01e4d-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
