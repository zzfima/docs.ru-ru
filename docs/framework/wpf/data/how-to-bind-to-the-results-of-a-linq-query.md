---
title: Практическое руководство. Привязка к результатам запроса LINQ
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d21ac5f366e001ea76d6eda64ed62583248796f6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454416"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Практическое руководство. Привязка к результатам запроса LINQ

В этом примере показано, как выполнить запрос LINQ, а затем привязать к результатам.

## <a name="example"></a>Пример

В следующем примере создаются два списка. Первый список содержит три элемента списка.

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

При выборе элемента из первого списка вызывается следующий обработчик событий. В этом примере `Tasks` является коллекцией объектов `Task`. Класс `Task` имеет свойство с именем `Priority`. Этот обработчик событий выполняет запрос LINQ, возвращающий коллекцию объектов `Task` с выбранным значением приоритета, а затем задает это как <xref:System.Windows.FrameworkElement.DataContext%2A>:

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

Второй список привязывается к этой коллекции, так как ее <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> значение равно `{Binding}`. В результате он отображает возвращенную коллекцию (на основе <xref:System.Windows.DataTemplate>`myTaskTemplate`).

## <a name="see-also"></a>См. также

- [Обеспечение доступности данных для привязки в XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Новые возможности в WPF версии 4.5](../getting-started/whats-new.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
