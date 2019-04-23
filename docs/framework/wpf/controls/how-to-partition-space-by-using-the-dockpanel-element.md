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
ms.openlocfilehash: ab51270644bf370944ebc933c765b40c528681c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158890"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="77147-102">Практическое руководство. Разделение пространства с помощью элемента DockPanel</span><span class="sxs-lookup"><span data-stu-id="77147-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="77147-103">В следующем примере создается простой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework с помощью <xref:System.Windows.Controls.DockPanel> элемент.</span><span class="sxs-lookup"><span data-stu-id="77147-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="77147-104"><xref:System.Windows.Controls.DockPanel> Разделяет доступное пространство между его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="77147-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77147-105">Пример</span><span class="sxs-lookup"><span data-stu-id="77147-105">Example</span></span>  
 <span data-ttu-id="77147-106">В этом примере используется <xref:System.Windows.Controls.DockPanel.Dock%2A> свойство, которое является присоединенным свойством, чтобы прикрепить два идентичных <xref:System.Windows.Controls.Border> элементы <xref:System.Windows.Controls.Dock.Top> разделенного пространства.</span><span class="sxs-lookup"><span data-stu-id="77147-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="77147-107">Третий <xref:System.Windows.Controls.Border> прикреплен данный элемент <xref:System.Windows.Controls.Dock.Left>, шириной 200 пикселей.</span><span class="sxs-lookup"><span data-stu-id="77147-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="77147-108">Четвертый <xref:System.Windows.Controls.Border> закреплены <xref:System.Windows.Controls.Dock.Bottom> экрана.</span><span class="sxs-lookup"><span data-stu-id="77147-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="77147-109">Последний <xref:System.Windows.Controls.Border> элемент автоматически заполняет оставшееся пространство.</span><span class="sxs-lookup"><span data-stu-id="77147-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="77147-110">По умолчанию последний дочерний узел данного <xref:System.Windows.Controls.DockPanel> элемент заполняет оставшееся незанятое пространство.</span><span class="sxs-lookup"><span data-stu-id="77147-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="77147-111">Если в этом нет необходимости, следует задать `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="77147-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="77147-112">Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.</span><span class="sxs-lookup"><span data-stu-id="77147-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="77147-113">![Обычный сценарий DockPanel.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="77147-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77147-114">См. также</span><span class="sxs-lookup"><span data-stu-id="77147-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="77147-115">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="77147-115">Panels Overview</span></span>](panels-overview.md)
