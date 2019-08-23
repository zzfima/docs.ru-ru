---
title: Практическое руководство. Разделение пространства с помощью элемента DockPanel
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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960190"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Практическое руководство. Разделение пространства с помощью элемента DockPanel
В следующем примере создается простая [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] платформа <xref:System.Windows.Controls.DockPanel> с помощью элемента. <xref:System.Windows.Controls.DockPanel> Секция разделяет доступное место для дочерних элементов.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Windows.Controls.DockPanel.Dock%2A> свойство, которое является присоединенным свойством, чтобы закрепить два одинаковых <xref:System.Windows.Controls.Border> элемента <xref:System.Windows.Controls.Dock.Top> в разделе с секционированным пространством. Третий <xref:System.Windows.Controls.Border> элемент закрепляется <xref:System.Windows.Controls.Dock.Left>в, ширина которого равна 200 пикселей. Четвертый <xref:System.Windows.Controls.Border> элемент закрепляется <xref:System.Windows.Controls.Dock.Bottom> на экране. Последний <xref:System.Windows.Controls.Border> элемент автоматически заполняет оставшееся пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> По умолчанию последний дочерний <xref:System.Windows.Controls.DockPanel> элемент элемента заполняет оставшееся незанятое пространство. Если в этом нет необходимости, следует задать `LastChildFill="False"`.  
  
 Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.  
  
 ![Обычный сценарий DockPanel.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DockPanel>
- [Общие сведения о панелях](panels-overview.md)
