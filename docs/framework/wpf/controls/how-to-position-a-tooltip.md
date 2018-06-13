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
ms.openlocfilehash: 218d8814cf75cd80a63c94397ed00e92c6a9a8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555942"
---
# <a name="how-to-position-a-tooltip"></a>Практическое руководство. Задание положения всплывающей подсказки
В этом примере показано, как указать позицию всплывающей подсказки на экране.  
  
## <a name="example"></a>Пример  
 Разместить всплывающую подсказку можно с помощью набора пять свойств, которые определены как <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> классы. В следующей таблице представлены эти два набора из пяти свойств и ссылки на справочную документацию согласно классу.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Свойства подсказки, соответствующие согласно классу  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Класс свойств|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Класс свойств|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Если определить содержимое всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса, однако <xref:System.Windows.Controls.ToolTipService> свойства имеют более высокий приоритет. Используйте <xref:System.Windows.Controls.ToolTipService> свойства для подсказки, который не определен как <xref:System.Windows.Controls.ToolTip> объектов.  
  
 На следующих рисунках положение подсказки с помощью этих свойств. Несмотря на то что, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры на этих рисунках показывают, как для задания свойств, которые определены в <xref:System.Windows.Controls.ToolTip> класса соответствующим свойствам <xref:System.Windows.Controls.ToolTipService> следуют тем же правилам размещения. Дополнительные сведения о возможных значениях свойства размещения см. в разделе [окна](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Положение подсказки с помощью свойства размещения  
  
 ![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Положение подсказки с помощью свойства размещения и PlacementRectangle  
  
 ![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Положение подсказки с помощью свойств Placement, PlacementRectangle и смещение  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для определения положения подсказки, содержимое которых <xref:System.Windows.Controls.ToolTip> объекта.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для определения положения подсказки, содержимое которого не является <xref:System.Windows.Controls.ToolTip> объекта.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [Используйте ContextMenuService и ToolTipService](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
