---
title: Как выполнить Выбор между StackPanel и DockPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: 458ba2fe23ecde28b3eb15400e7a9fa49c4cca68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622537"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Как выполнить Выбор между StackPanel и DockPanel
В этом примере показано, как выбрать между использованием <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel> при стека содержимого в <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Пример  
 Несмотря на то, что можно использовать либо <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.StackPanel> для расположения дочерних элементов, два элемента управления не всегда дают одинаковые результаты. Например, порядок, что вы поместили дочерних элементов может повлиять на размер дочерних элементов в <xref:System.Windows.Controls.DockPanel> , но не в <xref:System.Windows.Controls.StackPanel>. Это различие возникает из-за <xref:System.Windows.Controls.StackPanel> направлении стека в <xref:System.Double>.<xref:System.Double.PositiveInfinity>, однако <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.  
  
 Следующий пример демонстрирует это ключевое различие между <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
