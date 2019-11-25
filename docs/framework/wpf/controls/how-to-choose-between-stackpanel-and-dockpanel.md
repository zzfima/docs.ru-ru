---
title: Практическое руководство. Выбор между StackPanel и DockPanel
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
ms.openlocfilehash: bdf4b38e67a7856136224368e86609c135e5ad6f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976440"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Практическое руководство. Выбор между StackPanel и DockPanel
В этом примере показано, как выбрать между использованием <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel> при стеке содержимого в <xref:System.Windows.Controls.Panel>.

## <a name="example"></a>Пример
 Хотя можно использовать либо <xref:System.Windows.Controls.DockPanel>, либо <xref:System.Windows.Controls.StackPanel> для размещения дочерних элементов, эти два элемента управления не всегда дают одинаковые результаты. Например, порядок размещения дочерних элементов может повлиять на размер дочерних элементов в <xref:System.Windows.Controls.DockPanel>, но не в <xref:System.Windows.Controls.StackPanel>. Это различное поведение обусловлено тем, что <xref:System.Windows.Controls.StackPanel> меры в направлении наложения в [Double. PositiveInfinity](xref:System.Double.PositiveInfinity); Однако <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.

 В следующем примере демонстрируется это ключевое различие между <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel>.

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [Общие сведения о панелях](panels-overview.md)
