---
title: "Практическое руководство. Повышение производительности элемента управления TreeView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TreeView - элемент управления [WPF], повышение производительности"
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Повышение производительности элемента управления TreeView
Если элемент управления <xref:System.Windows.Controls.TreeView> содержит множество элементов, для их загрузки может потребоваться значительное время, что может привести к задержке в работе пользовательского интерфейса.  Время загрузки можно сократить, присвоив вложенному свойству <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> значение `true`.  Пользовательский интерфейс также может медленно реагировать на прокрутку пользователем элемента управления <xref:System.Windows.Controls.TreeView> с помощью колесика мыши или путем перетаскивания ползунка полосы прокрутки.  Производительность элемента управления <xref:System.Windows.Controls.TreeView> при прокрутке можно повысить, присвоив вложенному свойству <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> значение <xref:System.Windows.Controls.VirtualizationMode>.  
  
## Пример  
  
## Описание  
 В приведенном ниже примере создается элемент управления <xref:System.Windows.Controls.TreeView>, для оптимизации производительности свойству <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> которого присваивается значение true, а свойству <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> — значение <xref:System.Windows.Controls.VirtualizationMode>.  
  
## Код  
 [!code-xml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 В следующем примере показаны данные, использовавшиеся в предыдущем примере.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## См. также  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)