---
title: Практическое руководство. Привязка к результатам запроса LINQ
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d374bb69b6b7e022497403b9591b27e9ad7e2395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554997"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Практическое руководство. Привязка к результатам запроса LINQ
В этом примере показано, как выполнить запрос LINQ, а затем привязать к результатам.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два окна. Первый список содержит три элемента списка.  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 При выборе элемента в первом раскрывающемся списке вызывается следующий обработчик событий. В этом примере `Tasks` — это совокупность `Task` объектов. `Task` Класс имеет свойство с именем `Priority`. Этот обработчик событий запускает запрос LINQ, возвращающий коллекцию `Task` объектов, которые имеют значение выбранного приоритета, а затем задает его в качестве <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 Второй список привязывается к этой коллекции, так как его <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> имеет значение `{Binding}`. В результате отображается возвращаемая коллекция (на основе `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>См. также  
 [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Новые возможности в WPF версии 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
