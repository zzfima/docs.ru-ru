---
title: Инструкция по Изменению стиля строки в ListView, который реализует GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 150988aab368e3ffef0107d29bea5ebc53163946
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459322"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Инструкция по Изменению стиля строки в ListView, который реализует GridView
В этом примере показано, как реализовать стиль строки в элементе управления <xref:System.Windows.Controls.ListView>, который реализует режим <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Пример  
 Можно задать стиль строки в элементе управления <xref:System.Windows.Controls.ListView>, установив <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> в элементе управления <xref:System.Windows.Controls.ListView>. Задайте стиль для элементов, которые представлены как <xref:System.Windows.Controls.ListViewItem> объекты. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, используемые для вывода содержимого строки.  
  
 Полный пример, из которого взяты следующие примеры, отображает коллекцию сведений о композициях, хранящихся в базе данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.  
  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в коллекции песен. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, которые определяют способ отображения строки сведений о песне.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 В следующем примере показан <xref:System.Windows.Controls.ControlTemplate>, который добавляет текстовую строку `"Strongly Recommended"` в строку. На этот шаблон имеется ссылка в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображается, если рейтинг песни имеет значение 5 (пять). <xref:System.Windows.Controls.ControlTemplate> включает объект <xref:System.Windows.Controls.GridViewRowPresenter>, который размещает содержимое строки в столбцах, как определено в режиме представления <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 В следующем примере определяется <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Разделы практического руководства](listview-how-to-topics.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
