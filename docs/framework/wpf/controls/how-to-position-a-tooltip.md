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
# <a name="how-to-position-a-tooltip"></a>Практическое руководство. Задание положения всплывающей подсказки
В этом примере показано, как для указания положения всплывающей подсказки на экране.  
  
## <a name="example"></a>Пример  
 Можно положения всплывающей подсказки с помощью набора пять свойств, которые определены в обоих <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы. В следующей таблице показаны эти два набора пять свойств и ссылки на справочную документацию в соответствии с классом.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Соответствующие свойства всплывающей подсказки в соответствии с классом  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> свойства класса|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> свойства класса|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет. Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, которые не определены как <xref:System.Windows.Controls.ToolTip> объектов.  
  
 На следующих рисунках положения всплывающей подсказки с помощью этих свойств. Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах в этих примерах показано, как задать свойства, которые определяются <xref:System.Windows.Controls.ToolTip> класса, соответствующего свойства <xref:System.Windows.Controls.ToolTipService> класс следуют тем же правилам макета. Дополнительные сведения о возможных значениях свойства размещения см. в разделе [поведение при размещении контекстного меню](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Положение подсказки с помощью свойства размещения  
  
 ![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Положение подсказки с помощью свойства размещения и PlacementRectangle  
  
 ![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Положение подсказки с помощью свойств размещения, PlacementRectangle и смещения  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для указания положения всплывающей подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для указания положения всплывающей подсказки, содержимое которых не <xref:System.Windows.Controls.ToolTip> объекта.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md)
