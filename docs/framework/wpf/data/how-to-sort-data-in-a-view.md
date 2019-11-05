---
title: Практическое руководство. Сортировка данных в представлении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454826"
---
# <a name="how-to-sort-data-in-a-view"></a>Практическое руководство. Сортировка данных в представлении
В этом примере описывается сортировка данных в представлении.  
  
## <a name="example"></a>Пример  
 В следующем примере создается простой <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки содержит логику для сортировки элементов в <xref:System.Windows.Controls.ListBox> в порядке убывания. Это можно сделать, так как добавление элементов в <xref:System.Windows.Controls.ListBox> таким образом добавляет их в <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Controls.ListBox>, а <xref:System.Windows.Controls.ItemCollection> является производным от класса <xref:System.Windows.Data.CollectionView>. При привязке <xref:System.Windows.Controls.ListBox> к коллекции с помощью свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> можно использовать ту же методику, что и для сортировки.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Пока имеется ссылка на объект представления, для сортировки содержимого других представлений коллекций можно использовать тот же метод. Пример получения представления см. [в разделе Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md). Другой пример см. в разделе [Сортировка столбца GridView при щелчке заголовка](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Дополнительные сведения о представлениях см. в статье привязка к коллекциям в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Пример применения логики сортировки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]см. в разделе [Сортировка и группирование данных с помощью представления в XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Сортировка столбцов GridView при нажатии на заголовок](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Фильтрация данных в представлении](how-to-filter-data-in-a-view.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
