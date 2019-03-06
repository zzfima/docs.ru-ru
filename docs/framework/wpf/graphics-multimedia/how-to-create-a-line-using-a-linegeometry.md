---
title: Практическое руководство. Создание линии с помощью LineGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 6d5d0b413f940a2c7f70e05135ff070c1fe5ba21
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374665"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="0e4b0-102">Практическое руководство. Создание линии с помощью LineGeometry</span><span class="sxs-lookup"><span data-stu-id="0e4b0-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="0e4b0-103">В этом примере показано, как использовать <xref:System.Windows.Media.LineGeometry> класс, который описывает строку.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="0e4b0-104">Объект <xref:System.Windows.Media.LineGeometry> определяется его начальную и конечную точки.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e4b0-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0e4b0-105">Example</span></span>  
 <span data-ttu-id="0e4b0-106">В следующем примере показано, как создать и отобразить <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="0e4b0-107">Объект <xref:System.Windows.Shapes.Path> элемент используется для отображения линии.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="0e4b0-108">Поскольку линия не имеет площади, <xref:System.Windows.Shapes.Path> объекта <xref:System.Windows.Shapes.Shape.Fill%2A> не задан; вместо этого <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> используются свойства.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="0e4b0-109">![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="0e4b0-109">![A LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="0e4b0-110">Объект LineGeometry, соединяющий точки (10,20) и (100,130)</span><span class="sxs-lookup"><span data-stu-id="0e4b0-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="0e4b0-111">Другие простые геометрические классы включают <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="0e4b0-112">Эти геометрические объекты, а также более сложные, могут также создаваться с использованием <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0e4b0-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="0e4b0-113">Дополнительные сведения см. в разделе [Общие сведения о геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0e4b0-113">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4b0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0e4b0-114">See also</span></span>
- [<span data-ttu-id="0e4b0-115">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="0e4b0-115">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="0e4b0-116">Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="0e4b0-116">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="0e4b0-117">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="0e4b0-117">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
