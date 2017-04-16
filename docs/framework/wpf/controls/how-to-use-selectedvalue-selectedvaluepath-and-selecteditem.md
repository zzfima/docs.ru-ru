---
title: "Инструкция по Использованию SelectedValue, SelectedValuePath и SelectedItem | Microsoft Docs"
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
  - "Control - класс, SelectedItem - свойства"
  - "Control - класс, SelectedValue - свойства"
  - "Control - класс, SelectedValuePath - свойства"
  - "Control - класс, TreeView - свойства"
  - "SelectedValue, SelectedItem - свойства"
  - "SelectedValue, SelectedValuePath - свойства"
  - "TreeView - элемент управления, SelectedItem - свойства"
  - "TreeView - элемент управления, SelectedValue - свойства"
  - "TreeView - элемент управления, SelectedValuePath - свойства"
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Инструкция по Использованию SelectedValue, SelectedValuePath и SelectedItem
В этом примере показано, как использовать свойства <xref:System.Windows.Controls.TreeView.SelectedValue%2A> и <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> для указания значения для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> элемента <xref:System.Windows.Controls.TreeView>.  
  
## Пример  
 Свойство <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> предоставляет возможность указать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> элемента <xref:System.Windows.Controls.TreeView>.  <xref:System.Windows.Controls.TreeView.SelectedItem%2A> представляет объект в коллекции <xref:System.Windows.Controls.ItemsControl.Items%2A> и <xref:System.Windows.Controls.TreeView> отображает значение одного свойства выбранного элемента.  Свойство <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> указывает путь к свойству, используемому для определения значения свойства <xref:System.Windows.Controls.TreeView.SelectedValue%2A>.  В примерах этого раздела показана эта концепция.  
  
 Следующий пример демонстрирует <xref:System.Windows.Data.XmlDataProvider>, содержащий сведения о сотруднике.  
  
 [!code-xml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 В следующем примере определяется <xref:System.Windows.HierarchicalDataTemplate>, отображающий `EmployeeName` и `EmployeeWorkDay` из `Employee`.  Обратите внимание, что <xref:System.Windows.HierarchicalDataTemplate> не указывает `EmployeeNumber` в качестве части шаблона.  
  
 [!code-xml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Следующий пример демонстрирует <xref:System.Windows.Controls.TreeView>, использующий ранее определенный <xref:System.Windows.HierarchicalDataTemplate>, и устанавливает свойство <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для `EmployeeNumber`.  Когда выбирается `EmployeeName` в <xref:System.Windows.Controls.TreeView>, свойство <xref:System.Windows.Controls.TreeView.SelectedItem%2A> возвращает элемент данных `EmployeeInfo`, соответствующий выбранному `EmployeeName`.  Однако, так как <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> из этого <xref:System.Windows.Controls.TreeView> устанавливает значение в `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> устанавливает значение в `EmployeeNumber`.  
  
 [!code-xml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## См. также  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Обзор элемента управления "TreeView"](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)