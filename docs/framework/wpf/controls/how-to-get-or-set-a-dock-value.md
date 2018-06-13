---
title: Практическое руководство. Получение или задание значения Dock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: b792c8b2342416fb380827b702efa28885145d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554786"
---
# <a name="how-to-get-or-set-a-dock-value"></a>Практическое руководство. Получение или задание значения Dock
В следующем примере показано, как назначить <xref:System.Windows.Controls.Dock> значение для объекта. В этом примере <xref:System.Windows.Controls.DockPanel.GetDock%2A> и <xref:System.Windows.Controls.DockPanel.SetDock%2A> методы <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Пример  
 В примере создается экземпляр <xref:System.Windows.Controls.TextBlock> элемент, `txt1`и назначает <xref:System.Windows.Controls.Dock> значение `Top` с помощью <xref:System.Windows.Controls.DockPanel.SetDock%2A> метод <xref:System.Windows.Controls.DockPanel>. Затем он устанавливает значение <xref:System.Windows.Controls.Dock> свойства <xref:System.Windows.Controls.TextBlock.Text%2A> из <xref:System.Windows.Controls.TextBlock> элемента с помощью <xref:System.Windows.Controls.DockPanel.GetDock%2A> метод. Наконец, в примере добавляется <xref:System.Windows.Controls.TextBlock> элемента с родительским <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
