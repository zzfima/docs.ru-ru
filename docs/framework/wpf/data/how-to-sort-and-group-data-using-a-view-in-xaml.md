---
title: Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460129"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
В этом примере показано, как создать представление коллекции данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Представления обеспечивают функциональные возможности группирования, сортировки, фильтрации и понятия текущего элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере статический ресурс с именем *Places* определяется как коллекция объектов *Place* , в которых каждый объект- *место* состоит из названия города и состояния. Префикс *src* сопоставляется с пространством *имен, в котором определены источники данных* . Префикс *SCM* сопоставляется с картами `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* для `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 В следующем примере создается представление коллекции данных, которая сортируется по названию города и группируются по состоянию.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Представление может быть источником привязки, как показано в следующем примере:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Для привязок к XML-данным, определенным в <xref:System.Windows.Data.XmlDataProvider> ресурсе, перед именем XML следует указывать символ @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.CollectionViewSource>
- [Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
