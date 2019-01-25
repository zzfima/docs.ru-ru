---
title: Как выполнить Создание нескольких подконтуров внутри PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638357"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="2d98e-102">Как выполнить Создание нескольких подконтуров внутри PathGeometry</span><span class="sxs-lookup"><span data-stu-id="2d98e-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="2d98e-103">В этом примере показано, как создание нескольких подконтуров в <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="2d98e-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="2d98e-104">Чтобы создать несколько подконтуров, необходимо создать <xref:System.Windows.Media.PathFigure> для каждого вложенного пути.</span><span class="sxs-lookup"><span data-stu-id="2d98e-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d98e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2d98e-105">Example</span></span>  
 <span data-ttu-id="2d98e-106">В следующем примере создается два подконтуров, каждый из них треугольника.</span><span class="sxs-lookup"><span data-stu-id="2d98e-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="2d98e-107">В следующем примере показано, как создание нескольких подконтуров с помощью <xref:System.Windows.Shapes.Path> и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис атрибута.</span><span class="sxs-lookup"><span data-stu-id="2d98e-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="2d98e-108">Каждый `M` создает новый вложенный путь, чтобы в примере создается два подконтуров, что каждый Рисование треугольника.</span><span class="sxs-lookup"><span data-stu-id="2d98e-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="2d98e-109">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченные версии <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="2d98e-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="2d98e-110">Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="2d98e-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d98e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2d98e-111">See also</span></span>
- [<span data-ttu-id="2d98e-112">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="2d98e-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
