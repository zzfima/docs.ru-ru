---
title: "Практическое руководство. Создание фигуры с помощью PathGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31f77f0921bb018317834077f70e4623c47a4f7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="2b75f-102">Практическое руководство. Создание фигуры с помощью PathGeometry</span><span class="sxs-lookup"><span data-stu-id="2b75f-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="2b75f-103">В этом примере показано, как создать форму с помощью <xref:System.Windows.Media.PathGeometry> класса.</span><span class="sxs-lookup"><span data-stu-id="2b75f-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="2b75f-104"><xref:System.Windows.Media.PathGeometry>объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов, каждый из которых <xref:System.Windows.Media.PathFigure> представляет различные «рисунок» или фигуры.</span><span class="sxs-lookup"><span data-stu-id="2b75f-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="2b75f-105">Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет подключенных часть фигуры или формы.</span><span class="sxs-lookup"><span data-stu-id="2b75f-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="2b75f-106">Типы сегментов включают <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, и <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="2b75f-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b75f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2b75f-107">Example</span></span>  
 <span data-ttu-id="2b75f-108">В следующем примере используется <xref:System.Windows.Media.PathGeometry> для создания треугольника.</span><span class="sxs-lookup"><span data-stu-id="2b75f-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="2b75f-109"><xref:System.Windows.Media.PathGeometry> Отображается с использованием <xref:System.Windows.Shapes.Path> элемента.</span><span class="sxs-lookup"><span data-stu-id="2b75f-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="2b75f-110">На следующем рисунке показана фигура, созданная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="2b75f-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="2b75f-111">![Объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="2b75f-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="2b75f-112">Треугольник, созданных с помощью объект PathGeometry</span><span class="sxs-lookup"><span data-stu-id="2b75f-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="2b75f-113">В предыдущем примере показан способ создания относительно простой фигуры треугольника.</span><span class="sxs-lookup"><span data-stu-id="2b75f-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="2b75f-114">Объект <xref:System.Windows.Media.PathGeometry> можно также использовать для создания более сложных фигур, включая дуги и кривые.</span><span class="sxs-lookup"><span data-stu-id="2b75f-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="2b75f-115">Примеры см. в разделе [создать эллиптическую дугу](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [создайте кривую Безье третьего](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), и [создайте кривую Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="2b75f-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="2b75f-116">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="2b75f-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b75f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2b75f-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="2b75f-118">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="2b75f-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="2b75f-119">Образец геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="2b75f-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
