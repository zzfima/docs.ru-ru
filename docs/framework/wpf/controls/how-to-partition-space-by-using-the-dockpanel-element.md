---
title: Как выполнить Разделение пространства с помощью элемента DockPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 8b79b89e512ec9da27774188aeaeed8ebd5b1153
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577663"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Как выполнить Разделение пространства с помощью элемента DockPanel
В следующем примере создается простой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework с помощью <xref:System.Windows.Controls.DockPanel> элемент. <xref:System.Windows.Controls.DockPanel> Разделяет доступное пространство между его дочерних элементов.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Windows.Controls.DockPanel.Dock%2A> свойство, которое является присоединенным свойством, чтобы прикрепить два идентичных <xref:System.Windows.Controls.Border> элементы <xref:System.Windows.Controls.Dock.Top> разделенного пространства. Третий <xref:System.Windows.Controls.Border> прикреплен данный элемент <xref:System.Windows.Controls.Dock.Left>, шириной 200 пикселей. Четвертый <xref:System.Windows.Controls.Border> закреплены <xref:System.Windows.Controls.Dock.Bottom> экрана. Последний <xref:System.Windows.Controls.Border> элемент автоматически заполняет оставшееся пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  По умолчанию последний дочерний узел данного <xref:System.Windows.Controls.DockPanel> элемент заполняет оставшееся незанятое пространство. Если в этом нет необходимости, следует задать `LastChildFill="False"`.  
  
 Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.  
  
 ![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.DockPanel>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
