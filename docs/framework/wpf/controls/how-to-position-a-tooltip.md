---
title: Практическое руководство. Определение положения всплывающей подсказки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 811818fe6e7c0d8ce9e2aa058b42bf592ada4b92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212353"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="fcb4d-102">Практическое руководство. Определение положения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="fcb4d-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="fcb4d-103">В этом примере показано, как для указания положения всплывающей подсказки на экране.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcb4d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fcb4d-104">Example</span></span>  
 <span data-ttu-id="fcb4d-105">Можно положения всплывающей подсказки с помощью набора пять свойств, которые определены в обоих <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="fcb4d-106">В следующей таблице показаны эти два набора пять свойств и ссылки на справочную документацию в соответствии с классом.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="fcb4d-107">Соответствующие свойства всплывающей подсказки в соответствии с классом</span><span class="sxs-lookup"><span data-stu-id="fcb4d-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="fcb4d-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="fcb4d-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="fcb4d-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="fcb4d-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="fcb4d-110">Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="fcb4d-111">Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, которые не определены как <xref:System.Windows.Controls.ToolTip> объектов.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="fcb4d-112">На следующих рисунках положения всплывающей подсказки с помощью этих свойств.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="fcb4d-113">Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах в этих примерах показано, как задать свойства, которые определяются <xref:System.Windows.Controls.ToolTip> класса, соответствующего свойства <xref:System.Windows.Controls.ToolTipService> класс следуют тем же правилам макета.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="fcb4d-114">Дополнительные сведения о возможных значениях свойства размещения см. в разделе [поведение при размещении контекстного меню](popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="fcb4d-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  
 
 <span data-ttu-id="fcb4d-115">На следующем рисунке показано положение подсказки с помощью свойства размещения:</span><span class="sxs-lookup"><span data-stu-id="fcb4d-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Схема, показывающая положение подсказки с помощью свойства размещения.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)
 
 <span data-ttu-id="fcb4d-117">На следующем рисунке показано положение подсказки с помощью свойства размещения и PlacementRectangle:</span><span class="sxs-lookup"><span data-stu-id="fcb4d-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>   

 ![Схема, показывающая положение подсказки с помощью свойства PlacementRectangle.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  
 
 <span data-ttu-id="fcb4d-119">На следующем рисунке показано положение подсказки с помощью свойств Placement, PlacementRectangle и смещение:</span><span class="sxs-lookup"><span data-stu-id="fcb4d-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>   
  
 ![Схема, показывающая положение подсказки с помощью свойства смещение.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="fcb4d-121">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для указания положения всплывающей подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="fcb4d-122">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для указания положения всплывающей подсказки, содержимое которых не <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="fcb4d-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="fcb4d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fcb4d-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="fcb4d-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="fcb4d-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="fcb4d-125">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="fcb4d-125">ToolTip Overview</span></span>](tooltip-overview.md)
