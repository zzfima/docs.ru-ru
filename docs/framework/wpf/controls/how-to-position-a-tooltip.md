---
title: "Практическое руководство. Задание положения всплывающей подсказки"
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
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e86f2adfbe8f8aac000d653e955555c7def750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="816ad-102">Практическое руководство. Задание положения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="816ad-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="816ad-103">В этом примере показано, как указать позицию всплывающей подсказки на экране.</span><span class="sxs-lookup"><span data-stu-id="816ad-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="816ad-104">Пример</span><span class="sxs-lookup"><span data-stu-id="816ad-104">Example</span></span>  
 <span data-ttu-id="816ad-105">Разместить всплывающую подсказку можно с помощью набора пять свойств, которые определены как <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы.</span><span class="sxs-lookup"><span data-stu-id="816ad-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="816ad-106">В следующей таблице представлены эти два набора из пяти свойств и ссылки на справочную документацию согласно классу.</span><span class="sxs-lookup"><span data-stu-id="816ad-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="816ad-107">Свойства подсказки, соответствующие согласно классу</span><span class="sxs-lookup"><span data-stu-id="816ad-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="816ad-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>Класс свойств</span><span class="sxs-lookup"><span data-stu-id="816ad-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="816ad-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>Класс свойств</span><span class="sxs-lookup"><span data-stu-id="816ad-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="816ad-110">Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="816ad-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="816ad-111">Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, который не определен как <xref:System.Windows.Controls.ToolTip> объектов.</span><span class="sxs-lookup"><span data-stu-id="816ad-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="816ad-112">На следующих рисунках положение подсказки с помощью этих свойств.</span><span class="sxs-lookup"><span data-stu-id="816ad-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="816ad-113">Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры на этих рисунках показывают, как для задания свойств, которые определены в <xref:System.Windows.Controls.ToolTip> класса соответствующим свойствам <xref:System.Windows.Controls.ToolTipService> следуют тем же правилам размещения.</span><span class="sxs-lookup"><span data-stu-id="816ad-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="816ad-114">Дополнительные сведения о возможных значениях свойства размещения см. в разделе [окна](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="816ad-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="816ad-115">![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="816ad-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="816ad-116">Положение подсказки с помощью свойства размещения</span><span class="sxs-lookup"><span data-stu-id="816ad-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="816ad-117">![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="816ad-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="816ad-118">Положение подсказки с помощью свойства размещения и PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="816ad-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="816ad-119">![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="816ad-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="816ad-120">Положение подсказки с помощью свойств Placement, PlacementRectangle и смещение</span><span class="sxs-lookup"><span data-stu-id="816ad-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="816ad-121">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для определения положения подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="816ad-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="816ad-122">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для определения положения подсказки, содержимое которого не является <xref:System.Windows.Controls.ToolTip> объекта.</span><span class="sxs-lookup"><span data-stu-id="816ad-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="816ad-123">См. также</span><span class="sxs-lookup"><span data-stu-id="816ad-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="816ad-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="816ad-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="816ad-125">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="816ad-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="816ad-126">Используйте ContextMenuService и ToolTipService</span><span class="sxs-lookup"><span data-stu-id="816ad-126">Use the ContextMenuService and ToolTipService</span></span>](http://msdn.microsoft.com/en-us/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
