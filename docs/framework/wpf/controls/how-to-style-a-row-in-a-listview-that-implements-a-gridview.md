---
title: "Инструкция по Изменению стиля строки в ListView, который реализует GridView | Microsoft Docs"
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
  - "Элементы управления GridView, применение стилей"
  - "применение стилей к ListView, реализующему GridView"
  - "Элементы управления ListView, применение стилей к строкам в GridView"
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Инструкция по Изменению стиля строки в ListView, который реализует GridView
В этом примере показано, как стиль строки в <xref:System.Windows.Controls.ListView> управления, реализующий <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> режим.  
  
## <a name="example"></a>Пример  
 Настроить стиль строки в <xref:System.Windows.Controls.ListView> управления <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> на <xref:System.Windows.Controls.ListView> элемента управления. Задание стиля для его элементов, представленных в виде <xref:System.Windows.Controls.ListViewItem> объектов. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылки <xref:System.Windows.Controls.ControlTemplate> объекты, используемые для отображения содержимого строки.  
  
 Полный пример из вытекают следующие примеры, отображает коллекцию песни информации, хранящейся в [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] базы данных. Каждая песня в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки с информацией о песне.  
  
 В следующем примере показано определение <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в наборе. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылки <xref:System.Windows.Controls.ControlTemplate> объектов, определяющих способ отображения строки с информацией о песне.  
  
 [!code-xml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 В следующем примере показан <xref:System.Windows.Controls.ControlTemplate> текстовую строку, которая добавляет `"Strongly Recommended"` в строку. Этот шаблон ссылается на <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображает, если оценка песни имеет значение 5 (пять). <xref:System.Windows.Controls.ControlTemplate> включает <xref:System.Windows.Controls.GridViewRowPresenter> объект, который размещает содержимое строки в столбцы, как определяется <xref:System.Windows.Controls.GridView> режиме.  
  
 [!code-xml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 В следующем примере определяется <xref:System.Windows.Controls.GridView>.  
  
 [!code-xml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения о ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)