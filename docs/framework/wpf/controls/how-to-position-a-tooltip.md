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
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186941"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="fd4a3-102">Практическое руководство. Задание положения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="fd4a3-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="fd4a3-103">В этом примере показано, как указать положение инструмента на экране.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4a3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fd4a3-104">Example</span></span>  
 <span data-ttu-id="fd4a3-105">Вы можете расположить набор инструментов, используя набор из <xref:System.Windows.Controls.ToolTip> пяти <xref:System.Windows.Controls.ToolTipService> свойств, которые определяются как в классах, так и в классах.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="fd4a3-106">В следующей таблице показаны эти два набора из пяти свойств и приведены ссылки на их справочную документацию в соответствии с классом.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="fd4a3-107">Соответствующие свойства инструментария в зависимости от класса</span><span class="sxs-lookup"><span data-stu-id="fd4a3-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="fd4a3-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>свойства класса</span><span class="sxs-lookup"><span data-stu-id="fd4a3-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="fd4a3-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>свойства класса</span><span class="sxs-lookup"><span data-stu-id="fd4a3-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="fd4a3-110">Если вы определяете содержимое инструментария с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса; однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="fd4a3-111">Используйте <xref:System.Windows.Controls.ToolTipService> свойства для инструментов, <xref:System.Windows.Controls.ToolTip> которые не определены как объекты.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="fd4a3-112">Следующие иллюстрации показывают, как позиционировать набор инструментов с помощью этих свойств.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="fd4a3-113">Хотя [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры на этих иллюстрациях показывают, как установить свойства, определяемые <xref:System.Windows.Controls.ToolTip> классом, соответствующие свойства <xref:System.Windows.Controls.ToolTipService> класса следуют тем же правилам макета.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="fd4a3-114">Для получения дополнительной информации о возможных [Popup Placement Behavior](popup-placement-behavior.md)значениях для свойства размещения см.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="fd4a3-115">Следующее изображение показывает размещение инструментария с помощью свойства размещения:</span><span class="sxs-lookup"><span data-stu-id="fd4a3-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Диаграмма, показывающая размещение ToolTip с помощью свойства размещения.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="fd4a3-117">Следующее изображение показывает размещение инструментария с помощью свойств размещения и размещенияRectangle:</span><span class="sxs-lookup"><span data-stu-id="fd4a3-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![Диаграмма, показывающая размещение ToolTip с помощью свойства PlacementRectangle.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="fd4a3-119">Следующее изображение показывает размещение инструментария с помощью свойств размещения, размещения Rectangle и Offset:</span><span class="sxs-lookup"><span data-stu-id="fd4a3-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Диаграмма, показывающая размещение ToolTip с помощью свойства Offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="fd4a3-121">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для определения позиции <xref:System.Windows.Controls.ToolTip> инструмента, содержание которого является объектом.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="fd4a3-122">В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для определения позиции <xref:System.Windows.Controls.ToolTip> инструмента, содержимое которого не является объектом.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="fd4a3-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fd4a3-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="fd4a3-124">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="fd4a3-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="fd4a3-125">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="fd4a3-125">ToolTip Overview</span></span>](tooltip-overview.md)
