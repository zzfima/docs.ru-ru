---
title: "Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView
В этом примере показано, как использовать <xref:System.Windows.DataTemplate> и <xref:System.Windows.Style> объектов для определения внешнего вида <xref:System.Windows.Controls.ListView> управления, который использует <xref:System.Windows.Controls.GridView> режим просмотра.  
  
## <a name="example"></a>Пример  
 В приведенных ниже примерах <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объектов, настроить внешний вид заголовка столбца для <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Приведенный ниже показано, как использовать эти <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объекты для установки <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> свойства <xref:System.Windows.Controls.GridViewColumn>. <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Свойство определяет содержимое ячеек столбца.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> И <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> только два из свойств, которые можно использовать для настройки внешнего вида заголовка столбца для <xref:System.Windows.Controls.GridView> элемента управления. Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 В следующем примере показан способ определения <xref:System.Windows.DataTemplate> , настраивает внешний вид ячеек в <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 В следующем примере показано, как этот метод следует использовать <xref:System.Windows.DataTemplate> для определения содержимого <xref:System.Windows.Controls.GridViewColumn> ячейки. Этот шаблон используется вместо <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойство, которое показано в предыдущем <xref:System.Windows.Controls.GridViewColumn> примере.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
