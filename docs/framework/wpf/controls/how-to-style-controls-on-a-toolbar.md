---
title: Как выполнить Определение стиля элементов управления в панели инструментов
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 097bb23a41ba68bf9c121a53920f19694508348b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544865"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>Как выполнить Определение стиля элементов управления в панели инструментов
<xref:System.Windows.Controls.ToolBar> Определяет <xref:System.Windows.ResourceKey> объектов для задания стиля элементов управления в <xref:System.Windows.Controls.ToolBar>.  Для стиля элемента управления в <xref:System.Windows.Controls.ToolBar>, задайте `x:key` атрибута стиля для <xref:System.Windows.ResourceKey> определенные в <xref:System.Windows.Controls.ToolBar>.  
  
 <xref:System.Windows.Controls.ToolBar> Определяет следующие <xref:System.Windows.ResourceKey> объектов:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере определяется стили для элементов управления в пределах <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>См. также
- [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
