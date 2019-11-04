---
title: Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458607"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали
По умолчанию содержимое каждого столбца в <xref:System.Windows.Controls.ListViewItem> по левому краю. Можно изменить выравнивание каждого столбца, предоставив <xref:System.Windows.DataTemplate> и установив свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> элемента в <xref:System.Windows.DataTemplate>. В этом разделе показано, как <xref:System.Windows.Controls.ListView> выравнивает свое содержимое по умолчанию и как изменить выравнивание одного столбца в <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Пример  
 В следующем примере данные в столбцах `Title` и `ISBN` по левому краю.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Чтобы изменить выравнивание `ISBN` столбца, необходимо указать, что <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> свойства каждого <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.HorizontalAlignment.Stretch>, чтобы элементы в каждой <xref:System.Windows.Controls.ListViewItem> могли охватывать или расположиться вдоль всей ширины каждого столбца. Поскольку <xref:System.Windows.Controls.ListView> привязан к источнику данных, необходимо создать стиль, который задает <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Далее необходимо использовать <xref:System.Windows.DataTemplate> для показа содержимого вместо использования свойства <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>. Чтобы отобразить `ISBN` каждого шаблона, <xref:System.Windows.DataTemplate> может просто содержать <xref:System.Windows.Controls.TextBlock>, для свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> которого задано значение <xref:System.Windows.HorizontalAlignment.Right>.  
  
 В следующем примере определяется стиль и <xref:System.Windows.DataTemplate>, необходимые для того, чтобы `ISBN` столбец по правому краю, а также изменяется <xref:System.Windows.Controls.GridViewColumn> для ссылки на <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
