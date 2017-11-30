---
title: "Практическое руководство. Создание ListViewItems с CheckBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Практическое руководство. Создание ListViewItems с CheckBox
В этом примере показано, как отобразить столбец <xref:System.Windows.Controls.CheckBox> элементы управления в <xref:System.Windows.Controls.ListView> элемент управления, использующий <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Пример  
 Чтобы создать столбец, содержащий <xref:System.Windows.Controls.CheckBox> элементы управления в <xref:System.Windows.Controls.ListView>, создайте <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>. Затем установите <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> из <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.  
  
 В следующем примере показан <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>. В примере выполняется привязка <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> свойство <xref:System.Windows.Controls.CheckBox> для <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> значение свойства <xref:System.Windows.Controls.ListViewItem> , которая его содержит. Таким образом, когда <xref:System.Windows.Controls.ListViewItem> , содержащий <xref:System.Windows.Controls.CheckBox> выбран, <xref:System.Windows.Controls.CheckBox> проверяется.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 В следующем примере показано, как создать столбец <xref:System.Windows.Controls.CheckBox> элементов управления. Чтобы сделать столбец, в примере задается <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> свойство <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
