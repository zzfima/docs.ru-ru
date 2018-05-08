---
title: Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 30e328c94e1e1da4641e93dd5f5730eab2d8af1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины
Возможны ситуации, когда вы хотите привязать <xref:System.Windows.Controls.TreeView> к источнику данных, глубина которого неизвестен.  Это может произойти, когда данные рекурсивных по своей природе, например в файловой системе, где папок может содержать папки, или организационной структуры компании, где сотрудники имеют других сотрудников в качестве подчиненных.  
  
 Источник данных должен иметь иерархическую объектную модель. Например `Employee` класс может содержать коллекцию объектов Employee, подчиненных сотрудника. Если данные представлены в виде, не является иерархической, необходимо построить иерархическое представление данных.  
  
 При задании <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> свойства и, если <xref:System.Windows.Controls.ItemsControl> приводит к возникновению ошибки <xref:System.Windows.Controls.ItemsControl> для каждого дочернего элемента, а затем дочерние <xref:System.Windows.Controls.ItemsControl> использует тот же самый <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> как родительский элемент. Например, если задать <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство для привязки к данным <xref:System.Windows.Controls.TreeView>, каждая <xref:System.Windows.Controls.TreeViewItem> , созданный использует <xref:System.Windows.DataTemplate> , назначенный для <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство <xref:System.Windows.Controls.TreeView>.  
  
 <xref:System.Windows.HierarchicalDataTemplate> Дает возможность указать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.TreeViewItem>, или любой <xref:System.Windows.Controls.HeaderedItemsControl>, шаблон данных. При задании <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> свойство, значение используется, когда <xref:System.Windows.HierarchicalDataTemplate> применяется. С помощью <xref:System.Windows.HierarchicalDataTemplate>, то можно установить рекурсивно <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого <xref:System.Windows.Controls.TreeViewItem> в <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как привязать <xref:System.Windows.Controls.TreeView> иерархических данных и используйте <xref:System.Windows.HierarchicalDataTemplate> для указания <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого <xref:System.Windows.Controls.TreeViewItem>.  <xref:System.Windows.Controls.TreeView> Привязывается к XML-данные о сотрудниках компании.  Каждый `Employee` элемент может содержать другие `Employee` элементов, чтобы указать, кому подчиняется. Поскольку данные являются рекурсивными, <xref:System.Windows.HierarchicalDataTemplate> может применяться к каждому уровню.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)
