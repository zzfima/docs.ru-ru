---
title: Практическое руководство. Создание составной фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452101"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="4e2cc-102">Практическое руководство. Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="4e2cc-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="4e2cc-103">В этом примере показано, как создавать составные фигуры с помощью <xref:System.Windows.Media.Geometry>ных объектов и отображать их с помощью элемента <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="4e2cc-104">В следующем примере <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.RectangleGeometry> используются с <xref:System.Windows.Media.GeometryGroup> для создания составной фигуры.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="4e2cc-105">Затем геометрические объекты рисуются с помощью элемента <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e2cc-106">Пример</span><span class="sxs-lookup"><span data-stu-id="4e2cc-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="4e2cc-107">На следующем рисунке показана фигура, созданная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="4e2cc-108">![Составная геометрия, созданная с помощью GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="4e2cc-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="4e2cc-109">Составной геометрический объект</span><span class="sxs-lookup"><span data-stu-id="4e2cc-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="4e2cc-110">Более сложные фигуры, такие как многоугольники и фигуры с изогнутыми сегментами, могут быть созданы с помощью <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4e2cc-111">Пример создания фигуры с помощью <xref:System.Windows.Media.PathGeometry>см. [в разделе Создание фигуры с помощью PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="4e2cc-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="4e2cc-112">Хотя в этом примере фигура подготавливается к экрану с помощью элемента <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> объекты также могут использоваться для описания содержимого <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="4e2cc-113">Они также могут использоваться для обрезки и проверки попадания.</span><span class="sxs-lookup"><span data-stu-id="4e2cc-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="4e2cc-114">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="4e2cc-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
