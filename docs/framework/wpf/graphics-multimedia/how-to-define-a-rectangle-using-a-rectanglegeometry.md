---
title: Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 5d2ec6aec1eea8528ea6b43f72f4820b8bc19a37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560427"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="ee79e-102">Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="ee79e-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="ee79e-103">В этом примере описывается использование <xref:System.Windows.Media.RectangleGeometry> класса для описания прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="ee79e-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee79e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ee79e-104">Example</span></span>  
 <span data-ttu-id="ee79e-105">В следующем примере показано создание и отображение <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ee79e-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="ee79e-106">Относительное положение и размеры прямоугольника определяются <xref:System.Windows.Rect> структуры.</span><span class="sxs-lookup"><span data-stu-id="ee79e-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="ee79e-107">Относительное положение устанавливается `50,50` и высоту и ширину `25` создает квадрат.</span><span class="sxs-lookup"><span data-stu-id="ee79e-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="ee79e-108">Рисования внутренней прямоугольника с <xref:System.Windows.Media.Brushes.LemonChiffon%2A> кисти и его контура отрисовывается с <xref:System.Windows.Media.Brushes.Black%2A> штриха толщиной `1`.</span><span class="sxs-lookup"><span data-stu-id="ee79e-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="ee79e-109">![Практическое руководство](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="ee79e-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="ee79e-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="ee79e-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="ee79e-111">Несмотря на то, что в этом примере используется <xref:System.Windows.Shapes.Path> элемента для визуализации <xref:System.Windows.Media.RectangleGeometry>, существует множество способов для использования <xref:System.Windows.Media.RectangleGeometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="ee79e-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="ee79e-112">Например <xref:System.Windows.Media.RectangleGeometry> может использоваться для указания <xref:System.Windows.UIElement.Clip%2A> из <xref:System.Windows.UIElement> или <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> из <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="ee79e-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="ee79e-113">Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ee79e-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="ee79e-114">Эти геометрические объекты, а также более сложные, можно также создать с помощью <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ee79e-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee79e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ee79e-115">See Also</span></span>  
 [<span data-ttu-id="ee79e-116">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="ee79e-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="ee79e-117">Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="ee79e-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="ee79e-118">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="ee79e-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
