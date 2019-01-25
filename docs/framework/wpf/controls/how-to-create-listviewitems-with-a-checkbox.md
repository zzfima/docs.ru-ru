---
title: Как выполнить Создание элементов ListView с помощью CheckBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: 1ed623495529609c83c0ced68bfc1696c29d4570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682246"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Как выполнить Создание элементов ListView с помощью CheckBox
В этом примере показано, как отобразить столбец <xref:System.Windows.Controls.CheckBox> элементов управления в <xref:System.Windows.Controls.ListView> элемента управления, использующего <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Пример  
 Чтобы создать столбец, содержащий <xref:System.Windows.Controls.CheckBox> элементов управления в <xref:System.Windows.Controls.ListView>, создание <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>. Затем установите <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> из <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.  
  
 В следующем примере показан <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>. В примере выполняется привязка <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> свойство <xref:System.Windows.Controls.CheckBox> для <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> значение свойства <xref:System.Windows.Controls.ListViewItem> , которая его содержит. Таким образом, когда <xref:System.Windows.Controls.ListViewItem> , содержащий <xref:System.Windows.Controls.CheckBox> выбран, <xref:System.Windows.Controls.CheckBox> проверяется.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 В следующем примере показано, как создать столбец <xref:System.Windows.Controls.CheckBox> элементов управления. Чтобы сделать столбец, в примере задается <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> свойство <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
