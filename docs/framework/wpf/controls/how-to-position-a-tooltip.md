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
# <a name="how-to-position-a-tooltip"></a>Практическое руководство. Задание положения всплывающей подсказки
В этом примере показано, как указать положение инструмента на экране.  
  
## <a name="example"></a>Пример  
 Вы можете расположить набор инструментов, используя набор из <xref:System.Windows.Controls.ToolTip> пяти <xref:System.Windows.Controls.ToolTipService> свойств, которые определяются как в классах, так и в классах. В следующей таблице показаны эти два набора из пяти свойств и приведены ссылки на их справочную документацию в соответствии с классом.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Соответствующие свойства инструментария в зависимости от класса  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>свойства класса|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>свойства класса|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Если вы определяете содержимое инструментария с помощью <xref:System.Windows.Controls.ToolTip> объекта, можно использовать свойства любого класса; однако <xref:System.Windows.Controls.ToolTipService> свойства имеют приоритет. Используйте <xref:System.Windows.Controls.ToolTipService> свойства для инструментов, <xref:System.Windows.Controls.ToolTip> которые не определены как объекты.  
  
 Следующие иллюстрации показывают, как позиционировать набор инструментов с помощью этих свойств. Хотя [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры на этих иллюстрациях показывают, как установить свойства, определяемые <xref:System.Windows.Controls.ToolTip> классом, соответствующие свойства <xref:System.Windows.Controls.ToolTipService> класса следуют тем же правилам макета. Для получения дополнительной информации о возможных [Popup Placement Behavior](popup-placement-behavior.md)значениях для свойства размещения см.  

 Следующее изображение показывает размещение инструментария с помощью свойства размещения:  
  
 ![Диаграмма, показывающая размещение ToolTip с помощью свойства размещения.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 Следующее изображение показывает размещение инструментария с помощью свойств размещения и размещенияRectangle:

 ![Диаграмма, показывающая размещение ToolTip с помощью свойства PlacementRectangle.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 Следующее изображение показывает размещение инструментария с помощью свойств размещения, размещения Rectangle и Offset:
  
 ![Диаграмма, показывающая размещение ToolTip с помощью свойства Offset.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTip> свойства для определения позиции <xref:System.Windows.Controls.ToolTip> инструмента, содержание которого является объектом.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.ToolTipService> свойства для определения позиции <xref:System.Windows.Controls.ToolTip> инструмента, содержимое которого не является объектом.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Как-к темам](tooltip-how-to-topics.md)
- [Общие сведения о всплывающих подсказках](tooltip-overview.md)
