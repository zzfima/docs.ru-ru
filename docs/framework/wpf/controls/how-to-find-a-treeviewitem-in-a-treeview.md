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
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962096"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Практическое руководство. Поиск элемента TreeViewItem в TreeView
<xref:System.Windows.Controls.TreeView> Элемент управления предоставляет удобный способ для показа иерархических данных. Если привязка привязана к источнику данных <xref:System.Windows.Controls.TreeView.SelectedItem%2A> , это свойство предоставляет удобный способ быстрого извлечения выбранного объекта данных. <xref:System.Windows.Controls.TreeView> Обычно лучше работать с базовым объектом данных, но иногда может потребоваться программно манипулировать содержащимся <xref:System.Windows.Controls.TreeViewItem>в нем данным. Например, может потребоваться программное расширение <xref:System.Windows.Controls.TreeViewItem>или выбор другого элемента <xref:System.Windows.Controls.TreeView>в.  
  
 Для поиска <xref:System.Windows.Controls.TreeViewItem> объекта, содержащего конкретный объект данных, необходимо пройти по <xref:System.Windows.Controls.TreeView>каждому уровню. Элементы в <xref:System.Windows.Controls.TreeView> можно также виртуализованы для повышения производительности. В случае, когда элементы могут быть виртуализированы, необходимо также реализовать, <xref:System.Windows.Controls.TreeViewItem> чтобы проверить, содержит ли он объект данных.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание  
 В следующем примере выполняется поиск <xref:System.Windows.Controls.TreeView> определенного объекта и возвращается объект, содержащий. <xref:System.Windows.Controls.TreeViewItem> В этом примере создается экземпляр <xref:System.Windows.Controls.TreeViewItem> каждого экземпляра, чтобы можно было выполнять поиск его дочерних элементов. Этот пример также работает, <xref:System.Windows.Controls.TreeView> если не использует виртуализированные элементы.  
  
> [!NOTE]
> Следующий пример работает для любого <xref:System.Windows.Controls.TreeView>, независимо от базовой модели данных, и ищет все <xref:System.Windows.Controls.TreeViewItem> объекты до тех пор, пока объект не будет найден. Другой способ, имеющий лучшую производительность, — поиск в модели данных указанного объекта, отслеживание его расположения в иерархии данных, а затем поиск соответствующего <xref:System.Windows.Controls.TreeViewItem> элемента <xref:System.Windows.Controls.TreeView>в. Однако метод, имеющий лучшую производительность, требует знания модели данных и не может быть обобщен для всех указанных <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Код  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Предыдущий код полагается на пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel> объект, предоставляющий метод с именем. `BringIntoView` Следующий код определяет пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel>объект.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 В следующем коде XAML показано, как создать <xref:System.Windows.Controls.TreeView> объект, использующий пользовательский. <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>См. также

- [Повышение производительности элемента управления TreeView](how-to-improve-the-performance-of-a-treeview.md)
