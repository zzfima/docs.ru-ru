---
title: Практическое руководство. Создание кривой Безье второго порядка
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: 9d389125b6ad09833a16b64cb8f498cc20d4e79c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="dc0fb-102">Практическое руководство. Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="dc0fb-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="dc0fb-103">В этом примере показано, как создать кривую Безье второго порядка.</span><span class="sxs-lookup"><span data-stu-id="dc0fb-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="dc0fb-104">Чтобы создать кривую Безье второго порядка, используйте <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.QuadraticBezierSegment> классы.</span><span class="sxs-lookup"><span data-stu-id="dc0fb-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc0fb-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dc0fb-105">Example</span></span>  
 <span data-ttu-id="dc0fb-106">В следующих примерах кривая Безье второго порядка строится от (10, 100) для (300,100).</span><span class="sxs-lookup"><span data-stu-id="dc0fb-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="dc0fb-107">Кривая имеет контрольную точку с координатами (200,200).</span><span class="sxs-lookup"><span data-stu-id="dc0fb-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="dc0fb-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="dc0fb-108">[xaml]</span></span>  
  
 <span data-ttu-id="dc0fb-109">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно использовать синтаксис атрибутов для описания пути.</span><span class="sxs-lookup"><span data-stu-id="dc0fb-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="dc0fb-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="dc0fb-110">[xaml]</span></span>  
  
 <span data-ttu-id="dc0fb-111">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию из <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="dc0fb-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="dc0fb-112">Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="dc0fb-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="dc0fb-113">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], может также нарисовать кривую Безье второго порядка, используя синтаксис элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="dc0fb-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="dc0fb-114">Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc0fb-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="dc0fb-115">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="dc0fb-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0fb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0fb-116">See Also</span></span>  
 [<span data-ttu-id="dc0fb-117">Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="dc0fb-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="dc0fb-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="dc0fb-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
