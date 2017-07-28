---
title: "Практическое руководство. Создание простых или сложных элементов TreeView | Microsoft Docs"
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
  - "Control - класс, TreeView, создание"
  - "TreeView - элемент управления, создание"
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание простых или сложных элементов TreeView
В этом примере показано создание простых или сложных элементов управления <xref:System.Windows.Controls.TreeView>.  
  
 <xref:System.Windows.Controls.TreeView> состоит из иерархии элементов управления <xref:System.Windows.Controls.TreeViewItem>, которые могут содержать простые текстовые строки, а также более сложное содержимое, такое как элементы управления <xref:System.Windows.Controls.Button> или <xref:System.Windows.Controls.StackPanel> с вложенным содержимым.  Можно явно определить содержимое <xref:System.Windows.Controls.TreeView> или содержимое может быть предоставлено источником данных.  В этом разделе приведены примеры этих понятий.  
  
## Пример  
 Свойство <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> для <xref:System.Windows.Controls.TreeViewItem> включает содержимое, которое <xref:System.Windows.Controls.TreeView> отображает для данного элемента.  <xref:System.Windows.Controls.TreeViewItem> также может иметь элементы управления <xref:System.Windows.Controls.TreeViewItem> в качестве дочерних элементов, которые можно определить с помощью свойства <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 В следующем примере показано явное определение содержимого <xref:System.Windows.Controls.TreeViewItem> с помощью задания для свойства <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> значения "текстовая строка".  
  
 [!code-xml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 В следующем примере показано, как определить дочерние элементы для <xref:System.Windows.Controls.TreeViewItem> с помощью определения <xref:System.Windows.Controls.ItemsControl.Items%2A>, которые являются элементами управления <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.TreeView>, где <xref:System.Windows.Data.XmlDataProvider> предоставляет содержимое <xref:System.Windows.Controls.TreeViewItem> и <xref:System.Windows.HierarchicalDataTemplate> определяет отображение содержимого.  
  
 [!code-xml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.TreeView>, где содержимое <xref:System.Windows.Controls.TreeViewItem> включает элементы управления <xref:System.Windows.Controls.DockPanel>, которые содержат вложенное содержимое.  
  
 [!code-xml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## См. также  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Обзор элемента управления "TreeView"](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)