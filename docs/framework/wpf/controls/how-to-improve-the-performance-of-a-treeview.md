---
title: Практическое руководство. Повышение производительности элемента управления TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 75f17c770af89f08fedfd3c8193a916901fe6f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="3950f-102">Практическое руководство. Повышение производительности элемента управления TreeView</span><span class="sxs-lookup"><span data-stu-id="3950f-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="3950f-103">Если <xref:System.Windows.Controls.TreeView> содержит много элементов, количество времени, необходимое для загрузки может вызвать значительные задержки в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="3950f-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="3950f-104">Можно сократить время загрузки, задав `VirtualizingStackPanel.IsVirtualizing` присоединенному свойству `true`.</span><span class="sxs-lookup"><span data-stu-id="3950f-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="3950f-105">Пользовательский Интерфейс также может медленно реагировать при прокрутке <xref:System.Windows.Controls.TreeView> с помощью колесика мыши или путем перетаскивания ползунка полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="3950f-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="3950f-106">Можно повысить производительность <xref:System.Windows.Controls.TreeView> при прокрутке, задав `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3950f-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3950f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3950f-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="3950f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3950f-108">Description</span></span>  
<span data-ttu-id="3950f-109">В следующем примере создается <xref:System.Windows.Controls.TreeView> , которая устанавливает `VirtualizingStackPanel.IsVirtualizing` вложенное свойство в значение true и `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> для оптимизации производительности.</span><span class="sxs-lookup"><span data-stu-id="3950f-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="3950f-110">Код</span><span class="sxs-lookup"><span data-stu-id="3950f-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="3950f-111">В следующем примере показано данные в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3950f-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="3950f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3950f-112">See Also</span></span>  
 [<span data-ttu-id="3950f-113">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="3950f-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
