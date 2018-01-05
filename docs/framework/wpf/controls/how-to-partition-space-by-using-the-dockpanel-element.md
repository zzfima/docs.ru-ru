---
title: "Практическое руководство. Разделение пространства с помощью элемента DockPanel"
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
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4adfabba76e9f6bf32e47fe4e52e42b68676bc0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="71598-102">Практическое руководство. Разделение пространства с помощью элемента DockPanel</span><span class="sxs-lookup"><span data-stu-id="71598-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="71598-103">В следующем примере создается простой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework с помощью <xref:System.Windows.Controls.DockPanel> элемента.</span><span class="sxs-lookup"><span data-stu-id="71598-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="71598-104"><xref:System.Windows.Controls.DockPanel> Разделяет доступное пространство его дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="71598-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71598-105">Пример</span><span class="sxs-lookup"><span data-stu-id="71598-105">Example</span></span>  
 <span data-ttu-id="71598-106">В этом примере используется <xref:System.Windows.Controls.DockPanel.Dock%2A> свойство, которое является присоединенным свойством, чтобы прикрепить два идентичных <xref:System.Windows.Controls.Border> элементы <xref:System.Windows.Controls.Dock.Top> разделенного пространства.</span><span class="sxs-lookup"><span data-stu-id="71598-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="71598-107">В третьем <xref:System.Windows.Controls.Border> элемент прикрепляется к <xref:System.Windows.Controls.Dock.Left>, с шириной 200 пикселей.</span><span class="sxs-lookup"><span data-stu-id="71598-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="71598-108">Четвертый <xref:System.Windows.Controls.Border> прикрепляется к <xref:System.Windows.Controls.Dock.Bottom> экрана.</span><span class="sxs-lookup"><span data-stu-id="71598-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="71598-109">Последний <xref:System.Windows.Controls.Border> элемент автоматически заполняет оставшееся пространство.</span><span class="sxs-lookup"><span data-stu-id="71598-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="71598-110">По умолчанию, последний дочерний <xref:System.Windows.Controls.DockPanel> элемент заполняет оставшееся незанятое пространство.</span><span class="sxs-lookup"><span data-stu-id="71598-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="71598-111">Если в этом нет необходимости, следует задать `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="71598-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="71598-112">Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.</span><span class="sxs-lookup"><span data-stu-id="71598-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="71598-113">![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="71598-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71598-114">См. также</span><span class="sxs-lookup"><span data-stu-id="71598-114">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="71598-115">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="71598-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
