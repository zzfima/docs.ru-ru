---
title: Практическое руководство. Применение объекта GuidelineSet к рисунку
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217813"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="46e1a-102">Практическое руководство. Применение объекта GuidelineSet к рисунку</span><span class="sxs-lookup"><span data-stu-id="46e1a-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="46e1a-103">В этом примере показано, как применить <xref:System.Windows.Media.GuidelineSet> для <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="46e1a-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="46e1a-104"><xref:System.Windows.Media.DrawingGroup> Класс является единственным типом <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="46e1a-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="46e1a-105">Чтобы применить <xref:System.Windows.Media.GuidelineSet> к другому типу <xref:System.Windows.Media.Drawing>, добавьте его в <xref:System.Windows.Media.DrawingGroup> , а затем применить <xref:System.Windows.Media.GuidelineSet> для вашей <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="46e1a-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46e1a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="46e1a-106">Example</span></span>  
 <span data-ttu-id="46e1a-107">В следующем примере создается два <xref:System.Windows.Media.DrawingGroup> объекты, которые практически идентичны; единственное отличие заключается в: второй <xref:System.Windows.Media.DrawingGroup> имеет <xref:System.Windows.Media.GuidelineSet> и первый — нет.</span><span class="sxs-lookup"><span data-stu-id="46e1a-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="46e1a-108">На следующем рисунке показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="46e1a-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="46e1a-109">Так как два различия в отрисовке <xref:System.Windows.Media.DrawingGroup> объекты не очень заметны, части рисунков увеличены.</span><span class="sxs-lookup"><span data-stu-id="46e1a-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="46e1a-110">![DrawingGroup c GuidelineSet и без него ](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="46e1a-110">![A DrawingGroup with and without a GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="46e1a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="46e1a-111">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="46e1a-112">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="46e1a-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
