---
title: "Практическое руководство. Создание составной фигуры"
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
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ecb4ecdc5c83cbb6f2b4faee9cb3654939bd346
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="002cd-102">Практическое руководство. Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="002cd-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="002cd-103">В этом примере демонстрируется создание составных фигур с помощью <xref:System.Windows.Media.Geometry> объектов и отобразить их с помощью <xref:System.Windows.Shapes.Path> элемента.</span><span class="sxs-lookup"><span data-stu-id="002cd-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="002cd-104">В следующем примере <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.RectangleGeometry> используются с <xref:System.Windows.Media.GeometryGroup> для создания составного фигуры.</span><span class="sxs-lookup"><span data-stu-id="002cd-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="002cd-105">Затем вычерчиваются с помощью <xref:System.Windows.Shapes.Path> элемента.</span><span class="sxs-lookup"><span data-stu-id="002cd-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="002cd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="002cd-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="002cd-107">На следующем рисунке показана фигура, созданная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="002cd-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="002cd-108">![Составной геометрический объект создан с использованием GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="002cd-108">![A composite geometry created using a GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="002cd-109">Составная геометрическая фигура</span><span class="sxs-lookup"><span data-stu-id="002cd-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="002cd-110">Более сложные фигуры, таких как многоугольники и фигуры с фрагментами кривых, могут быть созданы с помощью <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="002cd-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="002cd-111">Пример, показывающий, как создать форму с помощью <xref:System.Windows.Media.PathGeometry>, в разделе [создать фигуру с помощью объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="002cd-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="002cd-112">Несмотря на то, что этот пример отображает фигуру на экран с помощью <xref:System.Windows.Shapes.Path> элемент, <xref:System.Windows.Media.Geometry> объектов может также использоваться для описания содержимого <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="002cd-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="002cd-113">Они также могут использоваться для обрезки и проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="002cd-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="002cd-114">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="002cd-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
