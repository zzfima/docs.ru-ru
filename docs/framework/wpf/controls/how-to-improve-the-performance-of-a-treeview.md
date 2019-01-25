---
title: Как выполнить Повышение производительности элемента управления TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 3c7bd151e1c8a5f318660cc45702b5b9c98534a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500698"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Как выполнить Повышение производительности элемента управления TreeView
Если <xref:System.Windows.Controls.TreeView> содержит много элементов, количество времени, затрачиваемого на загрузку может привести к значительной задержке в пользовательском интерфейсе. Можно сократить время загрузки, задав `VirtualizingStackPanel.IsVirtualizing` вложенное свойство, чтобы `true`.  Пользовательский Интерфейс также может медленно реагировать при прокрутке <xref:System.Windows.Controls.TreeView> , используя колесико мыши или перетаскивания ползунка полосы прокрутки. Можно повысить производительность <xref:System.Windows.Controls.TreeView> при прокрутке, задав `VirtualizingStackPanel.VirtualizationMode` вложенное свойство, чтобы <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание:  
В следующем примере создается <xref:System.Windows.Controls.TreeView> , задает `VirtualizingStackPanel.IsVirtualizing` присоединенное свойство в значение true и `VirtualizingStackPanel.VirtualizationMode` вложенное свойство, чтобы <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> для оптимизации производительности.  
  
## <a name="code"></a>Код  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 В следующем примере показано данные в предыдущем примере.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>См. также
- [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
