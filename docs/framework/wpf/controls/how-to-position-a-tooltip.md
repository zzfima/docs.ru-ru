---
title: Практическое руководство. Задание положения всплывающей подсказки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 985c9b7737d979937837d7184f9b96f226ec73c3
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746919"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="27836-102">Практическое руководство. Задание положения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="27836-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="27836-103">В этом примере показано, как для указания положения всплывающей подсказки на экране.</span><span class="sxs-lookup"><span data-stu-id="27836-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27836-104">Пример</span><span class="sxs-lookup"><span data-stu-id="27836-104">Example</span></span>  
 <span data-ttu-id="27836-105">Можно положения всплывающей подсказки с помощью набора пять свойств, которые определены в обоих <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы.</span><span class="sxs-lookup"><span data-stu-id="27836-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="27836-106">В следующей таблице показаны эти два набора пять свойств и ссылки на справочную документацию в соответствии с классом.</span><span class="sxs-lookup"><span data-stu-id="27836-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="27836-107">Соответствующие свойства всплывающей подсказки в соответствии с классом</span><span class="sxs-lookup"><span data-stu-id="27836-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="27836-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="27836-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="27836-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="27836-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="27836-110">Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="27836-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="27836-111">Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, которые не определены как <xref:System.Windows.Controls.ToolTip> объектов.</span><span class="sxs-lookup"><span data-stu-id="27836-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="27836-112">На следующих рисунках положения всплывающей подсказки с помощью этих свойств.</span><span class="sxs-lookup"><span data-stu-id="27836-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="27836-113">Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах в этих примерах показано, как задать свойства, которые определяются <xref:System.Windows.Controls.ToolTip> класса, соответствующего свойства <xref:System.Windows.Controls.ToolTipService> класс следуют тем же правилам макета.</span><span class="sxs-lookup"><span data-stu-id="27836-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="27836-114">Дополнительные сведения о возможных значениях свойства размещения см. в разделе [поведение при размещении контекстного меню](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="27836-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="27836-115">![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="27836-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="27836-116">Положение подсказки с помощью свойства размещения</span><span class="sxs-lookup"><span data-stu-id="27836-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="27836-117">![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="27836-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="27836-118">Положение подсказки с помощью свойства размещения и PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="27836-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="27836-119">![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="27836-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="27836-120">Положение подсказки с помощью свойств размещения, PlacementRectangle и смещения</span><span class="sxs-lookup"><span data-stu-id="27836-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="27836-121">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для указания положения всплывающей подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="27836-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="27836-122">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для указания положения всплывающей подсказки, содержимое которых не <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="27836-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="27836-123">См. также</span><span class="sxs-lookup"><span data-stu-id="27836-123">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="27836-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="27836-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="27836-125">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="27836-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
