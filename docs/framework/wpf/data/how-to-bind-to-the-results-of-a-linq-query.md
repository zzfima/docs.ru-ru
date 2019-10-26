---
title: Практическое руководство. Привязка к результатам запроса LINQ
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 70f4b439d231d69e5671216bc4e62d0789ce66c7
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920138"
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
- [Общие сведения о привязке данных](data-binding-overview.md)
