---
title: "Как создать составной рисунок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 424f77b076344ad86db992614175243d1473886d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="4e998-102">Как создать составной рисунок</span><span class="sxs-lookup"><span data-stu-id="4e998-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="4e998-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingGroup> для создания сложных рисунков путем объединения нескольких <xref:System.Windows.Media.Drawing> объектов в один составной рисунок.</span><span class="sxs-lookup"><span data-stu-id="4e998-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e998-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4e998-104">Example</span></span>  
 <span data-ttu-id="4e998-105">В следующем примере используется <xref:System.Windows.Media.DrawingGroup> для создания составного рисунка из <xref:System.Windows.Media.GeometryDrawing> и <xref:System.Windows.Media.ImageDrawing> объектов.</span><span class="sxs-lookup"><span data-stu-id="4e998-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="4e998-106">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="4e998-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="4e998-107">![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="4e998-107">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="4e998-108">Составной рисунок, который создается с помощью DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="4e998-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="4e998-109">Обратите внимание, серую границу, которая обозначает границы рисунка.</span><span class="sxs-lookup"><span data-stu-id="4e998-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="4e998-110">Можно использовать <xref:System.Windows.Media.DrawingGroup> для применения <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> параметр <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, или <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> к рисункам.</span><span class="sxs-lookup"><span data-stu-id="4e998-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="4e998-111">Поскольку <xref:System.Windows.Media.DrawingGroup> также <xref:System.Windows.Media.Drawing>, он может содержать другие <xref:System.Windows.Media.DrawingGroup> объекты.</span><span class="sxs-lookup"><span data-stu-id="4e998-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="4e998-112">Следующий пример похож на предыдущем примере, за исключением того, что он использует дополнительные <xref:System.Windows.Media.DrawingGroup> объектов для применения эффектов растрового изображения и маски непрозрачности к некоторым из его рисунков.</span><span class="sxs-lookup"><span data-stu-id="4e998-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="4e998-113">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="4e998-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="4e998-114">![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="4e998-114">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="4e998-115">Составной рисунок, состоящий из нескольких объектов DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="4e998-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="4e998-116">Обратите внимание, серую границу, которая обозначает границы рисунка.</span><span class="sxs-lookup"><span data-stu-id="4e998-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="4e998-117">Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, в разделе [Общие сведения об объектах Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4e998-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e998-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4e998-118">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [<span data-ttu-id="4e998-119">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="4e998-119">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
