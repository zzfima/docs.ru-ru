---
title: "Практическое руководство. Создание отрезка с помощью LineGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 487a5ffaf952450c6196f5fe0d00fd249177b054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="afdbc-102">Практическое руководство. Создание отрезка с помощью LineGeometry</span><span class="sxs-lookup"><span data-stu-id="afdbc-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="afdbc-103">В этом примере показано, как использовать <xref:System.Windows.Media.LineGeometry> класса для описания строки.</span><span class="sxs-lookup"><span data-stu-id="afdbc-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="afdbc-104">Объект <xref:System.Windows.Media.LineGeometry> определяется его начальную и конечную точки.</span><span class="sxs-lookup"><span data-stu-id="afdbc-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afdbc-105">Пример</span><span class="sxs-lookup"><span data-stu-id="afdbc-105">Example</span></span>  
 <span data-ttu-id="afdbc-106">В следующем примере показано создание и отображение <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="afdbc-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="afdbc-107">Объект <xref:System.Windows.Shapes.Path> элемент используется для отображения в строке.</span><span class="sxs-lookup"><span data-stu-id="afdbc-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="afdbc-108">Так как строки без области <xref:System.Windows.Shapes.Path> объекта <xref:System.Windows.Shapes.Shape.Fill%2A> не указан; вместо этого <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> используются свойства.</span><span class="sxs-lookup"><span data-stu-id="afdbc-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="afdbc-109">![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="afdbc-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="afdbc-110">Объект LineGeometry, соединяющий точки (10,20) и (100,130)</span><span class="sxs-lookup"><span data-stu-id="afdbc-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="afdbc-111">Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="afdbc-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="afdbc-112">Эти геометрические объекты, а также более сложные, можно также создать с помощью <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="afdbc-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="afdbc-113">Дополнительные сведения см. в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="afdbc-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdbc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="afdbc-114">See Also</span></span>  
 [<span data-ttu-id="afdbc-115">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="afdbc-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="afdbc-116">Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="afdbc-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="afdbc-117">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="afdbc-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
