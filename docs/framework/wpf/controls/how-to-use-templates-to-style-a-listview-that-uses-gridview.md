---
title: "Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView | Microsoft Docs"
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
  - "ListView - элементы управления, применение стилей"
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView
В данном примере показано использование объектов <xref:System.Windows.DataTemplate> и <xref:System.Windows.Style> для задания внешнего вида элемента управления <xref:System.Windows.Controls.ListView>, использующего режим представления <xref:System.Windows.Controls.GridView>.  
  
## Пример  
 В следующих примерах показаны объекты <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate>, которые настраивают внешний вид заголовка столбца для <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 В следующем примере показано использование объектов <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> для задания свойств <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> для <xref:System.Windows.Controls.GridViewColumn>.  Свойство <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> определяет содержимое ячеек столбца.  
  
 [!code-xml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> — только два свойства из тех, которые можно использовать для настройки внешнего вида заголовка столбца для элемента управления <xref:System.Windows.Controls.GridView>.  Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 В следующем примере показано, как определить <xref:System.Windows.DataTemplate>, который настраивает внешний вид ячеек в <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 В следующем примере показано использование шаблона <xref:System.Windows.DataTemplate> для определения содержимого ячейки <xref:System.Windows.Controls.GridViewColumn>.  Этот шаблон используется вместо свойства <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, которое показано в предыдущем примере <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)