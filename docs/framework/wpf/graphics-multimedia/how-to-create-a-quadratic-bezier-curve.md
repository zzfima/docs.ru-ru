---
title: Практическое руководство. Создание кривой Безье второго порядка
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: 8481a7e0e6d682a335b22ea6cdf73a23a9f155af
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43880514"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="dabbd-102">Практическое руководство. Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="dabbd-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="dabbd-103">В этом примере демонстрируется создание кривой Безье второго порядка.</span><span class="sxs-lookup"><span data-stu-id="dabbd-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="dabbd-104">Создание кривой Безье второго порядка, используйте <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.QuadraticBezierSegment> классы.</span><span class="sxs-lookup"><span data-stu-id="dabbd-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dabbd-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dabbd-105">Example</span></span>  
 <span data-ttu-id="dabbd-106">В следующих примерах кривая Безье второго порядка извлекается из (10, 100) в (300,100).</span><span class="sxs-lookup"><span data-stu-id="dabbd-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="dabbd-107">Кривая имеет контрольную точку с координатами (200,200).</span><span class="sxs-lookup"><span data-stu-id="dabbd-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="dabbd-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="dabbd-108">[xaml]</span></span>  
  
 <span data-ttu-id="dabbd-109">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно использовать синтаксис атрибута для описания пути.</span><span class="sxs-lookup"><span data-stu-id="dabbd-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="dabbd-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="dabbd-110">[xaml]</span></span>  
  
 <span data-ttu-id="dabbd-111">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченные версии <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="dabbd-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="dabbd-112">Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="dabbd-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="dabbd-113">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно также начертить кривую Безье второго порядка, используя синтаксис объектных элементов.</span><span class="sxs-lookup"><span data-stu-id="dabbd-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="dabbd-114">Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dabbd-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="dabbd-115">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="dabbd-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dabbd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dabbd-116">See Also</span></span>  
 [<span data-ttu-id="dabbd-117">Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="dabbd-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="dabbd-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="dabbd-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
