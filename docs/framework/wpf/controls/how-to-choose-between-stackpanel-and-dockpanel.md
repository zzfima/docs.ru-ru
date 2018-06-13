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
ms.openlocfilehash: c9bfb8d29051a9cfa61d3fcb93b8bb9a68d14e00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551938"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="b982b-102">Практическое руководство. Выбор между StackPanel и DockPanel</span><span class="sxs-lookup"><span data-stu-id="b982b-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="b982b-103">В этом примере показано, как выбрать между <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel> при стека содержимого в <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="b982b-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b982b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b982b-104">Example</span></span>  
 <span data-ttu-id="b982b-105">Несмотря на то, что можно использовать любой <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.StackPanel> для расположения дочерних элементов, два элемента управления не всегда производят те же результаты.</span><span class="sxs-lookup"><span data-stu-id="b982b-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="b982b-106">Например, порядок, поместить дочерних элементов может повлиять на размер дочерних элементов в <xref:System.Windows.Controls.DockPanel> , но не в <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b982b-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b982b-107">Это различие возникает из-за <xref:System.Windows.Controls.StackPanel> стека в направлении <xref:System.Double>.<xref:System.Double.PositiveInfinity>, однако <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.</span><span class="sxs-lookup"><span data-stu-id="b982b-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="b982b-108">В следующем примере показано это ключевое различие между <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b982b-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b982b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b982b-109">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="b982b-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="b982b-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
