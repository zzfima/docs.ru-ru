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
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020742"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
В этом примере показано, как создать представление для сбора данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Представления предоставляют функциональные возможности группирования, сортировки, фильтрации и понятие текущего элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере статический ресурс с именем *помещает* определен как коллекция *месте* объектов, в котором каждый *месте* объект состоит из название города и состояние. Префикс *src* пространство имен, где источник данных *местах* определен. Префикс *scm* сопоставляется `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* сопоставляется `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 В следующем примере создается представление коллекции данных, сгруппированных по состоянию и отсортированы по названию города.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Представление может быть источником привязки, как показано в следующем примере:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Для привязки к данным XML, определенные в <xref:System.Windows.Data.XmlDataProvider> ресурсов, укажите перед именем XML символ @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.CollectionViewSource>
- [Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
