---
title: "Практическое руководство. Создание эллиптической дуги"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeb93cefd2e55e80f27922feab788698653f405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="c2e2d-102">Практическое руководство. Создание эллиптической дуги</span><span class="sxs-lookup"><span data-stu-id="c2e2d-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="c2e2d-103">В этом примере показано, как рисовать эллиптической дуги. Чтобы создать эллиптическую дугу, используйте <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.ArcSegment> классы.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e2d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c2e2d-104">Example</span></span>  
 <span data-ttu-id="c2e2d-105">В следующих примерах эллиптическую дугу рисуется от (10, 100) (200,100).</span><span class="sxs-lookup"><span data-stu-id="c2e2d-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="c2e2d-106">Дуга имеет <xref:System.Windows.Media.ArcSegment.Size%2A> 100 на 50 аппаратно независимых пикселей, <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 градусов <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> параметра `true`и <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> из <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="c2e2d-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="c2e2d-107">[xaml]</span></span>  
  
 <span data-ttu-id="c2e2d-108">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно использовать синтаксис атрибутов для описания пути.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="c2e2d-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="c2e2d-109">[xaml]</span></span>  
  
 <span data-ttu-id="c2e2d-110">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию из <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="c2e2d-111">Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="c2e2d-111">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="c2e2d-112">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также можно нарисовать эллиптическую дугу явным образом с помощью тегов объектов.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="c2e2d-113">Ниже приведен эквивалентный предшествующей [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="c2e2d-114">Данный пример является частью большого примера.</span><span class="sxs-lookup"><span data-stu-id="c2e2d-114">This example is part of a larger sample.</span></span> <span data-ttu-id="c2e2d-115">Полный пример см. в разделе [примеры](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="c2e2d-115">For the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e2d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e2d-116">See Also</span></span>  
 [<span data-ttu-id="c2e2d-117">Создание кривой Безье второго порядка</span><span class="sxs-lookup"><span data-stu-id="c2e2d-117">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [<span data-ttu-id="c2e2d-118">Создание кривой Безье третьего порядка</span><span class="sxs-lookup"><span data-stu-id="c2e2d-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
