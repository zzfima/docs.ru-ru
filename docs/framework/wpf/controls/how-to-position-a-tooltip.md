---
title: Как выполнить Задание положения всплывающей подсказки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 403b070e782a6f243fd5a420e569daa02044dbb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727707"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="a300d-102">Как выполнить Задание положения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="a300d-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="a300d-103">В этом примере показано, как для указания положения всплывающей подсказки на экране.</span><span class="sxs-lookup"><span data-stu-id="a300d-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a300d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a300d-104">Example</span></span>  
 <span data-ttu-id="a300d-105">Можно положения всплывающей подсказки с помощью набора пять свойств, которые определены в обоих <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы.</span><span class="sxs-lookup"><span data-stu-id="a300d-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="a300d-106">В следующей таблице показаны эти два набора пять свойств и ссылки на справочную документацию в соответствии с классом.</span><span class="sxs-lookup"><span data-stu-id="a300d-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="a300d-107">Соответствующие свойства всплывающей подсказки в соответствии с классом</span><span class="sxs-lookup"><span data-stu-id="a300d-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="a300d-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="a300d-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="a300d-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> свойства класса</span><span class="sxs-lookup"><span data-stu-id="a300d-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a300d-110">Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="a300d-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="a300d-111">Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, которые не определены как <xref:System.Windows.Controls.ToolTip> объектов.</span><span class="sxs-lookup"><span data-stu-id="a300d-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="a300d-112">На следующих рисунках положения всплывающей подсказки с помощью этих свойств.</span><span class="sxs-lookup"><span data-stu-id="a300d-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="a300d-113">Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах в этих примерах показано, как задать свойства, которые определяются <xref:System.Windows.Controls.ToolTip> класса, соответствующего свойства <xref:System.Windows.Controls.ToolTipService> класс следуют тем же правилам макета.</span><span class="sxs-lookup"><span data-stu-id="a300d-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="a300d-114">Дополнительные сведения о возможных значениях свойства размещения см. в разделе [поведение при размещении контекстного меню](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="a300d-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="a300d-115">![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="a300d-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="a300d-116">Положение подсказки с помощью свойства размещения</span><span class="sxs-lookup"><span data-stu-id="a300d-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="a300d-117">![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="a300d-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="a300d-118">Положение подсказки с помощью свойства размещения и PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="a300d-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="a300d-119">![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="a300d-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="a300d-120">Положение подсказки с помощью свойств размещения, PlacementRectangle и смещения</span><span class="sxs-lookup"><span data-stu-id="a300d-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="a300d-121">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для указания положения всплывающей подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="a300d-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="a300d-122">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для указания положения всплывающей подсказки, содержимое которых не <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="a300d-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="a300d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a300d-123">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="a300d-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="a300d-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="a300d-125">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="a300d-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
- [<span data-ttu-id="a300d-126">Используйте ContextMenuService и ToolTipService</span><span class="sxs-lookup"><span data-stu-id="a300d-126">Use the ContextMenuService and ToolTipService</span></span>](https://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
