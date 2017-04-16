---
title: "Практическое руководство. Задание положения всплывающей подсказки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "размещение элементов управления ToolTip"
  - "ToolTip - элемент управления, размещение"
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Задание положения всплывающей подсказки
В этом примере показан порядок указания положения подсказки на экране.  
  
## Пример  
 Разместить всплывающую подсказку можно, используя пять свойств, которые определены в классах <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService>.  В следующей таблице представлены эти два набора из пяти свойств и ссылки на справочную документацию, соответствующую каждому классу.  
  
### Свойства подсказки, соответствующие классу  
  
|Свойства класса <xref:System.Windows.Controls.ToolTip?displayProperty=fullName>|Свойства класса <xref:System.Windows.Controls.ToolTipService?displayProperty=fullName>|  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=fullName>|  
  
 Если определить содержимое всплывающей подсказки с помощью объекта <xref:System.Windows.Controls.ToolTip>, можно использовать свойства любого класса; однако свойства класса <xref:System.Windows.Controls.ToolTipService> имеют приоритет.  Свойства <xref:System.Windows.Controls.ToolTipService> используются для всплывающих подсказок, не определенных как объекты <xref:System.Windows.Controls.ToolTip>.  
  
 На следующих рисунках показано, как задать положение подсказки с помощью этих свойств.  Хотя примеры кода [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] на этих рисунках показывают, как установить значения свойств, определенных с помощью класса <xref:System.Windows.Controls.ToolTip>, соответствующие свойства класса <xref:System.Windows.Controls.ToolTipService> следуют тем же правилам размещения.  Дополнительные сведения о возможных значениях свойства Placement содержатся в разделе [Поведение при размещении контекстного меню](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Положение подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Размещение всплывающей подсказки с помощью свойства Placement  
  
 ![Помещение подсказки при помощи прямоугольника размещения](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Размещение всплывающей подсказки с помощью свойств Placement и PlacementRectangle  
  
 ![Схема положения подсказки](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Размещение всплывающей подсказки с помощью свойств Placement, PlacementRectangle и Offset  
  
 В следующем примере показано использование свойств <xref:System.Windows.Controls.ToolTip> для определения положения подсказки, содержимое которой является объектом <xref:System.Windows.Controls.ToolTip>.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 В следующем примере показано использование свойств <xref:System.Windows.Controls.ToolTipService> для определения положения подсказки, содержимое которой не является объектом <xref:System.Windows.Controls.ToolTip>.  
  
 [!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## См. также  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Практические руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md)   
 [Use the ContextMenuService and ToolTipService](http://msdn.microsoft.com/ru-ru/809b0e9c-d612-4cda-b8af-1a698c68f4d1)