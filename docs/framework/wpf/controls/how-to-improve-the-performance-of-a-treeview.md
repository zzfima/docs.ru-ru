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
ms.locfileid: "33552757"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Практическое руководство. Повышение производительности элемента управления TreeView
Если <xref:System.Windows.Controls.TreeView> содержит много элементов, количество времени, необходимое для загрузки может вызвать значительные задержки в пользовательском интерфейсе. Можно сократить время загрузки, задав `VirtualizingStackPanel.IsVirtualizing` присоединенному свойству `true`.  Пользовательский Интерфейс также может медленно реагировать при прокрутке <xref:System.Windows.Controls.TreeView> с помощью колесика мыши или путем перетаскивания ползунка полосы прокрутки. Можно повысить производительность <xref:System.Windows.Controls.TreeView> при прокрутке, задав `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание  
В следующем примере создается <xref:System.Windows.Controls.TreeView> , которая устанавливает `VirtualizingStackPanel.IsVirtualizing` вложенное свойство в значение true и `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> для оптимизации производительности.  
  
## <a name="code"></a>Код  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 В следующем примере показано данные в предыдущем примере.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
