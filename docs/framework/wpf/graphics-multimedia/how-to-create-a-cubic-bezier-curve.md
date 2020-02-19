---
title: Практическое руководство. Создание кривой Безье третьего порядка
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452114"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="16025-102">Практическое руководство. Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="16025-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="16025-103">В этом примере показано, как создать кривую Безье третьего порядка.</span><span class="sxs-lookup"><span data-stu-id="16025-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="16025-104">Чтобы создать кривую Безье третьего порядка, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>и <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="16025-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="16025-105">Чтобы отобразить полученную геометрию, используйте элемент <xref:System.Windows.Shapes.Path> или используйте его с <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="16025-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="16025-106">В следующих примерах кривая Безье третьего порядка рисуется от (10, 100) до (300, 100).</span><span class="sxs-lookup"><span data-stu-id="16025-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="16025-107">Кривая имеет контрольные точки (100, 0) и (200, 200).</span><span class="sxs-lookup"><span data-stu-id="16025-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16025-108">Пример</span><span class="sxs-lookup"><span data-stu-id="16025-108">Example</span></span>  
 <span data-ttu-id="16025-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="16025-109">[xaml]</span></span>  
  
 <span data-ttu-id="16025-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]можно использовать сокращенный синтаксис разметки для описания пути.</span><span class="sxs-lookup"><span data-stu-id="16025-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="16025-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="16025-111">[xaml]</span></span>  
  
 <span data-ttu-id="16025-112">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]можно также нарисовать кривую Безье третьего порядка с помощью тегов объектов.</span><span class="sxs-lookup"><span data-stu-id="16025-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="16025-113">Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16025-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="16025-114">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="16025-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16025-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="16025-115">See also</span></span>

- [<span data-ttu-id="16025-116">Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="16025-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="16025-117">Создание LineSegment в PathGeometry</span><span class="sxs-lookup"><span data-stu-id="16025-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="16025-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="16025-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="16025-119">Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="16025-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
