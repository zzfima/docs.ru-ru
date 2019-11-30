---
title: Практическое руководство. Привязка данных к элементам Windows Presentation Foundation (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: b623dc10bfe1b723c62b2861b4142a138904e64a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569343"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Практическое руководство. Привязка данных к элементам Windows Presentation Foundation (службы данных WCF)
С помощью WCF Data Services можно привязать Windows Presentation Foundation (WPF) элементы, такие как <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ComboBox>, к экземпляру <xref:System.Data.Services.Client.DataServiceCollection%601>, который обрабатывает события, создаваемые элементами управления, чтобы синхронизировать <xref:System.Data.Services.Client.DataServiceContext> с изменениями, внесенными в данные в элементах управления. Дополнительные сведения см. [в разделе Привязка данных к элементам управления](binding-data-to-controls-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF. При загрузке окна создается <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результата запроса, который возвращает клиентов, отфильтрованные по странам или регионам. Загружаются все страницы разбитого на страницы результата вместе со связанными заказами. После этого данные привязываются к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, который является корневым элементом управления макетом в окне WPF. Дополнительные сведения см. в разделе [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF. При загрузке окна создается <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результата запроса, который возвращает клиентов со связанными объектами, отфильтрованные по странам или регионам. Результат привязывается к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, являющегося корневым элементом управления макетом в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
