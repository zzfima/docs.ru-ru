---
title: Практическое руководство. Поиск элемента TreeViewItem в TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: cff931312e6bc6db5ae5f26c0db80ad2f43825f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Практическое руководство. Поиск элемента TreeViewItem в TreeView
<xref:System.Windows.Controls.TreeView> Элемент управления предоставляет удобный способ отображения иерархических данных. Если ваш <xref:System.Windows.Controls.TreeView> привязан к источнику данных, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> свойству предоставляет удобный способ для быстрого извлечения выбранного объекта данных. Обычно лучше всего работать с базовым объектом данных, но иногда необходимо программно манипулировать данных, содержащих <xref:System.Windows.Controls.TreeViewItem>. Например, может потребоваться программно разверните <xref:System.Windows.Controls.TreeViewItem>, или выберите другой элемент в <xref:System.Windows.Controls.TreeView>.  
  
 Чтобы найти <xref:System.Windows.Controls.TreeViewItem> , содержащий конкретный объект данных, необходимо пройти каждый уровень <xref:System.Windows.Controls.TreeView>. Элементы в <xref:System.Windows.Controls.TreeView> также можно виртуализировать для повышения производительности. В случае, когда виртуализации элементов необходимо также реализовать <xref:System.Windows.Controls.TreeViewItem> Чтобы проверить, содержит ли объект данных.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание  
 В следующем примере выполняется поиск <xref:System.Windows.Controls.TreeView> для указанного объекта и возвращает объект, содержащего <xref:System.Windows.Controls.TreeViewItem>. В примере проверяется, чтобы каждый <xref:System.Windows.Controls.TreeViewItem> создается, чтобы его дочерние элементы можно искать. В этом примере также работает, если <xref:System.Windows.Controls.TreeView> используются виртуализированные элементы.  
  
> [!NOTE]
>  Следующий пример работает для любого <xref:System.Windows.Controls.TreeView>, независимо от базовой модели данных и выполняет каждый <xref:System.Windows.Controls.TreeViewItem> пока объект найден. Другим способом, который имеет более высокую производительность является поиск модели данных для указанного объекта, отслеживать его положение в иерархии данных и затем найти соответствующий <xref:System.Windows.Controls.TreeViewItem> в <xref:System.Windows.Controls.TreeView>. Тем не менее, метод, который имеет более высокую производительность требует знаний модели данных и не может быть обобщена для любой заданной <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Код  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Предыдущий код использует пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel> , предоставляет метод с именем `BringIntoView`. Следующий код определяет пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Приведенный ниже код XAML показан способ создания <xref:System.Windows.Controls.TreeView> , использующего пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>См. также  
 [Повышение производительности элемента управления TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
