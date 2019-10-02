---
title: Практическое руководство. Привязка к источнику данных ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: dbe34cba8f01320fbf37beea65ed95656e09395c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697146"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Практическое руководство. Привязка к источнику данных ADO.NET

В этом примере показано, как привязать [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> элемент управления к ADO.NET `DataSet`.

## <a name="example"></a>Пример

В этом примере объект `OleDbConnection` используется для подключения к источнику данных, который представляет собой файл `Access MDB`, указанный в строке подключения. После установления соединения создается объект `OleDbDataAdapter`. Объект `OleDbDataAdapter` выполняет инструкцию SELECT язык SQL (SQL) для получения набора записей из базы данных. Результаты выполнения команды SQL хранятся в `DataTable` `DataSet` путем вызова метода `Fill` `OleDbDataAdapter`. `DataTable` в этом примере назван `BookTable`. Затем в примере задается свойство <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Controls.ListBox> для объекта `DataSet`.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

Затем можно привязать свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> к `BookTable` `DataSet`:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` — <xref:System.Windows.DataTemplate>, определяющая, как отображаются данные:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` преобразует `int` в цвет. При использовании этого преобразователя цвет <xref:System.Windows.Controls.TextBlock.Background%2A> третьего <xref:System.Windows.Controls.TextBlock> отображается зеленым, если значение `NumPages` меньше 350 и красный в противном случае. Здесь не приведена реализация преобразователя.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.BindingListCollectionView>
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
