---
title: "Инструкция по Изменению стиля строки в ListView, который реализует GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e37d70fe1cb6aefb1404424c1a8f5339e0badf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Инструкция по Изменению стиля строки в ListView, который реализует GridView
В этом примере показано, как стиль строки в <xref:System.Windows.Controls.ListView> управления, который реализует <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> режим.  
  
## <a name="example"></a>Пример  
 Настроить стиль строки в <xref:System.Windows.Controls.ListView> управления <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> на <xref:System.Windows.Controls.ListView> элемента управления. Задать стиль для элементов, представленных в виде <xref:System.Windows.Controls.ListViewItem> объектов. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Ссылки <xref:System.Windows.Controls.ControlTemplate> объекты, которые используются для отображения содержимого строки.  
  
 Полный пример, из которого взяты следующие примеры, отображает коллекцию сведений о композициях, хранящихся в базе данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.  
  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в наборе. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Ссылки <xref:System.Windows.Controls.ControlTemplate> объектов, определяющих способ отображения строки с информацией о песню.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 В следующем примере показан <xref:System.Windows.Controls.ControlTemplate> текстовую строку, которая добавляет `"Strongly Recommended"` в строку. Этот шаблон ссылается на <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображает, если оценка песни имеет значение 5 (пять). <xref:System.Windows.Controls.ControlTemplate> Включает <xref:System.Windows.Controls.GridViewRowPresenter> объекта, в которой отображается содержимое строки в столбцах в соответствии с определением <xref:System.Windows.Controls.GridView> режим просмотра.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 В следующем примере определяется <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
