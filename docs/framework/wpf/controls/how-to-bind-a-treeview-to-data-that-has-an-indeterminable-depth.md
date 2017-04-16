---
title: "Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины | Microsoft Docs"
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
  - "TreeView - элемент управления [WPF], привязка к данным неопределенной глубины"
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины
В некоторых случаях бывает необходимо выполнить привязку элемента управления <xref:System.Windows.Controls.TreeView> к источнику данных, глубина которого неизвестна.  Это возможно, если данные имеют рекурсивную природу. Примером таких данных является файловая система, в которой папки могут содержать другие папки, или организационная структура компании, в которой одни сотрудники непосредственно подчинены другим.  
  
 Источник данных может иметь иерархическую объектную модель.  Например, класс `Employee` может содержать коллекцию объектов Employee \(сотрудник\), которые напрямую подчиняются данному сотруднику.  Если данные представлены в неиерархическом виде, необходимо построить иерархическое представление данных.  
  
 При присвоении значения свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=fullName> и при создании элементом управления <xref:System.Windows.Controls.ItemsControl> элемента управления <xref:System.Windows.Controls.ItemsControl> для каждого дочернего элемента, дочерний элемент управления <xref:System.Windows.Controls.ItemsControl> использует тот же самый элемент управления <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> в качестве родительского элемента.  Например, при задании свойства <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для привязанного к данным элемента управления <xref:System.Windows.Controls.TreeView> каждый созданный элемент <xref:System.Windows.Controls.TreeViewItem> использует объект <xref:System.Windows.DataTemplate>, присвоенный свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> элемента управления <xref:System.Windows.Controls.TreeView>.  
  
 Объект <xref:System.Windows.HierarchicalDataTemplate> позволяет указать объект <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для элемента <xref:System.Windows.Controls.TreeViewItem> или любого элемента управления <xref:System.Windows.Controls.HeaderedItemsControl> в шаблоне данных.  При задании свойства <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=fullName> его значение используется при применении шаблона данных <xref:System.Windows.HierarchicalDataTemplate>.  Используя <xref:System.Windows.HierarchicalDataTemplate> можно рекурсивно задать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого элемента <xref:System.Windows.Controls.TreeViewItem> в элементе управления <xref:System.Windows.Controls.TreeView>.  
  
## Пример  
 В приведенном ниже примере демонстрируется привязка элемента управления <xref:System.Windows.Controls.TreeView> к иерархическим данным, а шаблон <xref:System.Windows.HierarchicalDataTemplate> используется для указания <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого элемента <xref:System.Windows.Controls.TreeViewItem>.  Элемент управления <xref:System.Windows.Controls.TreeView> привязывается к XML\-данным о сотрудниках компании.  Каждый элемент `Employee` может содержать другие элементы `Employee`, чтобы указать, какой сотрудник кому подчиняется.  Поскольку данные являются рекурсивными, шаблон <xref:System.Windows.HierarchicalDataTemplate> можно применить к каждому уровню.  
  
 [!code-xml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)