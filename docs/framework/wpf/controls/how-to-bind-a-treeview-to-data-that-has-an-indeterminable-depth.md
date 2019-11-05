---
title: Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458618"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Практическое руководство. Привязка элемента управления TreeView к данным неопределенной глубины
Иногда возникает необходимость привязать <xref:System.Windows.Controls.TreeView> к источнику данных, глубина которого неизвестна.  Это может произойти, когда данные являются рекурсивными, например в файловой системе, где папки могут содержать папки или организационную структуру компании, где сотрудники имеют другие сотрудники в качестве прямых отчетов.  
  
 Источник данных должен иметь иерархическую объектную модель. Например, класс `Employee` может содержать коллекцию объектов Employee, которые являются прямыми отчетами сотрудника. Если данные представлены способом, который не является иерархическим, необходимо построить иерархическое представление данных.  
  
 Если задать свойство <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.ItemsControl> создает <xref:System.Windows.Controls.ItemsControl> для каждого дочернего элемента, дочерний <xref:System.Windows.Controls.ItemsControl> использует тот же <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, что и родительский элемент. Например, если задать свойство <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для привязанного к данным <xref:System.Windows.Controls.TreeView>, то каждый создаваемый <xref:System.Windows.Controls.TreeViewItem> использует <xref:System.Windows.DataTemplate>, назначенный свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.TreeView>.  
  
 <xref:System.Windows.HierarchicalDataTemplate> позволяет указать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.TreeViewItem>или любого <xref:System.Windows.Controls.HeaderedItemsControl>в шаблоне данных. При задании свойства <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> это значение используется при применении <xref:System.Windows.HierarchicalDataTemplate>. С помощью <xref:System.Windows.HierarchicalDataTemplate>можно рекурсивно задать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого <xref:System.Windows.Controls.TreeViewItem> в <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как привязать <xref:System.Windows.Controls.TreeView> к иерархическим данным и использовать <xref:System.Windows.HierarchicalDataTemplate>, чтобы указать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для каждого <xref:System.Windows.Controls.TreeViewItem>.  <xref:System.Windows.Controls.TreeView> привязывается к XML-данным, представляющим сотрудников компании.  Каждый элемент `Employee` может содержать другие элементы `Employee`, чтобы указать, кому именно отчет. Так как данные являются рекурсивными, <xref:System.Windows.HierarchicalDataTemplate> можно применить к каждому уровню.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
