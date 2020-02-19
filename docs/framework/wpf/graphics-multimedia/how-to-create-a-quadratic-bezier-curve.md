---
title: Практическое руководство. Создание кривой Безье второго порядка
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452075"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="418cf-102">Практическое руководство. Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="418cf-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="418cf-103">В этом примере показано, как создать кривую Безье второго порядка.</span><span class="sxs-lookup"><span data-stu-id="418cf-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="418cf-104">Чтобы создать кривую Безье квадратичных кривых, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>и <xref:System.Windows.Media.QuadraticBezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="418cf-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="418cf-105">Пример</span><span class="sxs-lookup"><span data-stu-id="418cf-105">Example</span></span>  
 <span data-ttu-id="418cf-106">В следующих примерах кривая Безье второго типа рисуется от (10 100) до (300 100).</span><span class="sxs-lookup"><span data-stu-id="418cf-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="418cf-107">Кривая имеет контрольную точку (200 200).</span><span class="sxs-lookup"><span data-stu-id="418cf-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="418cf-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="418cf-108">[xaml]</span></span>  
  
 <span data-ttu-id="418cf-109">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]можно использовать синтаксис атрибутов для описания пути.</span><span class="sxs-lookup"><span data-stu-id="418cf-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="418cf-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="418cf-110">[xaml]</span></span>  
  
 <span data-ttu-id="418cf-111">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, более светлую версию <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="418cf-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="418cf-112">Дополнительные сведения см. на странице [Синтаксис разметки пути](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="418cf-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="418cf-113">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]можно также нарисовать кривую Безье второго типа с помощью синтаксиса объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="418cf-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="418cf-114">Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="418cf-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="418cf-115">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="418cf-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418cf-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="418cf-116">See also</span></span>

- [<span data-ttu-id="418cf-117">Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="418cf-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="418cf-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="418cf-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
