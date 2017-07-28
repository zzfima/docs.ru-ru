---
title: "Практическое руководство. Поиск элемента TreeViewItem в TreeView | Microsoft Docs"
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
  - "TreeView - элемент управления [WPF], поиск TreeViewItem"
  - "TreeViewItem [WPF], поиск"
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Поиск элемента TreeViewItem в TreeView
Элемент управления <xref:System.Windows.Controls.TreeView> предоставляет удобный способ отображения иерархических данных.  Если элемент управления <xref:System.Windows.Controls.TreeView> привязан к источнику данных, свойство <xref:System.Windows.Controls.TreeView.SelectedItem%2A> предоставляет удобный способ быстрого извлечения выбранного объекта данных.  Обычно лучше всего работать с базовым объектом данных, однако иногда требуется программно управлять элементом управления <xref:System.Windows.Controls.TreeViewItem>, содержащим данные.  Например, может возникать необходимость в программном расширении элемента управления <xref:System.Windows.Controls.TreeViewItem> или в выборе другого элемента из элемента управления <xref:System.Windows.Controls.TreeView>.  
  
 Чтобы найти элемент управления <xref:System.Windows.Controls.TreeViewItem>, содержащий конкретный объект данных, необходимо пройти каждый уровень <xref:System.Windows.Controls.TreeView>.  Для повышения производительности можно также виртуализировать элементы <xref:System.Windows.Controls.TreeView>.  В случае виртуализации элементов необходимо также реализовать элемент управления <xref:System.Windows.Controls.TreeViewItem>, чтобы проверить, содержит ли он объект данных.  
  
## Пример  
  
## Описание  
 В следующем примере выполняется поиск определенного объекта в элементе управления <xref:System.Windows.Controls.TreeView> и возвращается элемент <xref:System.Windows.Controls.TreeViewItem>, содержащий этот объект.  В примере создается экземпляр каждого элемента <xref:System.Windows.Controls.TreeViewItem> для обеспечения возможности поиска его дочерних элементов.  Пример также работает, если в <xref:System.Windows.Controls.TreeView> не используются виртуализированные элементы.  
  
> [!NOTE]
>  Следующий пример работает для любого элемента управления <xref:System.Windows.Controls.TreeView>, независимо от базовой модели данных; в нем выполняется поиск в каждом элементе <xref:System.Windows.Controls.TreeViewItem> до тех пор, пока не будет найдет требуемый объект.  Другой метод, характеризующийся более высокой производительностью, состоит в поиске определенного объекта в модели данных, отслеживании его расположения в иерархии данных и последующем поиске соответствующего элемента <xref:System.Windows.Controls.TreeViewItem> в элементе управления <xref:System.Windows.Controls.TreeView>.  Однако для реализации этого более производительного метода требуется знание модели данных, и его нельзя обобщить для любого заданного элемента управления <xref:System.Windows.Controls.TreeView>.  
  
## Код  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 В предыдущем коде использовался пользовательский элемент управления <xref:System.Windows.Controls.VirtualizingStackPanel>, предоставляющий метод `BringIntoView`.  В следующем коде определяется пользовательский элемент управления <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 В следующем коде XAML показано создание элемента управления <xref:System.Windows.Controls.TreeView>, использующего пользовательский элемент управления <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## См. также  
 [Повышение производительности элемента управления TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)