---
title: "Практическое руководство. Получение или задание значения Dock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d663acf446ee2f7a36fc2d0c8605c31a0f2a84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="d9b6e-102">Практическое руководство. Получение или задание значения Dock</span><span class="sxs-lookup"><span data-stu-id="d9b6e-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="d9b6e-103">В следующем примере показано, как назначить <xref:System.Windows.Controls.Dock> значение для объекта.</span><span class="sxs-lookup"><span data-stu-id="d9b6e-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="d9b6e-104">В этом примере <xref:System.Windows.Controls.DockPanel.GetDock%2A> и <xref:System.Windows.Controls.DockPanel.SetDock%2A> методы <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="d9b6e-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9b6e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d9b6e-105">Example</span></span>  
 <span data-ttu-id="d9b6e-106">В примере создается экземпляр <xref:System.Windows.Controls.TextBlock> элемент, `txt1`и назначает <xref:System.Windows.Controls.Dock> значение `Top` с помощью <xref:System.Windows.Controls.DockPanel.SetDock%2A> метод <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="d9b6e-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="d9b6e-107">Затем он устанавливает значение <xref:System.Windows.Controls.Dock> свойства <xref:System.Windows.Controls.TextBlock.Text%2A> из <xref:System.Windows.Controls.TextBlock> элемента с помощью <xref:System.Windows.Controls.DockPanel.GetDock%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d9b6e-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="d9b6e-108">Наконец, в примере добавляется <xref:System.Windows.Controls.TextBlock> элемента с родительским <xref:System.Windows.Controls.DockPanel>, `dp1`.</span><span class="sxs-lookup"><span data-stu-id="d9b6e-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d9b6e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d9b6e-109">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [<span data-ttu-id="d9b6e-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="d9b6e-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
