---
title: Практическое руководство. Создание составного рисунка
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: ec71fb3e2f92444d33e15da38f0c88acc715c46d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374145"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="1419e-102">Практическое руководство. Создание составного рисунка</span><span class="sxs-lookup"><span data-stu-id="1419e-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="1419e-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingGroup> для создания сложных рисунков, объединив несколько <xref:System.Windows.Media.Drawing> объектов в один составной рисунок.</span><span class="sxs-lookup"><span data-stu-id="1419e-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1419e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1419e-104">Example</span></span>  
 <span data-ttu-id="1419e-105">В следующем примере используется <xref:System.Windows.Media.DrawingGroup> Создание составного рисунка из <xref:System.Windows.Media.GeometryDrawing> и <xref:System.Windows.Media.ImageDrawing> объектов.</span><span class="sxs-lookup"><span data-stu-id="1419e-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="1419e-106">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="1419e-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="1419e-107">![DrawingGroup с множественными отрисовками](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="1419e-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="1419e-108">Составной рисунок, который создается с помощью DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="1419e-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="1419e-109">Обратите внимание, серую границу, которая обозначает границы рисунка.</span><span class="sxs-lookup"><span data-stu-id="1419e-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="1419e-110">Можно использовать <xref:System.Windows.Media.DrawingGroup> для применения <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> параметр <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, или <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> к рисункам.</span><span class="sxs-lookup"><span data-stu-id="1419e-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="1419e-111">Так как <xref:System.Windows.Media.DrawingGroup> также <xref:System.Windows.Media.Drawing>, он может содержать другие <xref:System.Windows.Media.DrawingGroup> объектов.</span><span class="sxs-lookup"><span data-stu-id="1419e-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="1419e-112">Следующий пример похож на предыдущий, за исключением того, что она использует дополнительные <xref:System.Windows.Media.DrawingGroup> объектов, чтобы применить эффекты для точечных рисунков и маски непрозрачности к некоторым из его рисунков.</span><span class="sxs-lookup"><span data-stu-id="1419e-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="1419e-113">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="1419e-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="1419e-114">![DrawingGroup с множественными отрисовками](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="1419e-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="1419e-115">Составной рисунок, состоящий из нескольких объектов DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="1419e-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="1419e-116">Обратите внимание, серую границу, которая обозначает границы рисунка.</span><span class="sxs-lookup"><span data-stu-id="1419e-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="1419e-117">Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1419e-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1419e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1419e-118">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="1419e-119">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="1419e-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
