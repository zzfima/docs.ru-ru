---
title: Практическое руководство. Создание эллиптической дуги
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453069"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="12df7-102">Практическое руководство. Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="12df7-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="12df7-103">В этом примере показано, как нарисовать дугу эллиптической дуги. Чтобы создать эллиптическую дугу, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>и <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="12df7-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12df7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="12df7-104">Example</span></span>  
 <span data-ttu-id="12df7-105">В следующих примерах эллиптическая дуга рисуется от (10 100) до (200 100).</span><span class="sxs-lookup"><span data-stu-id="12df7-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="12df7-106">Arc имеет <xref:System.Windows.Media.ArcSegment.Size%2A> 100 на 50 аппаратно-независимых пикселей, <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 градусов, <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> параметра `true`и <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="12df7-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="12df7-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="12df7-107">[xaml]</span></span>  
  
 <span data-ttu-id="12df7-108">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]можно использовать синтаксис атрибутов для описания пути.</span><span class="sxs-lookup"><span data-stu-id="12df7-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="12df7-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="12df7-109">[xaml]</span></span>  
  
 <span data-ttu-id="12df7-110">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, более светлую версию <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="12df7-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="12df7-111">Дополнительные сведения см. на странице [Синтаксис разметки пути](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="12df7-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="12df7-112">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]можно также нарисовать эллиптическую дугу, явно используя теги объектов.</span><span class="sxs-lookup"><span data-stu-id="12df7-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="12df7-113">Следующий код эквивалентен предыдущему [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке.</span><span class="sxs-lookup"><span data-stu-id="12df7-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="12df7-114">Данный пример является частью большого примера.</span><span class="sxs-lookup"><span data-stu-id="12df7-114">This example is part of a larger sample.</span></span> <span data-ttu-id="12df7-115">Полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="12df7-115">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12df7-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12df7-116">See also</span></span>

- [<span data-ttu-id="12df7-117">Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="12df7-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="12df7-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="12df7-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
