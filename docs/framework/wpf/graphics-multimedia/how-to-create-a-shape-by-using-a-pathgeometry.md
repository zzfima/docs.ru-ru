---
title: Практическое руководство. Создание фигуры с помощью PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452049"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="e5c44-102">Практическое руководство. Создание фигуры с помощью PathGeometry</span><span class="sxs-lookup"><span data-stu-id="e5c44-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="e5c44-103">В этом примере показано, как создать фигуру с помощью класса <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e5c44-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="e5c44-104"><xref:System.Windows.Media.PathGeometry> объекты состоят из одного или нескольких объектов <xref:System.Windows.Media.PathFigure>; Каждый <xref:System.Windows.Media.PathFigure> представляет другую фигуру или форму.</span><span class="sxs-lookup"><span data-stu-id="e5c44-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="e5c44-105">Каждая <xref:System.Windows.Media.PathFigure> сама по себе состоит из одного или нескольких объектов <xref:System.Windows.Media.PathSegment>, каждый из которых представляет собой подключенную часть рисунка или фигуры.</span><span class="sxs-lookup"><span data-stu-id="e5c44-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="e5c44-106">К типам сегментов относятся <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>и <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="e5c44-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5c44-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e5c44-107">Example</span></span>  
 <span data-ttu-id="e5c44-108">В следующем примере для создания треугольника используется <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e5c44-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="e5c44-109"><xref:System.Windows.Media.PathGeometry> отображается с помощью элемента <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="e5c44-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="e5c44-110">На следующем рисунке показана фигура, созданная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="e5c44-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="e5c44-111">![Объект PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="e5c44-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="e5c44-112">Треугольник, созданный с помощью PathGeometry</span><span class="sxs-lookup"><span data-stu-id="e5c44-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="e5c44-113">В предыдущем примере показано, как создать относительно простую фигуру — треугольник.</span><span class="sxs-lookup"><span data-stu-id="e5c44-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="e5c44-114"><xref:System.Windows.Media.PathGeometry> также можно использовать для создания более сложных фигур, включая дуги и кривые.</span><span class="sxs-lookup"><span data-stu-id="e5c44-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="e5c44-115">Примеры см. в статьях [Создание эллиптической дуги](how-to-create-an-elliptical-arc.md), [Создание кривой Безье третьего порядка](how-to-create-a-cubic-bezier-curve.md)и [Создание кривой Безье квадратичных](how-to-create-a-quadratic-bezier-curve.md)кривых.</span><span class="sxs-lookup"><span data-stu-id="e5c44-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="e5c44-116">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="e5c44-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c44-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5c44-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="e5c44-118">Общение сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="e5c44-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="e5c44-119">Пример геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="e5c44-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
